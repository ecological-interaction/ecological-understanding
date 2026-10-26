# Repository integration and implementation plan

## Source and destination

Draft source: this review package. Intended repository: /Users/jonathan/Github/ecological-understanding/ecological-understanding. Website repository: /Users/jonathan/Github/ecological-interaction.github.io. These repository paths were readable but outside this session's writable roots; the review package does not modify them.

## Stage 1 — Review and source integration

Review the README, domain scopes, metadata choices and inventory. In a Codex workspace authorised to edit the source repository, inspect applicable AGENTS.md instructions and Git status again. Integrate approved files with a diff; replace README deliberately, preserve PROVENANCE.md unchanged and do not overwrite unrelated material. The package's REVIEW.md is a handover document, not necessarily a public page. Do not copy its ZIP or validation report into the public documentation.

The outer ecological-understanding directory is organisational; its ecological-understanding child is the existing Git repository. Do not initialise an additional repository or move existing independent projects.

## Stage 2 — Metadata and first resources

Review schema version 0.1.0 and taxonomy values. Use a declared YAML parser and JSON Schema validator in a reproducible development environment. Parse YAML safely and reject duplicate keys. Register IDs only when creating actual resource records. Convert verified candidates into authored components without relocating source code or claiming educational review prematurely. Document licence and source versions. Preserve unknowns rather than manufacture values.

Validate required fields, enums, dates, URLs, unique IDs, local paths, ordered assemblies and cross-file relationships. Check that the template and candidate inventory are excluded from the catalogue. Reject missing programme members, version mismatches, prerequisite cycles and recursive programme inclusion. Missing candidate materials remain an explicit limitation; source recovery may proceed separately.

## Stage 3 — Local website publication preview

Inspect website navigation tests and import conventions before editing. Keep /understanding/ stable. Add a scoped Understanding importer and explicit allowlist covering README and the ten approved domains. Remove the existing placeholder route when enabling the generated index. Rewrite repository-relative README and domain links to valid MkDocs destinations; test both source links and published links.

Provide local-only working-tree preview for uncommitted review drafts without silently falling back from a failed pinned import. Hosted builds must reject this mode. Add the ten domains beneath an Understanding section using the existing unlabelled index pattern. Do not change Information navigation or publication pins.

## Stage 4 — Catalogue enhancement

After actual component records exist, generate static resource links and a derived JSON index from validated metadata. Implement scoped search, filters and cards according to the specification. Keep the catalogue usable without JavaScript and preserve the existing navigation accessibility code. Programme construction remains a later feature.

## Stage 5 — Checks and review

Run focused metadata, graph, link and importer checks, then the website's established unittest suite and strict MkDocs build in its existing environment. Review /understanding/ and all ten domain pages in local preview. Check desktop and narrow layouts, keyboard access, filter combinations and empty states if the catalogue enhancement is included. Repeat broader checks only when changes or failures justify them.

Existing website commands, to run only in the authorised implementation workspace:

```sh
uv run python -B -m unittest discover -s tests -v
uv run mkdocs build --strict
uv run mkdocs serve --dev-addr 127.0.0.1:8000
```

## Stage 6 — User-managed publication

Present final diffs and preview evidence for review. Do not commit, push or deploy. The user will use GitHub Desktop. After an approved source commit exists, separately prepare the website publication manifest with the exact source commit, checksums and confirmed remote identity. A source push alone will not update the website. Website main pushes currently trigger deployment, so keep publication changes unpushed until the user chooses to publish.

## Suggested Codex handover instruction

> Integrate the approved Ecological Understanding Phase 1 review package into the existing ecological-understanding repository. Inspect current instructions and Git status first. Preserve historical provenance and unrelated changes. Do not commit, push or deploy. First show the source diff and validate metadata and links. Then implement a local-only MkDocs preview in the website repository using the approved publication plan; preserve existing routes and Information imports. Present the completed preview and any unresolved issues for review before preparing production publication pins.
