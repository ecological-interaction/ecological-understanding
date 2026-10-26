# Metadata authoring guide

The [JSON Schema](metadata.schema.json) describes the object parsed from YAML front matter in a resource Markdown file. It is proposed version 0.1.0, not an existing DRM standard. Domain pages and candidate inventory records use separate document shapes and must not be validated as components.

## Minimum record and field meanings

Start with the [component template](component-template.md). Replace its reserved ID, placeholders and dates. Quoted dates remain strings in YAML parsers. Use safe parsing and reject duplicate keys. Do not parse or execute custom YAML tags.

| Fields | Meaning |
|---|---|
| schema_version, id, version | Metadata contract, permanent resource identity and resource revision. |
| title, summary, status | Display description and editorial lifecycle. |
| functions, domains, content_type, pathways | Independent classifications with controlled values. |
| difficulty.level, difficulty.rationale | Required complexity, integer 1–5, with a specific justification. |
| research_questions, learning_objectives | Questions investigated and observable learning aims; at least one list must contain an item. |
| practical_tasks, expected_outputs | Activities and their resulting artefacts or findings. Outputs cannot be empty. |
| prerequisites | Knowledge, skill, equipment or resource dependencies; resource dependencies require a registered ID. |
| related_modules | Associative resource links, not prerequisites. |
| source_references | Attributed sources, locations, versions, access dates, inspection and reuse status. |
| intended_audiences | Participants for whom the resource was designed. |
| resource_location | Local repository-relative Markdown path or external HTTPS resource URL. |
| estimated_hours | Positive workload estimate or null when not established. |
| language, authors, licence | Language tag, attribution and an explicit licence identifier or statement; null means unresolved. |
| created, updated, reviewed_on, publication_url | Editorial dates and publication state. Dates and URLs require format-aware validation. |
| programme | Ordered, versioned assembly; required only for Full Programme records. |

Empty questions or tasks may be appropriate for some outlines, but must be checked during review. A licence string should cite an actual licence; unknown permission must not be represented as an open licence. An inspected software source still needs a version pin and teaching adaptation review before publication.

## Programme example

[programme-example.yaml](programme-example.yaml) is a synthetic schema example, not a real programme or catalogue entry. It deliberately references a not-yet-registered component so the future graph checker must reject it for publication until a real member and matching version exist. It shows how sequence and versioning differ from domains, prerequisites and difficulty.

## Validation responsibilities

JSON Schema checks field shapes, enums and conditional requirements. Enable date and URI format checking explicitly in the chosen validator. Repository validation additionally checks unique IDs, reserved IDs, local-path containment, HTTPS external targets, source-version resolution, lifecycle dates, declared licences and relationship graphs. Remote references must never trigger arbitrary code execution or automatic remote schema loading.

The schema cannot itself confirm factual accuracy, source permission, completion, prerequisite suitability or whether a programme member actually exists. A reviewed or published label requires an editorial decision as well as valid syntax. Unknowns in the candidate inventory remain permissible because it is an evidence-gathering register, not the published catalogue.
