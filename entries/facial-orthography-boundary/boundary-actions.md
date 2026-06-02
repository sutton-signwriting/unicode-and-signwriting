# Boundary Actions

**Community and implementation actions after the facial-orthography boundary**

Status note: This companion document supports *Facial Orthography Boundary*. It turns the boundary into practical actions for writers, teachers, implementers, corpus builders, researchers, archivists, funders, and software projects.

## Use The Boundary In Practice

The practical rule is simple:

- treat the official Unicode Sutton SignWriting block as a Unicode-scoped artifact for Unicode-model documentation, implementation audits, compatibility warnings, limited display experiments, and research explicitly scoped to the official block
- use FSW/SWU, Sutton-compatible tooling, or an equivalent coordinate-preserving production model for complete written signs, dictionaries, corpora, education, publication, archives, datasets, AI, and machine-learning workflows
- do not use the official Unicode block as the basis for production authoring, migration, citation, archiving, corpora, dictionaries, education, search, AI datasets, or preservation of Sutton SignWriting

Do not represent Noto Sans SignWriting, font support, or character-block support as proof of production-compatible text interchange or general production authoring. Noto demonstrates that a public font path for the official Unicode approach exists. It does not demonstrate audited production readiness, lossless migration from FSW/SWU, renderer-independent facial authoring, or compatibility across independent implementations.

## Implementation Actions

Implementers should:

1. Identify whether the task requires production Sutton SignWriting or only Unicode-model analysis.
2. Use FSW/SWU, Sutton-compatible tooling, or an equivalent coordinate-preserving production model for complete written signs.
3. Treat official Unicode SignWriting support as Unicode-model support, not as a production character layer.
4. Avoid presenting Noto/font support as proof of production-compatible text interchange.
5. Do not treat Unicode-native authoring as production-compatible for general Sutton facial writing unless authored facial arrangement is preserved independently of the renderer.
6. Preserve source FSW/SWU or equivalent production data when generating images, fonts, derived datasets, or display-only outputs.
7. Document which layer carries the authored written sign: production text, Unicode character sequence, rendered image, private payload, or application-specific data.
8. Treat lossy projection into the official Unicode facial model as diagnostic mapping, not production citation, publication, preservation, or interchange.

## Preservation Guidance

Archives, corpora, datasets, AI workflows, and publication systems should preserve the production text source when they create derived outputs.

Rendered images, font-specific output, screenshots, presentation markup, and application-specific payloads can be useful, but they should not replace the coordinate-preserving written-sign data unless the project explicitly accepts that loss.

For production Sutton SignWriting, the preservation target is not merely a recognizable rendered sign. It is the authored written sign: selected symbols, sign boundaries, spatial relations, and authored facial arrangement.

## What Would Change The Boundary

The boundary conclusion would need revision only if a model demonstrated:

- preservation of complete written-sign boundaries
- preservation of writer-selected symbol identity
- preservation of writer-selected facial-symbol identity and authored facial arrangement
- renderer-independent authoring of general Sutton facial writing
- stable behavior across independent implementations
- search, sorting, rendering, citation, revision, archive, corpus, dataset, AI, and machine-learning workflows over complete written signs

For the official facial-diacritic sequence alone, the missing field is the issue: authored facial arrangement is not present in `HEAD + facial marks`.
