# Initial courseware inventory

Reviewed on 26 October 2026. This is a candidate inventory, not a list of finished modules. The [structured inventory](courseware-candidates.yaml) records source locations, evidence status, limitations, proposed classifications and potential outputs. Its JSON-compatible YAML syntax is intentionally conservative and can be parsed as YAML 1.2 or JSON.

| Candidate | Resource | Development status | Domains | Proposed type | Proposed pathways | Level |
|---|---|---|---|---|---|---:|
| EU-CAND-0001 | Surveilling Nature | partially-developed-reported | EU-01, EU-02, EU-03, EU-04, EU-07 | Full Programme | Introductory, Technical, Research | 3 |
| EU-CAND-0002 | GIS and Remote Sensing | partially-developed-reported | EU-03, EU-04, EU-07 | Full Programme | Introductory, Technical, Applied | 3 |
| EU-CAND-0003 | Ecological Interactions master's seminar | scope-only | EU-01, EU-05, EU-08 | Teaching Module | Advanced, Research | 4 |
| EU-CAND-0004 | Course Technical Components | scope-only | EU-02, EU-07 | Teaching Module | Technical | 3 |
| EU-CAND-0005 | Four Ways of Seeing Green | partially-developed-reported | EU-04, EU-07 | Teaching Module | Technical, Applied | 3 |
| EU-CAND-0006 | rgb_to_grvi_video | existing-software-needs-teaching-adaptation | EU-02, EU-04, EU-07 | How-to | Technical, Applied | 3 |
| EU-CAND-0007 | rgb_to_exg_video | existing-software-needs-teaching-adaptation | EU-02, EU-04, EU-07 | How-to | Technical, Applied | 3 |
| EU-CAND-0008 | conir_to_ndvi_image | existing-software-needs-teaching-adaptation | EU-02, EU-04, EU-07 | How-to | Technical, Applied | 3 |
| EU-CAND-0009 | Compare GRVI and ExG under controlled display settings | proposed-future-component | EU-04, EU-07 | How-to | Technical, Applied | 3 |
| EU-CAND-0010 | Reproducible vegetation-index processing record | proposed-future-component | EU-02, EU-04, EU-07 | How-to | Introductory, Technical | 2 |

## Evidence and gaps

The three computation repositories were inspected through their main README, methods-documentation placeholder and principal implementation source. Software was not executed. Their source locations are recorded as local audit evidence, not public catalogue URLs. No dataset, source revision or reuse licence was verified.

The existing Understanding umbrella names Surveilling Nature and Ecological Interactions Seminar, but contains no teaching materials. Supplied planning context reports previous course development for Surveilling Nature, GIS and Remote Sensing and Four Ways of Seeing Green. It is evidence of planning history, not a substitute for inspecting those documents.

The project's local sources directory was empty. Two searches for named course materials returned no results; this does not establish that those materials do not exist. Previously reported slides and documents must be recovered or supplied before extraction or educational review. The provided Actions screenshot was accessible as an image-file record with extracted interface text; it informs interface organisation, not course content.

## Reuse priorities

1. Author a common preparation and interpretation component for the existing image-processing tools.
2. Develop separate GRVI and ExG how-to resources, retaining their distinct formulas and assumptions.
3. Review the CONIR sensor/channel assumptions before describing its result as a standard ecological measurement.
4. Recover the named course documents and inspect actual sections before breaking them into modules.
5. Build the four-index comparison only after appropriate VARI and GLI sources and implementations are available.

All proposed difficulty levels refer to the intended adaptation. Larger programmes may contain activities at multiple levels; their overall level indicates required preparation and complexity, not a uniform difficulty for every activity. Potential outputs are authoring proposals rather than verified existing artefacts.
