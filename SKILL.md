---
name: build-minimal-decision-ux
description: Design, review, and implement polished interfaces that let people complete their primary goal with minimal steps, navigation, typing, choices, and cognitive load. Use for UI/UX work on apps, operational tools, calendars, scheduling, dashboards, forms, hover or touch interactions, responsive layouts, workflow simplification, information hierarchy, aesthetics, or accessibility, especially when users ask for one-screen completion, mouse-first actions, proactive recommendations, or minimal-choice design.
---

# Build Minimal Decision UX

Optimize the interface for the user's completion event, not for feature exposure. Make the system absorb complexity through defaults, recommendations, conflict detection, and clear visual hierarchy.

Read [references/research-foundations.md](references/research-foundations.md) before introducing a new interaction pattern, data visualization, or visual language. Use its source matrix to justify consequential design decisions.

## Use UI UX Pro Max As An Advisory Tool

Use the installed `$ui-ux-pro-max` skill and its local search database when the task needs visual directions, product-pattern alternatives, palettes, typography, motion guidance, chart patterns, or stack-specific UI checks. Treat its output as candidates, not authority; filter every recommendation through the user's primary job, the existing product system, accessibility, and the minimal-decision rules in this skill.

Start a substantial new UI direction with one design-system query:

```bash
UIUX_PRO_MAX="${CODEX_HOME:-$HOME/.codex}/skills/ui-ux-pro-max"
python3 "$UIUX_PRO_MAX/scripts/search.py" "<product type> <industry> <interaction goals>" --design-system --density <1-10> --motion <1-10>
```

Use focused searches instead of regenerating a full style system for narrow changes:

```bash
python3 "$UIUX_PRO_MAX/scripts/search.py" "<specific usability question>" --domain ux
python3 "$UIUX_PRO_MAX/scripts/search.py" "<specific visual question>" --domain style
python3 "$UIUX_PRO_MAX/scripts/search.py" "<component or performance question>" --stack react
```

Reject outputs that introduce landing-page composition, large marketing typography, ornamental cards, excessive color, or motion unrelated to the operational task. Do not overwrite an established product style merely because the tool ranks another style highly. Record only the recommendations that materially improve the current user path.

## Establish The Job

Before proposing or editing UI, write this compact frame internally:

```text
Actor: who acts and in what context
Job: the single outcome they came to achieve
Completion: the visible event that proves success
Constraints: device, frequency, data density, accessibility, reversibility
```

Inspect the existing product and code before deciding. Preserve familiar domain and product conventions unless they obstruct the primary job.

## Audit The Current Path

Trace the most common successful path and count:

- pointer actions and long pointer travel
- clicks or taps
- typed fields and characters
- decisions and simultaneously visible options
- context switches, panels, routes, and scrolls
- facts the user must remember or compare mentally
- error recovery steps

Distinguish necessary complexity from complexity the system can resolve. Do not remove information needed to trust a recommendation or understand consequences.

## Design The Shortest Trustworthy Path

Use this order whenever input can be reduced:

1. Infer safely from context or existing data.
2. Apply a reversible default.
3. Recommend one best action with a short reason.
4. Show two or three ranked alternatives only when materially useful.
5. Ask the user only when the system cannot infer the answer or the consequence is costly to reverse.

Structure the primary surface in this order:

1. Current status.
2. Recommended next action.
3. Minimum evidence needed to trust it.
4. One primary action.
5. Details or rare alternatives on demand.

Prefer the loop `trigger -> preview -> one action -> immediate feedback or undo`. Keep the action in the same visual context as the evidence used to decide it.

## Choose Interactions Deliberately

- Use hover for reversible preview only. Provide equivalent focus and tap behavior.
- Use click or tap to pin, select, or commit.
- Use drag only when direct manipulation is substantially faster, and always provide a single-pointer alternative.
- Commit reversible actions immediately and offer undo. Confirm destructive, expensive, or irreversible actions.
- Keep hover content dismissible, hoverable, and persistent until pointer or focus leaves intentionally; support `Esc`.
- Do not trigger a context change from focus alone.
- Make repeated actions mouse-first when appropriate, but preserve complete keyboard operation.
- Keep the common path visible. Put infrequent settings and exhaustive detail behind one explicit control.

For dense scheduling and operational tools, prefer `overview first, details on demand`. Aggregate many people's states in one comparable row or layer, then expose individual detail on hover, focus, or selection. Encode availability, existing commitments, votes, and conflicts with separate visual channels; never overload one color or height with multiple meanings.

## Build A Calm Visual System

- Use alignment, spacing, typography, and grouping before color, borders, shadows, or containers.
- Use a 4px or 8px spacing rhythm and stable responsive dimensions.
- Keep typography compact and readable; use system sans-serif fonts with strong Korean support for Korean interfaces.
- Give one action clear visual dominance per surface.
- Use familiar icons for tools and concise text for consequential commands.
- Avoid nested cards, decorative gradients, floating blobs, excessive pills, and repeated tinted boxes.
- Keep card radii at 8px or less unless the existing system specifies otherwise.
- Use neutral surfaces with a small semantic palette. Never rely on color alone.
- Use depth only to explain interaction or state. Restrict 3D to subtle lift, press, or selection feedback; never distort quantitative comparison.
- Limit motion to continuity, selection, and feedback. Prefer 150-250ms transitions and honor `prefers-reduced-motion`.
- Prevent text truncation on information the user must compare. Use density rules and explicit overflow paths for exceptional volume.
- Keep dimensions stable so hover, loading, selection, and dynamic labels do not shift the layout.

Avoid an AI-generated appearance: uniform card grids, oversized headings in work tools, gratuitous copy, too many rounded containers, saturated multi-color status fills, and ornamental depth. Let the domain data create the visual character.

## Meet Accessibility Baselines

- Target at least WCAG 2.2 AA.
- Provide visible keyboard focus and logical focus order.
- Prefer 44px interactive targets; never violate WCAG's 24px minimum or spacing exception.
- Provide non-drag and non-hover alternatives for essential actions.
- Use text, icon, shape, pattern, or position in addition to color for status.
- Preserve legibility under zoom, reflow, high contrast, and reduced motion.
- Announce asynchronous status and completion without unexpectedly moving focus.
- Make labels describe outcomes, such as `15:00-16:00 후보로 추가`, instead of generic `확인`.

## Implement In The Existing System

- Reuse the repository's components, tokens, icons, state patterns, and interaction conventions.
- Separate visual state from domain state. Give each semantic state one stable name and representation.
- Build the smallest complete behavior, including empty, loading, dense, conflict, error, selected, and success states.
- Avoid abstractions that do not reduce real duplication or state complexity.
- Keep touch and pointer behavior equivalent without forcing identical layouts.

## Verify The Outcome

Test the complete primary path with realistic data, not only isolated components. Check desktop, tablet, mobile, keyboard, touch, zoom, reduced motion, and dense-content states as relevant.

Measure or estimate before and after:

- time to first useful information
- time and actions to completion
- number of decisions and visible alternatives
- typing required
- context switches and pointer travel
- task success, error rate, and recovery effort
- user confidence in the recommendation

Use HEART selectively: choose a goal, then signals, then metrics. Do not track metrics without a product decision they can inform.

Finish with a subtraction pass:

1. Remove one control that duplicates another path.
2. Remove one label that hierarchy or familiar iconography already communicates.
3. Remove one movement, click, or context switch the system can absorb.
4. Restore anything whose removal harms comprehension, trust, accessibility, or recovery.

## Communicate Decisions

When proposing alternatives, present at most three meaningfully different options, recommend one, and state the user-flow tradeoff. When implementing, summarize the changed completion path and verification results rather than listing cosmetic changes.

Do not claim simplicity from fewer visible elements alone. A design is simpler only when users reach the correct outcome faster, with less memory, uncertainty, and recovery effort.
