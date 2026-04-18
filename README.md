**English** | [简体中文](README.zh-CN.md)

# Confucius.skill

A Confucian perspective for examining roles, reciprocal responsibility, trust, ritual, and leadership. It adapts ideas for modern questions while distinguishing historical texts from present-day interpretation.

Version **1.0.0**. The English overview is the default; the language link opens
the Simplified Chinese overview. Responses default to English. Explicitly ask
for Chinese to use Simplified Chinese, unless you specify another variant.
An explicit language choice persists for the conversation; a request limited to
one answer or artifact applies only there. Other explicit language requests are
honored. The language of a prompt, source, or README alone does not switch the
response language. Source quotations and identifiers keep their original form
where necessary.

[Examples](#examples) · [Install](#install) · [Framework](#framework) · [Sources](#sources) · [Maintenance](#maintenance) · [Boundaries](#boundaries)

## Examples

These are modern response outlines, not quotations or completed historical case studies.

### Why does unclear ownership make teamwork fail?

A role cannot carry delivery responsibility coherently if someone else can override every decision. First compare the agreed duties with actual authority and resources; then clarify who resolves competing approvals. This is a modern use of role analysis, not a historical quotation.

### Our manager asks for harmony by discouraging disagreement.

Respectful disagreement can preserve a relationship better than concealed error. Examine how concerns are heard and resolved, including the manager's responsibility to respond. Harmony does not establish a duty to conceal problems.

### A colleague apologized. Must I trust them again?

An apology can acknowledge a breach; restored trust also depends on changed conduct. Clarify the repair owed and the boundaries you need. Forgiveness and continued cooperation are choices, not duties created by the apology.

## Install

```bash
npx skills add justinhuangai/confucius-skill
```

Example request:

```text
Use Confucius's perspective to examine the reasoning in this decision.
```

For a language change, add `Answer in Simplified Chinese` or another explicit preference.

## Framework

The five working models below are editorial interpretations, not a verified reconstruction of an entire worldview.

| Model | Use |
|---|---|
| Roles and names | Compare titles, actual authority, and accepted duties. |
| Li and shared form | Ask whether a practice serves respectful interaction. |
| Ren and humane regard | Consider how affected people are actually treated. |
| Yi and appropriateness | Examine whether an action is fitting beyond its immediate benefit. |
| Cultivation and trust | Compare stated standards with consistent conduct over time. |

The [skill entrypoint](SKILL.md) selects among five routes:

- [Role clarification](references/role-clarification.md)
- [Ritual and boundaries](references/ritual-protocol-and-boundary.md)
- [Trust repair](references/trust-and-relationship-repair.md)
- [Exemplary leadership](references/exemplary-leadership.md)
- [Long-term cooperation](references/long-horizon-coordination.md)

Eight working heuristics:

1. Clarify expectations before assigning blame.
2. Check reciprocal duties, not only obedience.
3. Judge a ritual by the humane purpose it serves.
4. Distinguish harmony from compelled agreement.
5. Compare the leader's conduct with their demands.
6. Repair a breach through acknowledgment and follow-through.
7. Preserve room for dissent and refusal.
8. Consider renegotiation or exit when cooperation is no longer acceptable.

## Sources

Five source records are retained: an Analects index, Great Learning and Doctrine of the Mean text captures, and two secondary article excerpts from SEP and Britannica. The Analects chapters themselves are not captured. Great Learning is bilingual; Doctrine of the Mean retains classical Chinese from Wikisource. The articles are incomplete. Later tradition texts are not direct evidence of Confucius's authorship.

See the [source inventory](references/sources/README.md) for evidence boundaries and the [six research notes](references/research/README.md) for editorial interpretation. Source text remains in its original language. Exact quotations require checking the actual passage and edition; a source count is not a quality guarantee.

## Repository Layout

```text
confucius-skill/
├── README.md                 # English overview
├── README.zh-CN.md           # Simplified Chinese overview
├── SKILL.md                  # Routing and response rules
├── LICENSE
├── requirements.txt          # Optional source-capture dependencies
├── references/               # Five routes and extraction guidance
│   ├── research/             # Six thematic editorial notes
│   └── sources/              # Captures, metadata, and evidence limits
├── scripts/                  # Capture, conversion, and checks
└── tests/                    # Script regression tests
```

## Maintenance

Run the checks from the repository root with Python 3.10 or later:

```bash
python3 scripts/check_links.py .
python3 scripts/check_sources_inventory.py .
python3 scripts/check_research_repetition.py references/research
python3 -m unittest discover -s tests -v
```

The checks and core tests use the standard library. Optional HTML integration
tests run when Beautiful Soup is installed. For web or PDF capture, install
`python3 -m pip install -r requirements.txt`. The capture tool requires
`--language` with the source's actual language (`en`, `zh-CN`, `lzh`, `mul`, or
another appropriate tag; `und` if unknown). It preserves source text and does
not translate it. Public access is not permission to ignore source terms.

Subtitle download requires the optional `yt-dlp` command. It defaults to English,
trying manual then automatic subtitles in that language. `--language zh-CN`
selects explicitly labeled Simplified Chinese tracks; neither choice falls back
to another language or to Traditional Chinese. External yt-dlp configuration is
ignored to keep selection predictable. Command-line messages remain English.

```bash
bash scripts/download_subtitles.sh "VIDEO_URL" outputs/subtitles
bash scripts/download_subtitles.sh --language zh-CN "VIDEO_URL" outputs/subtitles
```

Use `scripts/srt_to_transcript.py` to clean an existing SRT or VTT file. Keep
source attribution, original language, copyright notices, and truncation visible.
Use the [extraction framework](references/extraction-framework.md) when changing
research. Mechanical checks do not verify historical truth or answer quality;
review realistic requests and keep both README versions aligned.

## Boundaries

- The Analects is a transmitted collection; exact attribution requires a passage-bearing source.
- Historical hierarchy is described critically. Modern consent, equality, and accountability are explicit design commitments.
- The skill does not justify coercion, suppress dissent, or require reconciliation or continued relationships.
- Philosophical interpretation does not replace current facts or relevant specialist expertise.

## Credits and License

Maintained by Jackson Huang and originally assembled with
[Nuwa.skill](https://github.com/alchaincyf/nuwa-skill). Thanks to its authors and
contributors for the tooling.

Original project content is released under the [MIT License](LICENSE).
Third-party texts, translations, website material, and excerpts retain their
respective rights and terms; inclusion does not relicense them under MIT.
