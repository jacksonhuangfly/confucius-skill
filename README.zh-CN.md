[English](README.md) | **简体中文**

# 孔子.skill

用儒家视角审视角色、相互责任、信任、礼与领导行为。在现代问题中运用相关思想，同时区分历史文本与当代解释。

版本 **1.0.0**。英文说明为默认入口，语言链接打开简体中文说明。
回答默认使用英文；明确要求中文后，使用简体中文，除非另行指定变体。
明确的语言选择在当前对话中持续有效；若仅限定某次回答或某个产物，则只对该范围生效。
也尊重其他明确的语言要求。提问、来源或 README 本身使用何种语言，不会自动切换回答语言。
必要时保留引文与标识符的原始形式。

[示例](#示例) · [安装](#安装) · [方法](#方法) · [来源](#来源) · [维护](#维护) · [边界](#边界)

## 示例

以下是现代应用的回答提纲，不是历史原话，也不是已经完成验证的历史案例。

### 职责不清为什么会破坏协作？

一个人承担交付责任，却无法决定任何关键事项，责任就难以落实。先比较已约定的职责与实际权力、资源，再明确由谁处理相互冲突的审批。这是角色分析的现代应用，不是历史原话。

### 管理者为了和谐，不希望有人提出异议。

有分寸的异议可能比隐瞒错误更有利于关系。检查意见如何被听见、如何得到处理，以及管理者回应问题的责任。和谐不能构成隐瞒问题的义务。

### 同事道歉后，我必须重新信任他吗？

道歉可以承认过错，恢复信任还需要行为变化。先明确应有的修复和你需要的边界。原谅与继续合作是选择，不是道歉自动产生的义务。

## 安装

```bash
npx skills add justinhuangai/confucius-skill
```

示例请求：

```text
用孔子的视角检查这个决策的推理。请用简体中文回答。
```

改变回答语言时，请明确说明“请用简体中文回答”或其他语言偏好。

## 方法

以下五种工作模型属于编辑性解释，不是对人物完整世界观的已验证复原。

| 模型 | 用途 |
|---|---|
| 角色与名分 | 比较称谓、实际权力与已接受的责任。 |
| 礼与交往形式 | 检查惯例是否服务于相互尊重。 |
| 仁与对人的关切 | 关注受影响者受到的实际对待。 |
| 义与合宜 | 考察行为是否合宜，不只看眼前收益。 |
| 修身与信任 | 比较宣称的标准与长期行为是否一致。 |

[Skill 入口](SKILL.md)按问题选择五条路径：

- [角色澄清](references/role-clarification.md)
- [礼与边界](references/ritual-protocol-and-boundary.md)
- [信任修复](references/trust-and-relationship-repair.md)
- [榜样式领导](references/exemplary-leadership.md)
- [长期协作](references/long-horizon-coordination.md)

八条工作启发式：

1. 问责前先澄清期待。
2. 检查相互责任，不只要求服从。
3. 按礼的实际关怀目的评价形式。
4. 区分和谐与被迫一致。
5. 比较领导者自身行为与对别人的要求。
6. 通过承认责任和后续行动修复失信。
7. 保留异议和拒绝的空间。
8. 合作不再可接受时，考虑重新协商或退出。

## 来源

仓库保留五张来源卡：《论语》索引、《大学》和《中庸》文本，以及 SEP、Britannica 的两份二手文章节选。没有收录《论语》各章正文。《大学》保留中英对照；《中庸》实际来自维基文库，保留文言原文。文章均不完整。后世传统文本不等于孔子本人著作的直接证据。

[来源清单](references/sources/README.md)说明证据边界，[六篇研究笔记](references/research/README.md)提供编辑性解释。来源正文保留原始语言。精确引用需要核对实际段落与版本，来源数量不代表质量保证。

## 仓库结构

```text
confucius-skill/
├── README.md                 # 英文说明
├── README.zh-CN.md           # 简体中文说明
├── SKILL.md                  # 路由与回答规则
├── LICENSE
├── requirements.txt          # 可选的来源采集依赖
├── references/               # 五条操作路径与提炼方法
│   ├── research/             # 六篇主题研究笔记
│   └── sources/              # 采集文本、元数据与证据边界
├── scripts/                  # 采集、转换与检查工具
└── tests/                    # 脚本回归测试
```

## 维护

在仓库根目录使用 Python 3.10 或更高版本运行：

```bash
python3 scripts/check_links.py .
python3 scripts/check_sources_inventory.py .
python3 scripts/check_research_repetition.py references/research
python3 -m unittest discover -s tests -v
```

检查器和核心测试只依赖标准库；安装 Beautiful Soup 后还会运行可选的 HTML 集成测试。
网页或 PDF 采集需要先执行 `python3 -m pip install -r requirements.txt`。
采集工具要求显式填写 `--language`，记录来源的实际语言，例如 `en`、`zh-CN`、
`lzh`、`mul` 或其他合适标签；无法确定时用 `und`。它保留原文，不执行翻译。
公开可访问不代表可以忽略来源使用条款。

字幕下载需要可选工具 `yt-dlp`。默认英文，先尝试人工字幕，再尝试同语言自动字幕。
`--language zh-CN` 只选择明确标记的简体中文字幕；两种模式均不回退到其他语言或繁体中文。
工具忽略外部 yt-dlp 配置，以保持选择规则一致。命令行提示保留英文。

```bash
bash scripts/download_subtitles.sh "VIDEO_URL" outputs/subtitles
bash scripts/download_subtitles.sh --language zh-CN "VIDEO_URL" outputs/subtitles
```

`scripts/srt_to_transcript.py` 可清理已有的 SRT 或 VTT 文件。
维护时保留来源署名、原始语言、版权声明和截断说明。修改研究材料时参考
[提炼方法](references/extraction-framework.md)。自动检查不证明历史论断为真，也不验证回答质量；
还需检查真实使用情景，并同步维护两版 README。

## 边界

- 《论语》是传世文献集合；精确归引需要查阅实际段落。
- 批判性地呈现历史等级关系；现代应用明确尊重同意、平等与问责。
- 不以思想权威为胁迫、压制异议、强制和解或维持关系辩护。
- 哲学解释不能替代当前事实或相关专业判断。

## 致谢与许可

项目由 Jackson Huang 维护，最初使用
[Nuwa.skill](https://github.com/alchaincyf/nuwa-skill)辅助搭建，感谢其作者与贡献者提供工具。

项目原创内容采用 [MIT License](LICENSE)。第三方文本、译文、网站材料和节选保留各自的权利与使用条款；
收录于本仓库不代表将其重新授权为 MIT。
