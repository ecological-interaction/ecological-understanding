# Historical research provenance

## Purpose

This record documents the relationship between research material
historically committed in Ecological Understanding and its current
locations in EIRKB.

It preserves the distinction between unchanged file migration and
revised documentation. It does not rewrite history or establish
duplicate current authorities.

## Repository identities

Original repository:

- Historical local path:
  `/Users/jonathan/Github/ecological-understanding`
- Current local path:
  `/Users/jonathan/Github/ecological-understanding/_umbrella`
- Configured remote: `https://github.com/Jonathan-Minchin/ecological-understanding.git`
- Live remote existence and accessibility remain unverified.

Current research repository:

- Local path: `/Users/jonathan/Github/ecological-information/EIRKB`
- No remote is configured.
- Initial commit: `3462f2571a8343287084e5deab0913b1acc74f43`

## Historical commits

| Commit | Change |
|---|---|
| `3d3e4b6f0f9f385c56405d4347ff88ccec7e8844` | Added `.gitattributes` and the original historical narrative |
| `a1c60c9bc0673d0cf5a3bed0901ed6198641eb63` | Added the initial README |
| `099b27836b3ad5093af4b0bf8cab964563dad415` | Updated the historical narrative |
| `f3e55cf2e0db80a710adc4866172bb72319284f6` | Added the V0 reference register |
| `2bdef1a3c6a9ca8268e539b294921e00771645a6` | Added citation and knowledge architecture protocol v1.2 |

All four original documents are present at historical commit
`2bdef1a3c6a9ca8268e539b294921e00771645a6`.

## File relationships

Paths in the original-path column are relative to the original
Understanding repository. EIRKB destinations are relative to EIRKB.

| Original path | Relevant original commit | Current destination | Relationship |
|---|---|---|---|
| `MASTER_history_theory_ecological_information_v0.md` | Introduced at `3d3e4b6`; last updated at `099b278` | `MASTER_history_theory_ecological_information.md` | Unchanged content; renamed path |
| `ecological_information_complete_reference_register_V0.xlsx` | Introduced at `f3e55cf` | `registers/ecological_information_complete_reference_register_V0.xlsx` | Unchanged content; moved into registers |
| `REFERENCE_CITATION_README_v1.2.md` | Introduced at `2bdef1a` | `README.md` | Historical predecessor of revised v1.3 documentation; not an identical migration |
| `README.md` | Introduced at `a1c60c9` | Understanding's replacement `README.md` | Obsolete placeholder replaced by educational domain documentation; no EIRKB successor |

The narrative and V0 register destinations are recorded in
`/Users/jonathan/Github/ecological-information/REORGANISATION.json`.
Their content equality was independently verified.

That manifest records migration from an ordinary Information directory;
it is not a complete account of the earlier Understanding Git history.
This document records the additional historical relationship.

## Checksums

Checksums are SHA-256 over exact file bytes.

### Historical narrative

Original at `2bdef1a` and current EIRKB destination:

`5d7d51bb6a5969f489c9b3ccdb9ef7c24c99e150a22fb996fdcd74a5371a81fe`

### V0 reference register

Original at `2bdef1a` and current EIRKB destination:

`a43d1c226b8cc339ca8a69c3925a41c7f13140748a6b339781233d81dca093be`

### Historical citation protocol v1.2

Original at `2bdef1a`:

`66cf5a368b15664acf66073d6eba0e0b05198a28150b38fb595c1fab0988c662`

Current EIRKB README at `3462f25`:

`1165df5483a9fee131117f505cbff6b987785e639b12949c5ac2599ab3101cdd`

These documents differ. The current README records consolidation from
v1.2 into v1.3, including adoption of SQLite as the planned canonical
structured store, CSV exchange, and additional staging, review and
interoperability guidance.

The predecessor relationship is supported by that change record and
content comparison. It is not represented as an unchanged file move.

### Original Understanding README

Original at `2bdef1a`:

`6f194a96c556a603775ac3bbbe340ef641bc395d24288331d72587c4a2e330f4`

Its content was the placeholder “initial readme creation”.
Its historical version remains preserved.

## Preservation and recovery

Verified pre-migration snapshot:

`/Users/jonathan/Backups/Ecological-Interaction/2026-10-12-pre-migration-152545/`

The snapshot contains:

- The complete original Understanding working tree and Git metadata.
- All original commits and references.
- Separate exports of the four historical documents under
  `historical-understanding/`.
- Checksums, repository states and recovery instructions under
  `verification/`.

The exported documents were verified against commit
`2bdef1a3c6a9ca8268e539b294921e00771645a6`.

No existing Git history has been rewritten. The authoritative research
files remain in EIRKB; the original versions remain available through
Understanding's history and the snapshot.

External Dropbox research datasets were not included in this snapshot
and remain a separate unresolved backup requirement.
