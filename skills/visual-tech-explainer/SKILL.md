---
name: visual-tech-explainer
description: Create comprehensive, visually compelling explanations of technology concepts using bento-box layouts, diagrams, timelines, comparisons, and progressive disclosure. Use when a user asks how a technology works, requests a visual explanation or interactive explainer, wants a complex technical system explained in layman's terms, or needs a self-contained educational web presentation instead of a conventional article or chat response.
---

# Visual Tech Explainer

Turn a technology topic into a self-contained visual learning experience. Optimize for understanding, not decoration.

## Workflow

1. Identify the learner, their likely prior knowledge, and the central question.
2. Research unstable or implementation-specific facts using authoritative primary sources when browsing is available.
3. Form a single plain-language mental model before introducing terminology.
4. Select only the visual structures that materially clarify the concept. Read [visual-patterns.md](references/visual-patterns.md) for the available patterns.
5. Build a responsive, self-contained HTML presentation using a bento-box layout.
6. Verify factual accuracy, reading order, responsive behavior, contrast, and keyboard accessibility.
7. Display the result inline when the host supports interactive artifacts. Otherwise save the complete HTML file and provide its path.

## Explanation sequence

Use this order unless the topic demands another:

1. **One-sentence answer** — state what the technology accomplishes.
2. **Mental model** — explain it through one concrete analogy, clearly labeled as an analogy.
3. **System map** — show the actors, boundaries, and direction of information flow.
4. **Step-by-step mechanism** — reveal what happens in chronological order.
5. **What is actually transmitted or computed** — distinguish signals, identifiers, data, and control messages.
6. **Constraints and failure modes** — explain latency, accuracy, privacy, platform, environmental, or scaling limitations.
7. **Implementation view** — include APIs, components, or pseudocode only when useful to the learner.
8. **Recap** — restate the model in three to five short points.

## Design requirements

- Use a bento grid with varied card sizes to create hierarchy.
- Give every card one teaching job.
- Prefer diagrams, spatial relationships, and annotated motion over paragraphs.
- Keep body copy concise and define jargon at first use.
- Use consistent colors for the same actors and signals across every card.
- Encode meaning with labels or shape as well as color.
- Make animations optional, subtle, and compatible with reduced-motion preferences.
- Avoid decorative charts, generic stock imagery, fake metrics, and walls of text.
- Ensure the page remains understandable without animation or interaction.

## Output contract

Produce one portable HTML file with embedded CSS and JavaScript unless the user requests another format. Do not require a framework, build step, external font, or proprietary host feature. If external assets are necessary, explain why and keep the experience functional when they fail.

When host-specific capabilities improve the result, treat them as optional enhancements. Never make the core explanation depend on Codex-, Claude-, Cursor-, or another vendor-specific directive.

## Quality check

Before delivery, confirm:

- A non-expert can describe the core mechanism after scanning the page.
- The visual flow matches the actual technical flow.
- Analogy and reality are visibly separated.
- Important caveats appear beside the claim they qualify.
- The layout works at narrow and wide viewport sizes.
- Interactive elements have visible labels, focus states, and non-interactive fallbacks.
