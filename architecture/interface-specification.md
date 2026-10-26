# Catalogue interface specification

Status: design specification only; no CSS, JavaScript or website navigation has been changed.

## Reference and intent

The supplied Screenshot 2026-10-26 at 17.50.50.png was accessible through its image-file record and extracted interface text. It shows GitHub Actions' introductory heading, workflow search, grouped sections and cards containing titles, provider attribution, descriptions and actions. No pixel-precise visual recreation has been performed. Use this organisational pattern, with package-style version and provenance information, rather than reproducing GitHub branding or deployment language.

## Page composition

1. Heading: Ecological Understanding, followed by a concise framework introduction and links to its research scope and domain directory.
2. Four functions: short explanations or links that also provide entry points into the catalogue.
3. Prominent search field labelled Search resources, with a clear control and live result count.
4. Filters for domain, function, content type, pathway and difficulty; visible active selections and Clear filters.
5. Catalogue grouped by domain, with a short group description and View domain link.
6. Cards with resource title, summary, domain assignments, function, content type, pathways, difficulty, development status, estimated duration where known, source attribution and Open resource link.
7. Future programme assembly area, introduced only when functional.

Do not use Configure as the resource action. Do not display an active Add to programme control before an assembly feature exists. Resource status should be visible, especially in draft previews. Proposed inventory candidates do not become public cards automatically.

## Search and filter behaviour

Search titles, summaries, domain labels, objectives and audience terms. Match text case-insensitively; multiple query terms must all occur somewhere in those fields. Filters combine with AND across dimensions and OR within a dimension. For example, choosing Technical and Applied pathways includes either, while choosing Level 3 additionally restricts difficulty.

One component remains one identity even when assigned to several domains. In grouped view it may be represented in each matching domain group, but count unique results and use a shared selection state. A flat results view should show each resource once. State the grouping rule beside the result count when duplication occurs.

All controls update the count and results together. Provide a no-results message with Clear filters. Preserve selections in URL query parameters so views can be shared; define parameter names when implementation starts. Treat source text as text, not HTML. No account, tracking or server database is needed for the initial catalogue.

## Responsive layout and accessibility

Use the existing Material page width. A desktop grid may use two or three columns according to available space, reducing to one column on narrow screens. Filters wrap or expand in a labelled panel; do not require horizontal scrolling. Keep the main website navigation and existing accessibility enhancement intact.

Use native labelled inputs, selects, checkboxes and anchors. Group filters with fieldsets and legends. All controls and cards must be keyboard usable, with visible focus and sufficient contrast. Announce result-count changes with a polite live region without moving focus. Use text labels alongside colours; avoid nested interactive card elements or clickable containers that obscure the resource link.

## Progressive enhancement and MkDocs integration

The base page must contain usable domain and resource links without JavaScript. The initial foundational site may show domain cards and an honest catalogue-development notice before reviewed component records exist. Do not use invented resources to fill the grid.

Later generate a catalogue JSON index and static resource links from validated source metadata. Scoped CSS and JavaScript enhance only the Understanding catalogue. Do not alter Material theme templates or Information page styling unless a verified requirement emerges. No current plugin provides these custom filters automatically.

## Future programme assembly

A later builder can select resource IDs, order activities, check prerequisites and export a programme definition. It must show exact versions, optional activities, context adaptations, workload and unresolved requirements. Local selection can precede any persistence design, but saving and sharing behaviour require a separate scope decision. Level alone cannot establish that a learner has met prerequisites.

## Acceptance criteria for implementation

- Every visible resource resolves to a real reviewed record or explicitly labelled draft in local preview.
- Combined filtering, clearing, unique counts and empty states follow the defined rules.
- Search and filters work with keyboard input and on a narrow viewport.
- Without JavaScript, meaningful domain and resource links remain available.
- Existing Information routes and navigation behaviours remain unchanged.
- Draft-only records and local source paths cannot leak into the hosted catalogue.
- Programme assembly controls appear only after their behaviour is implemented and reviewed.
