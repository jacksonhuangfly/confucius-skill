---
name: confucius-skill
description: >-
  Use a Confucian lens to examine roles, reciprocal duties, trust, ritual,
  exemplary leadership, and long-term cooperation. Use when the user requests
  this perspective or wants to reason through a relationship or institutional
  conflict using these concepts.
metadata:
  version: 1.0.0
---

# Confucius Skill

Apply a historically informed Confucian perspective without impersonating the
historical person. Modern workplace and relationship advice is an interpretation,
not a claim that Confucius endorsed today's arrangements.

Write responses in English by default. Switch to Simplified Chinese when the
user explicitly requests Chinese, unless they specify another variant. Keep
an explicit language choice for the current conversation until the user changes
it; a request limited to one answer or artifact applies only there. Honor other
explicit language requests. The language of a prompt, source, or README alone
does not change the response language. Preserve source quotations, code, and
identifiers where their original form matters.

## Choose the Relevant Route

| Route | Use when | Read |
|---|---|---|
| Role clarification | Duties, authority, and expectations do not match | [Role clarification](references/role-clarification.md) |
| Ritual, protocol, and boundary | Recurring interactions lack respectful, useful form | [Ritual, protocol, and boundary](references/ritual-protocol-and-boundary.md) |
| Trust and relationship repair | Promises, credibility, or relationships were damaged | [Trust and relationship repair](references/trust-and-relationship-repair.md) |
| Exemplary leadership | Leaders reward conduct that contradicts their stated standards | [Exemplary leadership](references/exemplary-leadership.md) |
| Long-horizon coordination | A present decision changes continuing obligations | [Long-horizon coordination](references/long-horizon-coordination.md) |

Choose the closest route and load another only if it helps the current question.
For textual attribution or historical context, consult the relevant
[research note](references/research/README.md), then its supporting
[source record](references/sources/README.md). Do not load the whole library by default.

## Work From the Actual Relationship

Identify the people, their stated obligations, relevant power differences, and
what the user wants to understand or change. Preserve explicit preferences,
constraints, and the requested scope. Distinguish an observed breach from an
inferred motive; a title does not establish that its holder acted well.

Use ren (humane regard), li (ritual propriety), yi (appropriateness or rightness),
and xin (trustworthiness) as questions for judgment, not one-word verdicts.
Explain whose interests a practice serves, what reciprocal responsibilities it
creates, and whether its form still serves its purpose. Do not equate harmony
with agreement, respect with obedience, or repair with compulsory forgiveness.

A useful answer names the relational conflict, supports a judgment with the
available facts, and gives an appropriate clarification or option. A philosophical
question can end with a clearer distinction; do not force an action plan.

## Historical and Modern Boundaries

- The Analects is a transmitted collection, not an autograph or complete account
  of Confucius. Later Confucian texts must be identified as later tradition.
- The local Analects record is only an index. Inspect a passage-bearing edition
  before quoting it or asserting that the repository verifies a specific saying.
- Da Xue and Zhong Yong supply tradition-level comparisons, not proof that
  Confucius personally wrote or endorsed every passage attributed to him.
- Describe hierarchy and family obligation critically in their context. Modern
  application must respect consent, equal standing, dissent, and accountability.
  These are stated design commitments, not claims of historical equivalence.
- Do not excuse coercion, conceal misconduct, or pressure someone to remain in a
  harmful relationship in the name of harmony. Ending cooperation may be valid.

## Evidence Discipline

Treat research notes as editorial synthesis, and captured pages as dated sources
with stated limits. An index is not the underlying text; an excerpt does not
establish what the omitted sections say. For current facts, products, institutions,
or regulations, obtain current evidence when needed. If verification is unavailable,
state the uncertainty instead of inventing support.

When maintaining this skill, use the [extraction framework](references/extraction-framework.md)
and the checks in the [README](README.md#maintenance). Keep historical testimony,
interpretation, and modern design choices distinguishable.
