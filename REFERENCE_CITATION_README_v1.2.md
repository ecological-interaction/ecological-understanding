# Ecological Information Research Knowledge Base
## Reference, Citation and Knowledge Architecture Protocol

**Acronym:** EIRKB  
**Version:** 1.2
**Status:** Finalized project protocol
**Date:** 2026-10-01  
**Canonical structured format:** CSV  
**Human tabular interface:** XLSX  
**Intellectual narrative:** Markdown  
**Future semantic formats:** JSON-LD / RDF  
**Scope:** History and Theory of Ecological Information and subsequent situated ecological technology research

---

## 1. Purpose

The **Ecological Information Research Knowledge Base (EIRKB)** is a research knowledge-organization protocol for recording and relating the literature, people, concepts, fields, methods, ecological phenomena, observations, places and technologies investigated through this research.

It serves two complementary purposes.

Academically, it provides a transparent means of organizing an interdisciplinary literature that cannot adequately be represented through a single chronological, disciplinary or bibliographic hierarchy.

Computationally, it provides stable identifiers, controlled classifications and explicit relationships from which timelines, reference registers, conceptual maps and eventually a semantic knowledge graph or ontology can be generated.

EIRKB does **not** replace conventional academic citation systems, library classifications or persistent scholarly identifiers. It supplements them with a project-specific analytical layer.

---

## 2. Research rationale

The research spans ecology, information theory, cybernetics, biosemiotics, environmental monitoring, Earth observation, industrial ecology, ecological economics, ecological design and related spatial and technological studies. A resource may participate in several fields and historical or theoretical contexts simultaneously.

Technology assessment likewise depends on situated ecological conditions, scale, materials, infrastructure, skills and cultural and economic conditions. Faceted classifications and explicit relationships preserve these intersections while keeping scholarly evidence distinct from the project's synthesis. This is a defensible research organization method, not a claim to a universal library classification or ontology.

Its fundamental principle is:

> **Stable entities, extensible metadata, multiple classifications, explicit relationships and traceable evidence.**

---

## 3. What EIRKB records

Every record separates five kinds of information.

### Identity

What is the thing?

`T0032`

### Metadata

What do we know about it?

Technology type, description, date, source, etc.

### Classification

Where does it participate within the research?

`HA`, `IL`, `IM`, scale, system domain, etc.

### Relationship

How does it connect to another entity?

`T0032 → uses-process → C0142`

### Provenance

Why is that relationship asserted?

Documented literature, inference, or project interpretation.

Therefore:

> **Identity → Metadata → Classification → Relationship → Provenance**

---

## 4. Entity architecture

EIRKB distinguishes between **Core Research Entities** and **Extended Research Entities**.

This distinction concerns implementation priority rather than ontological importance.

### 4.1 Core Research Entities

These should be maintained from the beginning.

| Prefix | Entity | Example |
|---|---|---|
| `R` | Resource | journal article, book, report |
| `P` | Person | Gregory Bateson |
| `C` | Concept | Umwelt |
| `O` | Organization | Earth Commission |
| `F` | Field | Industrial Ecology |
| `M` | Method | Material Flow Analysis |
| `IND` | Indicator/framework | HANPP |

These primarily organize the scholarly and conceptual knowledge base.

---

## 5. Extended Research Entities

The following entity classes are formally reserved within EIRKB v1.2.

They need not all be comprehensively populated immediately.

| Prefix | Entity | Example |
|---|---|---|
| `PL` | Place | Terres de l'Ebre |
| `T` | Technology | Anaerobic digester |
| `PH` | Ecological phenomenon | Soil respiration |
| `I` | Instrument | Multispectral camera |
| `DS` | Dataset | Sentinel-2 imagery |
| `PR` | Project/program | EuropaBON |

These entities are particularly important for the later transition from **history and theory** toward **situated ecological technology and productive inference**.

---

## 6. Why Place and Technology are first-class entities

Place and technology have stable entity records because they will participate directly in the future ontology. A place may relate to climate, soils, hydrology, land use, ecological phenomena, infrastructure, datasets and indicators. A technology may relate to inputs, outputs, energy and water requirements, skills, scale, effects and applicable methods.

Illustrative relationship forms include:

```text
PL0007 → exhibits → PH0041
IND0031 → indicates → PH0041
I0012 → measures → IND0031
DS0001 → contains-observations-of → PL0007
T0032 → requires → C0142
T0032 → affects → PH0041
T0032 → suitable-for → PL0007
```

These are schema illustrations, not verified claims. A material requirement or condition can be represented by a concept when appropriate; `R` means a scholarly resource, not a physical material input. Technology–place suitability is an assessment requiring evidence and provenance, rather than a property assumed from a technology label.

---

## 7. Extensibility rule

Additional entity classes may be introduced when:

1. the entity occurs repeatedly;
2. relationships to it are analytically important;
3. representing it merely as text would lose meaningful structure.

A new entity type should not be introduced merely because something can be classified.

This prevents unnecessary ontological complexity.

Existing identifiers must never be restructured simply because new entity classes are introduced.

---

## 8. Stable identifiers

Every entity receives a unique immutable local identifier.

Examples:

`R0001`  
`P0001`  
`C0001`  
`PL0001`  
`T0001`  
`PH0001`

The prefix identifies the entity class; the numeric suffix is **non-semantic**. Use the registered uppercase prefix followed by a sequential integer padded to at least four digits (for example, `IND0001` or `PR0001`). Retain IDs as text, preserve leading zeros and allocate numbers independently within each class.

Do not encode:

- dates;
- disciplines;
- geographic location;
- author;
- intellectual classification

inside an entity ID.

For example:

**Preferred**

`T0032`

**Avoid**

`CAT-BIOGAS-2026-03`

because classifications and interpretations can change.

---

## 9. Record lifecycle

Identifiers must never be reused.

Records may have status:

`active`

`deprecated`

`duplicate`

`superseded`

A deprecated record should retain its ID.

Where appropriate:

`superseded_by = T0048`

This maintains referential integrity across documents and datasets.

---

## 10. Scholarly metadata

Resource metadata should remain compatible where practical with **Dublin Core Metadata Terms** and conventional bibliographic systems.

Core resource fields include:

- ID;
- title;
- creator;
- date;
- type;
- publisher;
- subject;
- description;
- language;
- source;
- external identifier.

Project-specific fields may extend these. Dublin Core compatibility means documenting field mappings, not claiming complete conformance: `title`, `creator`, `date`, `publisher`, `subject`, `description`, `language`, `source` and resource `type` align with the corresponding terms; local IDs and external identifiers map to `identifier`. Entity class in `entities.csv` is distinct from bibliographic resource type.

EIRKB does not attempt to reproduce an entire library cataloguing standard.

---

## 11. External identifiers

Where available, retain established persistent identifiers.

Examples include:

| Identifier | Use |
|---|---|
| DOI | scholarly object |
| ISBN | book |
| ISSN | journal |
| ORCID | researcher |
| ROR | research organization |
| URI/URL | online resource |

The local EIRKB ID supplements rather than replaces these identifiers. Store DOI, ISBN, ISSN, ORCID and ROR as text in separate fields; retain URI/URL values where available. A URL is a locator and is not necessarily persistent.

---

## 12. Academic citation

EIRKB is **not a citation style**.

The thesis and publications should use the citation style required by the relevant institution or publisher.

For example:

**(McHarg, 1969)**

may correspond internally to (illustrative ID):

`R0073`

These identifiers serve different purposes.

Reference-management interoperability with Zotero, CSL and BibTeX should be maintained where practical.

---

## 13. Temporal metadata

Dates are stored separately from identifiers.

Relevant temporal information can include:

### People

birth  
death  
active period

### Resources

publication date  
edition date

### Concepts/frameworks

date  
temporal role

Controlled temporal roles may include:

`precursor`

`first-formulation`

`named`

`formalized`

`operationalized`

`major-publication`

`later-development`

These fields should be used where historically meaningful rather than mechanically completed for every entity. Store dates as text: `YYYY`, `YYYY-MM` or `YYYY-MM-DD` when known. Do not invent month or day values. Retain uncertain dates and BCE dates explicitly with a documented notation, rather than forcing them into spreadsheet dates; document any later EDTF mapping.

---

## 14. Primary project analytical classifications

The research currently uses three principal analytical structures.

These are **research constructs**, not claimed universal classifications.

### `HA` — Historical Arc

Diachronic.

> How have ways of perceiving, measuring and using ecological information developed through time?

Example:

`HA01 — Nature as signs — observation before instrumentation`

---

### `IL` — Intellectual Lineages

Genealogical and theoretical.

> What ideas and questions connect thinkers and disciplines across time?

Example:

`IL01 — Organisms perceive informational worlds`

---

### `IM` — Intellectual Map

Synchronic and thematic.

> What knowledge territories constitute the research?

Example:

`IM-A4 — Umwelt and perceptual worlds`

Existing HA, IL and IM identifiers form a **frozen conceptual checkpoint**.

Their existing codes and meanings must be retained. Use `HA01`, `IL01`, `IM-A` and `IM-A4` forms as registered; do not convert HA/IL to hyphenated codes or remove the hyphen from IM. Examples here do not redefine the full approved classification registers. Add categories under new unused codes; substantial revisions require explicit old-to-new mappings and a versioned change record.

---

## 15. Auxiliary analytical dimensions

Three additional dimensions are maintained because they recur across the research.

### Scale — `SC`

Initial controlled vocabulary:

`SC-ORG` — organism  
`SC-SITE` — site  
`SC-LAND` — landscape  
`SC-REG` — regional  
`SC-GLOB` — planetary

Additional scales may be introduced when required.

---

### System Domain — `SD`

Initial examples:

`SD-ATM` — atmosphere  
`SD-BIO` — biological/biotic  
`SD-SOIL` — soil/rhizosphere  
`SD-SUB` — subsurface  
`SD-HYD` — hydrological  
`SD-SOC` — socioeconomic  
`SD-TECH` — technological

Multiple domains are permitted.

---

### Epistemic Mode — `EP`

This dimension records how ecological knowledge is obtained.

`EP-OBS` — direct observation  
`EP-MEAS` — direct measurement  
`EP-PROXY` — proxy  
`EP-IND` — indirect measurement  
`EP-MODEL` — model-derived  
`EP-INFER` — inference

This is particularly important to the project's concept of **ecological observability**.

---

## 16. Multiple classification

An entity may belong to multiple categories.

For example:

`R0127`

could simultaneously have:

`HA15`

`IL12`

`IM-D7`

`IM-F1`

`SC-GLOB`

This is expected behaviour.

EIRKB is deliberately **faceted rather than mutually exclusive**. Classification codes are not entity IDs: `C0012` identifies a concept, whereas `IM-A4` identifies a category. Store each membership as its own row in `classifications.csv`; `scheme` is one of `HA`, `IL`, `IM`, `SC`, `SD`, `EP`, and `class_id` must belong to that scheme's controlled register.

---

## 17. Relationships

Relationships use a simple directed structure:

> **subject → predicate → object**

For example:

`P0038 → develops → C0021`

or:

`I0012 → measures → IND0031`

or:

`PH0041 → occurs-in → PL0007`

or:

`T0032 → affects → PH0041`

A controlled predicate vocabulary should be maintained.

Initial predicates can include:

`authored-by`

`develops`

`introduces`

`formalizes`

`extends`

`criticizes`

`influenced-by`

`related-to`

`parallel-to`

`operationalizes`

`uses-method`

`measures`

`indicates`

`occurs-in`

`observed-in`

`derived-from`

`requires`

`produces`

`affects`

`applies-to`

`located-in`

`uses-process`

`exhibits`

`contains-observations-of`

`suitable-for`

`broader-than`

`narrower-than`

New predicates should be introduced deliberately and documented with a definition, direction and intended subject/object classes. For example, `R → authored-by → P` and `P → influenced-by → P` have different directions. Use `related-to` or `parallel-to` for conceptual resemblance where historical influence is unestablished. Reciprocal conceptual relationships may be represented by one row if the vocabulary records that the predicate is symmetric.

---

## 18. Technology–place relationships

The knowledge base must distinguish between **descriptive relationships** and **evaluative or inferred suitability relationships**.

For example:

`T0032 → requires → C0142`

may be documented.

`PL0007 → exhibits → PH0041`

may be observationally supported.

But:

`T0032 → suitable-for → PL0007`

is a much stronger proposition.

It should therefore require explicit evidence and provenance.

This enables productive inference to be represented as:

**Place**

→ ecological conditions

→ phenomena

→ observations

→ indicators

→ ecological inference

→ capacities/constraints

→ technology requirements/effects

→ candidate productive affordances

→ assessment

→ intervention

→ feedback.

The knowledge base therefore supports technology selection without embedding the assumption that technology selection is automatic or deterministic.

---

## 19. Provenance

Provenance is mandatory for significant historical, causal, evaluative or interpretative relationships.

Three initial statuses are used:

### `documented`

Explicitly supported by a primary or reliable secondary source.

### `inferred`

Supported by evidence but not directly stated.

### `project-interpretation`

A relationship proposed as an analytical synthesis or hypothesis through the present research. Use `inferred` for a conclusion drawn from cited evidence that is not explicitly stated there; use `project-interpretation` when the claim is framed as the project's own synthesis. A project interpretation may also use inferential reasoning, but each row records the status that best describes its scholarly presentation.

Example:

```text
subject,predicate,object,evidence,provenance
P0023,influenced-by,P0014,R0087,documented
```

versus:

```text
subject,predicate,object,evidence,provenance
C0041,related-to,C0092,R0121,project-interpretation
```

Record supporting resource IDs in `evidence`, a page, section or other locator in `evidence_locator`, and the reasoning or qualification in `note` where needed. Significant claims require traceable supporting sources; an interpretation must explain its basis even when no source directly states it. A blank confidence value means unassessed. Provenance status describes the basis of a claim, not its truth or certainty; `EP` describes the mode of knowing and is separate from provenance.

---

## 20. Confidence

An optional confidence field may be used:

`high`

`medium`

`low`

It is primarily intended for:

- uncertain historical attribution;
- inferred relationships;
- contested interpretations;
- provisional classifications.

Confidence is qualitative and should not be treated as a statistical probability.

---

## 21. Machine-readable canonical data

The canonical structured representation should initially use **CSV**.

Recommended core tables are:

### `entities.csv`

```text
id,type,label,status,superseded_by
```

### `resources.csv`

```text
id,title,creator,date,edition_date,type,publisher,subject,description,language,source,doi,isbn,issn,uri,url,citation_key
```

### `people.csv`

```text
id,name,birth,death,orcid
```

### `concepts.csv`

```text
id,preferred_label,alternative_label,definition
```

### `classifications.csv`

```text
entity_id,scheme,class_id
```

### `relations.csv`

```text
subject,predicate,object,evidence,evidence_locator,provenance,confidence,note
```

Extended entity tables can be added when required:

### `places.csv`

```text
id,name,place_type,parent_place,external_identifier
```

### `technologies.csv`

```text
id,name,technology_type,description
```

### `phenomena.csv`

```text
id,name,description
```

### `instruments.csv`

```text
id,name,instrument_type,description
```

### `datasets.csv`

```text
id,title,creator,date,spatial_coverage,temporal_coverage,url
```

A `projects.csv` table may use `id,name,description,url` for `PR` records. Core `O`, `F`, `M` and `IND` records may initially use `entities.csv`; add type-specific tables only where metadata requires them.

`entities.csv` is the authoritative identity register for every core and extended entity. Its `type` values are the registered prefixes. Each type-specific table's `id` must reference an entity of the corresponding class. Record lifecycle status belongs in `entities.csv`; avoid duplicating it in other tables. These tables reserve the extended architecture without requiring immediate comprehensive population.

These are explicit baseline headers, not an exhaustive bibliographic schema. Fields may be added under the governance rule; do not silently rename existing columns. Named creator text preserves bibliographic transcription; `authored-by` relationships link to person or organization records where available. The `source` field describes a resource's source context and is distinct from relationship evidence.

---

## 22. CSV conventions

For computational reliability:

- Use UTF-8 and comma-delimited CSV with a single header row, lowercase `snake_case` field names and no merged cells or embedded spreadsheet formulas.
- Apply standard CSV quoting: enclose cells containing commas, quotes or line breaks in double quotes; escape an embedded double quote by doubling it.
- Use one entity per row in entity tables, one classification membership per row in `classifications.csv`, and one directed assertion with its evidence and provenance per row in `relations.csv`.
- Store every identifier as text. Entity IDs must resolve in `entities.csv`; classification IDs must resolve in their scheme's controlled register.
- Use `active`, `deprecated`, `duplicate` or `superseded` for lifecycle `status`. When supplied, `superseded_by` must resolve to an existing canonical entity; do not leave circular redirects.
- Use the exact provenance tokens `documented`, `inferred`, `project-interpretation`. Confidence is optional and, if populated, is `high`, `medium` or `low`.
- For multiple evidence resource IDs supporting the same assertion, separate IDs with `|` in `evidence` (for example, `R0087|R0121`). Every token must resolve to an `R` record. Apply the same documented delimiter to repeatable text fields such as `alternative_label`; use it only in fields explicitly defined as repeatable, and reserve the delimiter from individual values.
- Use separate relationship rows for different objects and separate classification rows for different categories. Do not put lists of object IDs or class IDs in a cell. Different evidence or provenance may justify separate rows for the same subject–predicate–object triple.
- Leave unknown or inapplicable optional values empty; do not invent values or substitute literal `NULL`, `N/A` or zero for missing data.
- Preserve standardized dates as text, controlled spelling and case, and descriptive Unicode text.
- Use stable IDs in linking fields; retain human labels and bibliographic creator text in descriptive fields.
- Validate unique entity IDs, type/prefix agreement, required identity fields, valid controlled values, resolvable links, CSV parsing and exact duplicate rows before release.

The example IDs in this document illustrate syntax only. They must not be imported as factual records without identification and evidence.

---

## 23. Excel Reference Register

The `.xlsx` Reference Register remains the principal **human-readable tabular interface**.

It may contain sheets corresponding to:

References  
People  
Concepts  
Organizations  
Fields  
Methods  
Indicators  
Places  
Technologies  
Classifications  
Relationships

The workbook should derive from or remain synchronized with the canonical CSV records. Validate workbook edits and export them back to CSV before treating an update as authoritative. Preserve IDs and external identifiers as text and prevent automatic date conversion.

It should not establish a second incompatible identifier system.

---

## 24. Master Knowledge Document

The Master Markdown document is the **curated intellectual narrative**.

It contains:

- explanations;
- historical arguments;
- conceptual structures;
- interpretations;
- unresolved questions;
- synthesis.

It is not replaced by the knowledge base.

The distinction is:

> **Markdown explains the knowledge. CSV structures the knowledge. The Reference Register presents the knowledge. The graph connects the knowledge.**

---

## 25. Controlled vocabulary

Labels and predicates should use controlled terminology where possible.

Concept records may include:

`preferred_label`

`alternative_label`

`definition`

and relationships such as:

`broader-than`

`narrower-than`

`related-to`

This maintains conceptual compatibility with SKOS principles without requiring immediate formal implementation of SKOS.

---

## 26. Academic status of assertions

The knowledge base distinguishes three levels.

### External scholarly information

Examples:

publication dates, DOI, documented historical influence.

These should be externally verifiable.

### Established disciplinary terminology

Examples:

Industrial Ecology, Critical Zone Science, Material Flow Analysis.

These should correspond to established scholarly usage.

### Project analytical constructs

Examples:

the HA/IL/IM organization;

the particular synthesis of ecological observability;

Situated Ecological Technology;

Productive Inference.

These should be explicitly identifiable as analytical constructs developed through the research.

EIRKB does not present the project classifications as a universal ontology of ecological knowledge.

---

## 27. Future semantic representation

The data model intentionally approximates the basic graph structure:

**subject → predicate → object**

With explicit vocabulary, URI and provenance mappings, CSV records can later be transformed into:

**JSON**

→ **JSON-LD**

→ **RDF**

→ **semantic knowledge graph**

without replacing the existing local identifiers. This is a future mapping task, not a claim that CSV triples already constitute an RDF ontology. Assign stable namespace URIs that preserve local IDs and represent assertion-level provenance explicitly; JSON is optional, and JSON-LD/RDF remain the future semantic formats.

The eventual graph may connect:

**Person**

↔ **Resource**

↔ **Concept**

↔ **Field**

↔ **Method**

↔ **Indicator**

↔ **Phenomenon**

↔ **Instrument**

↔ **Dataset**

↔ **Place**

↔ **Technology**

↔ **Intervention (future analytical outcome; no additional entity prefix reserved in v1.2)**

The graph can therefore eventually address questions that conventional bibliography cannot.

For example:

> Which technologies have requirements compatible with the measured ecological capacities of a particular place?

or:

> Which indicators and datasets support the inference that those capacities exist?

or:

> What evidence supports the proposed relationship between an ecological condition and a productive intervention?

---

## 28. Research workflow

The preferred lifecycle is:

1. Develop and revise the intellectual argument in the Master Markdown document.
2. Search existing records by ID, external identifier, title, label and creator before allocating a new entity ID.
3. Record standard metadata and external identifiers in the appropriate CSV tables.
4. Assign relevant HA/IL/IM and auxiliary memberships using the controlled registers.
5. Record relationships, evidence, provenance and optional confidence; qualify interpretative claims.
6. Validate the canonical CSV records and synchronize the XLSX Reference Register.
7. Derive timelines, maps, research outputs and future semantic representations from the validated records.

This is an iterative research process; it does not make either a workbook or graph a second authority for structured data.

The research outputs may subsequently include:

- thesis chapters;
- academic papers;
- historical timelines;
- teaching modules;
- regional ecological profiles;
- technology assessments;
- design propositions;
- interactive maps;
- productive-inference tools.

---

## 29. Governance rule for future additions

Before adding a new field, entity class, classification system or relationship predicate, ask:

> **Does this represent a recurring distinction that materially improves the research or computational model?**

If no, use an existing field.

If yes, document the addition in this README and increment the protocol version.

This prevents uncontrolled ontology growth.

Suggested versioning:

- **v1.2:** finalized architecture with the reserved core and extended entity classes, analytical namespaces and provenance model.
- **v1.2.1:** compatible wording, vocabulary or schema clarifications.
- **v1.3:** deliberate additions such as a new entity class or analytical dimension.
- **v2.0:** substantial restructuring requiring migration guidance and explicit mappings.

### v1.2 change and governance note

This version consolidates the research knowledge base architecture and reserves Place, Technology, Ecological phenomenon, Instrument, Dataset and Project/program alongside the core entities. Final consistency corrections clarify identifier syntax, predicate coverage, assertion provenance, table links, CSV quoting and repeated-value conventions without adding new research scope.

Maintain a concise dated change record for protocol and controlled-vocabulary revisions. Preserve issued entity IDs and the frozen HA/IL/IM checkpoint; document replacements and migrations rather than silently changing meanings or renumbering records. Add structure only when a recurring research need justifies it. The protocol governs knowledge organization; institutional citation requirements and established external scholarly identifiers remain authoritative for their respective purposes.

