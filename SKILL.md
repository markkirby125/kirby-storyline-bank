---
name: kirby-storyline-bank
description: "Use when eliciting, cataloguing, or retrieving personal business scars and lessons into a storyline bank for PLR personalisation."
category: writing
triggers: [story-dataset, extract-stories, storyline-bank, personal-anecdotes, life-lessons-bank, experience-extractor]
risk: unverified
author: paul-kirby
tags: [kirby, ai-agent, workflow]
---

# SOP: Storyline Bank Extraction, Curation & Retrieval

> Standard Operating Procedure for extracting personal experiences, business failures, client breakthroughs, and milestone moments from human experts, cataloging them into a structured Storyline Bank, and dynamically querying them for content fusion.

---

## 1. The 4 Core Story Archetypes

Every entry in the Storyline Bank falls into one of four high-conversion archetypes:

### 1. The "Expensive Mistake" (Pain & Humility)
* **Definition:** A time the author lost money, wasted months, or publicly failed due to bad assumptions.
* **Conversion Power:** Destroys cynicism, builds immediate trust, establishes the author as someone who paid the tuition so the reader doesn't have to.
* **Example:** *"Spent $6,000 on custom web dev for an idea that had zero pre-orders."*

### 2. The "Accidental Breakthrough" (Epiphany)
* **Definition:** A moment when abandoning conventional wisdom or making an imperfect pivot produced unexpected results.
* **Conversion Power:** Validates simple, unconventional action over perfectionism.
* **Example:** *"Sent an ugly plain-text email with typos from an airport terminal and had the biggest launch day of the year."*

### 3. The "Client in the Trenches" (Third-Party Proof)
* **Definition:** A real case study of someone who was stuck in the reader's exact situation and overcame it.
* **Conversion Power:** Proves the framework works for ordinary people, not just the author.
* **Example:** *"Sarah was terrified to charge more than $50/hour until we packaged her services into a $1,500 audit."*

### 4. The "Line in the Sand" (Philosophy & Stance)
* **Definition:** An event or conversation that caused the author to reject a mainstream industry practice permanently.
* **Conversion Power:** Polarizes the audience, attracts ideal clients, repels bad-fit clients.
* **Example:** *"Fired our highest-paying client after they disrespected our junior designer on a Slack call."*

---

## 2. Extraction Protocol: Socratic Prompts

When building a Storyline Bank with an operator, execute the following interrogation cycle across common topics:

```markdown
Run this interview with the operator:
1. "Tell me about the single most expensive mistake you made in your first 2 years."
2. "What's a piece of common advice you followed obediently that blew up in your face?"
3. "Describe a moment when you felt like quitting. What was the exact physical setting, and what happened next?"
4. "What is a client result you are secretly most proud of, especially if they started with massive disadvantages?"
5. "What is something you believed 5 years ago that you now realize was totally wrong?"
```

---

## 3. Storyline Bank Entry Schema

Store all storylines in a centralized file `storyline_bank.json` or `.yaml` following this schema:

```json
[
  {
    "id": "STORY-042",
    "title": "The $8k Funnel Collapse",
    "archetype": "Expensive Mistake",
    "topics": ["funnels", "automation", "tech_stack", "launching"],
    "target_emotions": ["overwhelm", "shame", "frustration"],
    "one_sentence_hook": "I once watched $8,000 in ad spend evaporate in 48 hours because a single webhook was disconnected.",
    "narrative_beats": {
      "context": "Running a high-volume flash sale for a client in 2021.",
      "conflict": "Traffic was surging, but Stripe dashboard was dead silent.",
      "discovery": "Found a broken Zapier connection routing leads to a 404 page.",
      "resolution": "Rebuilt the pipeline with zero complex automations and salvaged the launch."
    },
    "core_lesson": "Complex automations are failure magnets; simple static pipelines protect your margins.",
    "usable_snippets": [
      "Simplicity isn't just aesthetic; it's operational insurance.",
      "If your sales funnel requires four separate third-party apps to pass data before taking money, you aren't running an e-commerce store—you're running a digital house of cards."
    ]
  }
]
```

---

## 4. Agent Query & Retrieval Instructions

When an agent needs a story for personalizing a piece of content:
1. **Analyze Subject Matter:** Extract keywords and emotional triggers from the incoming content (e.g., `["email deliverability", "fear of hitting send"]`).
2. **Scan Bank:** Search `storyline_bank.json` for matches against `topics` and `target_emotions`.
3. **Select Best Match:** Pick the entry with the highest topical alignment.
4. **Contextualize:** Use the `usable_snippets` and `narrative_beats` to seed the narrative anchor in `kirby-plr-personalizer`.

---

## 5. Verification Checklist

Before considering a storyline extraction complete, verify:
- [ ] Are all fields in the schema fully populated?
- [ ] Does the `core_lesson` connect logically to a specific business topic?
- [ ] Are there at least two `usable_snippets` capturing the author's distinct phrasing?
- [ ] Has the entry been persisted to the `storyline_bank.json` file?


## Examples

*(Add specific conversational examples here showing how the agent should behave.)*


## Limitations (When NOT to Use)

- Do not use this skill outside of its intended scope.
- Stop and ask the user for clarification if the requirements are ambiguous.
