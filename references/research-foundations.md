# Research Foundations

Use this reference to ground design decisions in established guidance. It summarizes sources; it does not replace testing with the product's actual users and data.

## Derived Principles

1. Start with the user's completion event, not a screen or feature list.
2. Make the system perform the hard work: infer, filter, rank, prevent conflicts, and preserve context.
3. Prefer recognition over recall. Put comparison evidence next to the action.
4. Keep one dominant action and expose rare detail progressively without hiding essential state.
5. Use preview for orientation and explicit action for commitment.
6. Treat accessibility as interaction quality, not a final compliance pass.
7. Encode each meaning with a distinct visual channel; color alone is insufficient.
8. Use motion and depth only to explain change, continuity, or manipulability.
9. Measure task completion and recovery, then iterate.

## Source Matrix

### User Need, Simplicity, And Measurement

1. [GOV.UK Government Design Principles](https://www.gov.uk/guidance/government-design-principles) — Start with user needs, do less, make the hard work simple, design with data, understand context, and iterate.
2. [GOV.UK Define user needs](https://www.gov.uk/guidance/define-user-needs) — Research the users, operating context, risks, and outcomes before selecting technology or features.
3. [Nielsen Norman Group: 10 Usability Heuristics](https://www.nngroup.com/articles/ten-usability-heuristics/) — Preserve system visibility, user control, consistency, error prevention, recognition, efficiency, and minimalist relevance.
4. [Nielsen Norman Group: Recognition Rather Than Recall](https://www.nngroup.com/articles/recognition-and-recall/) — Keep required information and choices visible or readily retrievable at the decision point.
5. [Nielsen Norman Group: Progressive Disclosure](https://www.nngroup.com/articles/progressive-disclosure/) — Show common, important controls first and reveal advanced or rare options through predictable disclosure.
6. [Google Research: HEART framework](https://research.google/pubs/measuring-the-user-experience-on-a-large-scale-user-centered-metrics-for-web-applications/) — Map product goals to signals and user-centered metrics rather than collecting undirected analytics.

### Platform And Product Design Systems

7. [Apple Human Interface Guidelines: Design principles](https://developer.apple.com/design/human-interface-guidelines/design-principles) — Favor hierarchy, harmony, consistency, familiarity, feedback, context, user control, and forgiveness.
8. [Apple HIG: Accessibility](https://developer.apple.com/design/human-interface-guidelines/accessibility) — Use familiar simple interactions, alternatives, sufficient controls, and inclusive defaults.
9. [Apple HIG: Pointing devices](https://developer.apple.com/design/human-interface-guidelines/pointing-devices) — Make pointer feedback reflect element behavior and keep hit regions forgiving and predictable.
10. [Microsoft Fluent 2: Design principles](https://fluent2.microsoft.design/design-principles) — Build for focus, reduce clutter and noise, stay natural to the platform, and adapt without losing familiarity.
11. [Microsoft Fluent 2: Accessibility](https://fluent2.microsoft.design/accessibility) — Use predictable hierarchy, scannable structure, keyboard access, clear focus, semantic implementation, and plain language.
12. [Atlassian Design System: Accessibility](https://atlassian.design/foundations/accessibility/) — Consistent familiar patterns lower cognitive load; accessible components still require end-to-end testing.
13. [Shopify Polaris: Accessibility](https://polaris-react.shopify.com/foundations/accessibility) — Combine functional, consistent, inclusive UI with correct focus behavior for overlays and navigation.

### Accessibility And Input

14. [W3C WCAG 2.2](https://www.w3.org/TR/WCAG22/) — Use the normative baseline for perceivable, operable, understandable, and robust interfaces.
15. [W3C WCAG 2.2 Understanding](https://www.w3.org/WAI/WCAG22/Understanding/) — Consult criterion-specific intent, benefits, examples, and test guidance.
16. [W3C: What's New in WCAG 2.2](https://www.w3.org/WAI/standards-guidelines/wcag/new-in-22/) — Provide single-pointer alternatives to dragging and improve focus and target usability.
17. [W3C: Target Size Minimum](https://www.w3.org/WAI/WCAG22/Understanding/target-size-minimum) — Ensure at least 24 by 24 CSS pixels or adequate spacing; prefer larger targets for frequent actions.
18. [W3C: Content on Hover or Focus](https://www.w3.org/WAI/WCAG21/Understanding/content-on-hover-or-focus) — Hover/focus content must be dismissible, hoverable, and persistent.
19. [W3C: SCR39 Hover Technique](https://www.w3.org/WAI/WCAG21/Techniques/client-side-script/SCR39) — Let the pointer enter revealed content and support intentional dismissal such as Escape.
20. [W3C: On Focus](https://www.w3.org/WAI/WCAG21/Understanding/on-focus.html) — Do not cause an unexpected context change merely because an element receives focus.
21. [W3C: Focus Appearance](https://www.w3.org/WAI/WCAG22/Understanding/focus-appearance) — Make keyboard focus visible with sufficient area and contrast.
22. [USWDS Color Tokens](https://designsystem.digital.gov/design-tokens/color/overview/) — Choose semantic colors with contrast implications in mind and never depend on color alone.

### Information And Data Visualization

23. [IBM Design Language: Data visualization basics](https://www.ibm.com/design/language/data-visualization/design/basics/) — Give an overview first, details on demand, keep essential information visible, and use motion to clarify relationships.
24. [USWDS Data Visualizations](https://designsystem.digital.gov/components/data-visualizations/) — Communicate one central idea, limit simultaneous concepts, use color carefully, and provide a nonvisual equivalent.
25. [Four Experiments on the Perception of Bar Charts](https://pubmed.ncbi.nlm.nih.gov/26356929/) — Aligned and adjacent bars support more accurate comparison than stacked or separated encodings.
26. [Effect of Three-Dimensional Bar Charts on Visual Perception](https://jds-online.org/journal/JDS/article/1367/file/pdf) — Added dimensionality can reduce quantitative accuracy; reserve 2.5D depth for interaction feedback rather than value encoding.

### Scheduling And Preview Patterns

27. [YouTube: Video previews](https://support.google.com/youtube/answer/7074781?hl=en) — A passive preview helps users judge content before navigation; adapt this pattern for reversible schedule previews.
28. [Google Calendar: Check availability across calendars](https://support.google.com/calendar/answer/16287054?hl=en) — Combine calendars, preview availability, and automatically suppress conflicts before asking for a booking choice.
29. [Google Calendar: Create an appointment schedule](https://support.google.com/calendar/answer/10729749?hl=en) — Establish duration and availability first, then progressively expose exceptional scheduling settings.
30. [Microsoft Outlook: Scheduling Poll voting](https://support.microsoft.com/en-us/outlook/scheduling-poll-voting) — Show the user's availability, others' votes, counts, preference states, and details at the same decision point.
31. [Microsoft Outlook: Create a Scheduling Poll](https://support.microsoft.com/en-us/outlook/create-a-scheduling-poll-in-outlook-for-windows) — Rank suggestions using required and optional attendee availability and reveal deeper conflict detail on demand.
32. [Microsoft Outlook: Auto scheduling](https://support.microsoft.com/en-us/outlook/auto-scheduling-in-scheduling-poll-for-new-outlook) — Resolve consensus for required attendees first, then optional attendees, with deterministic tie-breaking and automatic completion.
33. [Microsoft Outlook mobile: Scheduling Assistant](https://support.microsoft.com/en-us/outlook/how-do-i-use-the-the-scheduling-assistant-to-find-meeting-times) — Use a clear all-available state and direct manipulation while retaining a simpler selection route.
34. [UI UX Pro Max Skill](https://github.com/nextlevelbuilder/ui-ux-pro-max-skill) — Use its searchable product, style, color, typography, motion, UX, chart, and stack databases to generate design candidates, then filter them through user goals, existing conventions, and evidence-based usability constraints.

## Pattern Decisions

### Keep Information On One Screen When

- the information is required for comparison
- the action is frequent and reversible
- changing screens would make users remember prior state
- the data can remain legible through aggregation and hierarchy

Do not force one-screen density when it causes illegible text, hidden actions, or inaccessible interaction. Use a stable side panel or pinned overlay for details while preserving the overview.

### Use Progressive Disclosure When

- a control is infrequent, advanced, or exceptional
- the default is safe and reversible
- the hidden detail is not needed to trust the current recommendation
- disclosure is clearly labeled and retains context

Do not hide errors, conflicts, costs, selected state, or irreversible consequences.

### Represent Aggregated Schedules

- Use a shared aligned time axis.
- Give `other participants' combined commitments`, `my commitments`, `votes`, and `recommended availability` separate marks or layers.
- Use bar height for one quantitative variable only and label its denominator, for example `6/10 busy`.
- Keep existing commitments visually distinct from selectable free time.
- Let hover or focus identify contributors without adding one permanent row per person.
- Use aligned two-dimensional geometry for comparison; subtle 3D lift may indicate hover or selection only.

### Validate Aesthetic Quality

Ask whether the screen remains understandable in grayscale and without motion. Check optical alignment, rhythm, typography, density, state contrast, and consistency before adding decoration. A polished operational UI should feel quiet until action or exception demands attention.
