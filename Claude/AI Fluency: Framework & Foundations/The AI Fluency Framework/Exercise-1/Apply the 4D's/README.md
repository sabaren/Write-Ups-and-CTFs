# Claude AI Fluency: 4D Framework Exercise Prompts
**Course/Module:** AI Fluency: Framework & Foundations (Anthropic Academy)  
**Objective:** Construct context-rich prompts for Communication, Research, and Creative scenarios using the 4D Framework (Delegation, Description, Discernment, Diligence).

---

## 1. Communication Project: Marketing Email Campaign

### Baseline / Naive Prompt
```text
Write a series of 3 marketing emails for our new product launch.

```

### Engineered Prompt (4D Applied)

```text
<system_role>
You are an expert Copywriter and Email Marketing Strategist.
</system_role>

<context>
We are launching a new privacy-focused, open-source productivity tool. Our target audience consists of tech-savvy professionals and developers who value data ownership and clean design.
</context>

<delegation>
- AI Scope: Generate 3 draft emails (Announcement, Value Deep-Dive, Call to Action) and suggest compelling subject line variants.
- Human Scope: Final tone adjustments, brand voice alignment, and final sending approval.
</delegation>

<description_3ps>
- Product: A 3-part email sequence with clear structure (Subject, Preview Text, Body, single CTA).
- Process: Draft one email at a time. Highlight key value propositions without using artificial hype or buzzwords.
- Performance: Professional, direct, and transparent tone. Keep body copy under 150 words per email.
</description_3ps>

<constraints>
Do not use generic marketing cliches (e.g., "game-changer," "unlock your potential"). Focus on concrete utility.
</constraints>

```

---

## 2. Research Project: Dataset Vulnerability Patterns

### Baseline / Naive Prompt

```text
Look at this data and tell me what security issues we have.

```

### Engineered Prompt (4D Applied)

```text
<system_role>
You are a Lead Data Analyst and Security Researcher.
</system_role>

<context>
I am reviewing a dataset of system authentication logs and network patch levels following a recent infrastructure update across remote endpoints.
</context>

<delegation>
- AI Scope: Group raw data points, identify statistical anomalies, and construct a markdown summary table of patch completion rates.
- Human Scope: Determine root causes, assess organizational risk levels, and define remediation policy.
</delegation>

<description_3ps>
- Product: An anomaly report containing summary tables, identified statistical outliers, and data distribution notes.
- Process: First, list the criteria used to identify anomalies. Second, present the aggregated metrics table. Third, summarize notable data clusters.
- Performance: Objective, analytical, and academic tone. Avoid speculating on intent or cause without data evidence.
</description_3ps>

<diligence_guardrails>
Do not attempt to infer user identities or extrapolate beyond the provided log boundaries. Highlight any missing or corrupt data fields explicitly.
</diligence_guardrails>

```

---

## 3. Creative Project: Character Concept Development

### Baseline / Naive Prompt

```text
Give me 5 character ideas for a sci-fi story.

```

### Engineered Prompt (4D Applied)

```text
<system_role>
You are a Narrative Designer and Worldbuilding Consultant.
</system_role>

<context>
I am developing a near-future cyberpunk graphic novel centered around low-tech resistance groups operating in a hyper-automated metropolis.
</context>

<delegation>
- AI Scope: Propose 3 character archetypes with distinct motivations, flaws, and functional roles within the world.
- Human Scope: Final character selection, dialogue voice writing, and integration into the main plot structure.
</delegation>

<description_3ps>
- Product: 3 structured character profiles including Name/Alias, Core Motivation, Primary Conflict, and Key Visual Detail.
- Process: Ground each character in the physical reality of the setting. Ensure their motivations stem from the central thematic conflict (human agency vs. automation).
- Performance: Evocative, grounded, and concise descriptions. Avoid high-fantasy or space-opera tropes.
</description_3ps>

<discernment_check>
After presenting the profiles, provide 1 potential narrative weakness or clichéd element for each character that I should watch out for during development.
</discernment_check>

```

---

## 4. Key Takeaways & Best Practices

| Scenario | Primary 4D Focus | Strategic Benefit |
| --- | --- | --- |
| **Communication** | **Description & Performance** | Eliminates marketing fluff by constraining tone and word count explicitly. |
| **Research** | **Delegation & Diligence** | Prevents AI from inventing causal links while automating heavy data grouping. |
| **Creative** | **Discernment Guidance** | Prompts the model to critique its own ideas, surfacing clichés before drafting begins. |

```

```
