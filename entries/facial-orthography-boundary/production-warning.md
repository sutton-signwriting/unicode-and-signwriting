# Unicode SignWriting Production Warning

**For people choosing a Sutton SignWriting text format**

Status note: This companion page supports *Facial Orthography Boundary*. It is a practical warning for writers, teachers, implementers, publishers, corpus builders, archivists, dataset builders, AI workflows, funders, and software projects.

## Warning

Do not use the official Unicode SignWriting block as production text for complete Sutton SignWriting.

Official Unicode SignWriting is real Unicode support. It is not production Unicode support for Sutton SignWriting.

Use FSW/SWU, Sutton SignWriting-compatible tooling, or an equivalent coordinate-preserving production model when the work must preserve written signs.

## Why

The decisive issue is facial writing.

Official Unicode represents facial writing as:

> `U+1D9FF SIGNWRITING HEAD` plus nonspacing facial marks.

That sequence stores a head plus Unicode facial mark categories. It does not store the Sutton SignWriting facial symbols the writer selected or the authored facial arrangement.

For simple or conventional faces, a font may draw a plausible face. That does not make the sequence production text. A renderer cannot recover authored facial arrangement from a sequence that never stored it.

## Use This

Use FSW/SWU, Sutton SignWriting-compatible tooling, or an equivalent coordinate-preserving production model for:

- complete written signs
- production authoring
- migration from existing Sutton SignWriting data
- production citation
- dictionaries and lexical databases
- corpora and archives
- education and publication
- search, sorting, rendering, and revision
- AI datasets and machine-learning workflows
- long-term preservation

The key property is preservation: selected symbols, sign boundaries, authored spatial relations, and authored facial arrangement.

## Decision Table

| Use case | Official Unicode block/model | FSW/SWU or equivalent production model |
| --- | --- | --- |
| Unicode documentation | Yes | Optional |
| Standards history or Unicode-model research | Yes | Optional |
| Font experiments | Limited | Yes |
| Complete written signs | No | Yes |
| Production authoring | No | Yes |
| Facial orthography | No | Yes |
| Corpora / archives / AI datasets | No | Yes |
| Dictionaries and education | No | Yes |
| Production citation | No | Yes |
| Long-term preservation | No | Yes |

This table is about Sutton SignWriting-compatible production workflows. It is not a claim that the official Unicode block has no Unicode-scoped value.

## What Unicode Can Serve

The official Unicode block can serve:

- Unicode-model documentation
- standards history
- implementation audits of the official block or Noto-style font path
- compatibility warnings and loss analysis
- limited display experiments
- research explicitly scoped to what Unicode encoded

That is Unicode-scoped value. It is not production text value for Sutton SignWriting.

Noto Sans SignWriting demonstrates that a public font path for the official Unicode approach exists. It does not demonstrate audited production readiness, lossless migration from FSW/SWU, renderer-independent facial authoring, or compatibility across independent implementations.

## Practical Rule

If a workflow must preserve Sutton SignWriting as written text, do not make the official Unicode block the basis.

If a higher-level model preserves selected symbols, authored coordinates, sign boundaries, and authored facial arrangement, then that higher-level model is the production basis. The official Unicode facial sequence remains a Unicode-specific abstraction, not production-preserving Sutton SignWriting facial writing.

For the full technical argument, read *Facial Orthography Boundary*. For the detailed comparison, read *Compatibility Matrix*. Both are companion documents in the *Facial Orthography Boundary* entry of the *Unicode and SignWriting* series.
