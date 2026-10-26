# Courseware architecture — Phase 1

Status: proposed architecture, version 0.1.0, 26 October 2026. No website changes are included.

## Purpose and authority

Ecological Understanding connects research, methods, education and applied practice through reusable resources. The existing Understanding umbrella repository should own the framework, domain definitions, component descriptions and programme assemblies. Independent courses and software remain in their own repositories. Knowledge bases retain authority over their references and classifications.

The public README introduces the framework. Domain pages explain scope and opportunities. Component records describe actual resources. Programme records express ordered assemblies. Inventory candidates record what may be reusable without pretending that it is approved courseware.

## Classification rules

| Dimension | Cardinality | Rule |
|---|---|---|
| Framework functions | One or more | Purpose served; do not infer from content type. |
| Domains | One or more | EU-01–EU-10; IDs do not encode teaching sequence. |
| Content type | Exactly one | Choose Research, How-to, Teaching Module, Full Programme or Application. |
| Pathways | One or more | Audience trajectory or mode; independent of difficulty. |
| Difficulty | Exactly one | Integer 1–5, accompanied by a rationale. |
| Audiences | One or more | Describe intended participants rather than equating professional role with ability. |

Use stable resource IDs such as EU-C-0001 for all resource types, including full programmes. Do not encode domain, pathway or difficulty in resource IDs. Never recycle IDs. The candidate inventory uses EU-CAND-0001-style IDs and is deliberately separate from the authored catalogue.

Difficulty guidance: Level 1 introduces vocabulary and guided observation; Level 2 follows a defined basic procedure; Level 3 combines methods and interprets outputs; Level 4 designs or critically evaluates complex workflows; Level 5 develops or evaluates specialist research methods. These are local editorial descriptors, not accredited qualification levels. A research-themed resource can still be introductory.

## Authored resources

Use YAML front matter in Markdown. JSON Schema validates the parsed metadata object. It does not validate Markdown prose. Store one canonical resource record and assign multiple domains rather than copying a file into each domain directory. Use content/ as a field name only when necessary; the Markdown body already carries authored content.

Each record includes questions, objectives, tasks, outputs, prerequisites, related resource IDs, source provenance and audiences. Empty lists are permitted where a field is inapplicable, but editorial validation requires at least one research question or learning objective and at least one expected output. Prerequisites can state knowledge or equipment without inventing IDs for resources that do not yet exist.

Lifecycle status is independent of difficulty: outline → draft → reviewed → published, with archived available for retired records. Reviewed requires a review date; published requires a review date and publication URL. These labels express workflow status, not scientific certification. Keep proposed candidates out of the default public catalogue until an actual resource record is authored and reviewed for display.

## Reuse and programme assembly

Resources can be local Markdown or descriptions of external resources. Record location, source path and exact source version where available. Unknown licence or uninspected source version must remain explicit. Linking does not grant redistribution permission.

A Full Programme uses the same metadata schema and adds a programme object containing ordered resource IDs, exact resource versions, required/optional flags and contextual adaptation notes. The assembly may use the same component at different stages. An application is a resource documenting a situated use; a programme is an assembly, even when it ends in an application.

Prerequisites express dependencies, related modules express association, and programme entries express sequence. The graph checker must detect unresolved IDs, self-dependencies, prerequisite cycles and recursive programme inclusion. The schema alone cannot check these cross-file relationships. Do not infer that any domain order is mandatory.

Programme adaptations record place, audience, duration and evaluation requirements without overwriting a component's general instructions. A material change in objectives, method or outputs should create a separately versioned adaptation and preserve its source relationship. A programme release pins resource versions; the website publication additionally pins the source repository commit.

## Catalogue and publication

Generate a lightweight JSON index from approved Markdown metadata at build time. It is a derived artefact, not a second manually edited register. Inventory records and component templates are excluded. Validate identifiers, enums, links, source versions and graph relationships before generation. Draft preview can display status badges; the published catalogue should show explicitly allowlisted resources.

Maintain the existing /understanding/ route. Import the source README as understanding/index.md and domain pages as understanding/domains/.... Translate repository-relative README links at publication, without changing source prose. The website's existing placeholder must be removed or excluded when the generated route is introduced.

Use the established commit-pinned, checksum-allowlisted publication model. A separate, explicit local-only preview path can read working-tree drafts without updating production pins. Hosted builds must reject draft-preview mode. Public fetching cannot be configured until the Understanding repository identity and source accessibility are verified.

## Federation boundaries

EU domain identifiers do not replace EII, OSDS or other database taxonomies. Use qualified external identifiers only when the corresponding record has been inspected. Otherwise record a repository or source reference without inventing a relationship to a specific entity. DRM is developing registry and governance infrastructure; IRKB is the developing synthesis direction. Courseware teaches and applies these resources without becoming their canonical data store.

## Phase 1 limits

The schema is proposed and the template is synthetic. No components or full programmes have been declared complete. No new academic bibliography, accreditation, licensing grant, database integration or frontend feature has been established. The current package is a review draft for later repository integration.
