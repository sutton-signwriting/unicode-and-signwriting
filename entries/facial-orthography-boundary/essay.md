# Facial Orthography Boundary

**Unicode Sutton SignWriting and renderer-supplied facial composition**

Status note: This is an author-stewardship technical boundary note prepared for public, implementation, preservation, and SignWriting community discussion. It is not an official Unicode publication, Wikimedia position, or standards-body decision.

This note is for people choosing text models, tools, corpora, datasets, archives, publications, and educational workflows for Sutton SignWriting.

The practical boundary is direct:

> The official Unicode Sutton SignWriting block is a Unicode-internal standards artifact: an official Unicode character repertoire and Unicode-specific composition model. It is not the Sutton production symbol repertoire, not the Sutton production text model, and not a production foundation for complete written signs. Its official facial-diacritic model should not be used as a production representation or general production authoring model for Sutton facial writing.

For production Sutton SignWriting, use FSW/SWU, Sutton-compatible tooling, or an equivalent coordinate-preserving production model. Do not use the official Unicode block as the basis for production authoring, migration, citation, archiving, corpora, dictionaries, education, search, AI datasets, or preservation of Sutton SignWriting.

The official Unicode block can still be discussed for what it is: a stable Unicode artifact useful for Unicode-scoped documentation, standards history, implementation audits, limited display experiments, compatibility warnings, and research explicitly scoped to the official Unicode model. That is not the same as being useful as a production SignWriting text layer.

The reason is structural. The official facial-diacritic model represents facial writing as:

> `U+1D9FF SIGNWRITING HEAD` plus nonspacing facial marks.

For general FSW/SWU facial expressions, that sequence cannot supply a lossless production migration path by itself because authored facial arrangement is not present in the representation. The same boundary applies to new official-Unicode authoring: the model asks writers to work through renderer-supplied facial composition rather than storing authored facial arrangement as text.

## Core Position

The official Unicode Sutton SignWriting encoding is a real standards artifact. It names Unicode characters, assigns code points, and defines a Unicode-specific model for representing some SignWriting material.

That status should not be inflated. Official Unicode SignWriting code points are useful for talking about official Unicode SignWriting code points. That is not the same as being useful for working with production Sutton SignWriting.

The compatibility problem is the official facial-diacritic model. It assumes that a written face can be represented as a head plus a list of facial components, with the final written face supplied by rendering rules.

That model may be usable for simple or conventional faces. It fails as a production representation and general production authoring model for Sutton facial writing because it has no place to store authored facial arrangement.

Production Sutton facial writing needs preservation of:

- writer-selected facial-symbol identity
- authored facial arrangement
- spatial distinctions that may carry written meaning
- enough information for rendering, search, sorting, citation, archiving, corpus work, datasets, AI, machine-learning workflows, and production reuse
- the capacity for communities to develop facial orthography over time

In this note, **writer-selected facial-symbol identity** means the production-level symbol identity preserved in FSW/SWU, not merely the presence of abstract Unicode facial mark categories.

The official facial-diacritic model does not store the authored facial arrangement as text. It stores a component list and requires a renderer to construct the written face. That is not production-compatible preservation of Sutton facial authorship.

Facial expression is not marginal in signed languages. It can carry grammatical, lexical, discourse, affective, pedagogical, and poetic information. A text model that works only for simple or conventional faces is therefore limited in a central expressive domain of signed-language writing.

## Practical Guidance

Use official Unicode Sutton SignWriting only when the task is explicitly scoped to the Unicode model:

- Unicode character citation within the official Unicode model
- standards discussion about what Unicode encoded
- implementation audits of the official block or Noto-style font path
- compatibility warnings and loss analysis
- limited display experiments
- research explicitly scoped to the official block

Use FSW/SWU, Sutton-compatible tooling, or an equivalent coordinate-preserving production model when the task is:

- complete written signs
- dictionaries and lexical databases
- corpora and archives
- education and publication
- production citation, search, sorting, rendering, and revision
- datasets, AI, and machine-learning workflows

Noto Sans SignWriting demonstrates that a public font path for the official Unicode approach exists. It does not demonstrate audited production readiness, lossless migration from FSW/SWU, renderer-independent facial authoring, or compatibility across independent implementations.

Do not treat missing adoption of the official Unicode block as evidence that Sutton SignWriting lacks production use. The production path exists; it is not the official Unicode block.

Do not treat Unicode-native authoring as solving this boundary unless authored facial arrangement is preserved independently of a particular renderer's facial-composition behavior.

If a higher-level protocol uses Unicode characters while separately carrying authored coordinates or facial arrangement data, production compatibility comes from that separate production model, not from the official `HEAD + facial marks` sequence. For facial writing, Unicode facial marks should not be assumed to be valid production symbol identifiers unless they correspond to independently preservable Sutton production symbols.

## What The Unicode Block Provides

Unicode encoded a Sutton SignWriting block in Unicode 8.0.0 and later versions. That block can name many characters within the official Unicode model. It can support Unicode character citation, standards discussion about the Unicode model, work scoped to that model, and some font-based rendering.

Those facts define the useful Unicode-internal scope of the block. They do not establish production compatibility for complete written signs. A stable Unicode encoding can still be inadequate as a production foundation for the writing system it claims to encode.

ISWA 2010 remains the Sutton production symbol repertoire. The Unicode block is an official Unicode repertoire/model; it should not be treated as the production symbol repertoire or as the primary citation mechanism for Sutton SignWriting production symbols. When this note refers to Unicode character citation, it means citation within the official Unicode model, not citation of every Sutton production symbol or written object.

The Core Specification itself exposes the boundary. It describes SignWriting symbols as arranged in two-dimensional layout to form signs and states that spatial arrangement is essential to the writing system, while treating that arrangement as a higher-level protocol beyond the scope of the Unicode Standard. That is why official character support should not be mistaken for complete production text support.

In this note, **Unicode-specific facial composition model** means the official model in which facial expressions are represented by `U+1D9FF SIGNWRITING HEAD` plus nonspacing facial marks.

The Core Specification describes head and face characters as combining character sequences formed with `U+1D9FF SIGNWRITING HEAD` as a base followed by nonspacing marks for eyes, cheeks, mouth, and related expressions.

The L2/12-321 / N4342 SignWriting proposal describes the same design in section 6, "Faces and heads." The model consists of `U+1D9FF SIGNWRITING HEAD`, combining face characters, and fill modifiers that subcategorize those marks. The proposal says diacritics may occur after the head with eye and mouth diacritics combined in the sequence.

That is a categorical sequence model. It contains no coordinate field, no relative-placement field, and no authored-arrangement field for the facial components. Sequence order may identify which marks occur after the head; it does not preserve the writer's spatial arrangement of the written face.

The same section treats facial marks without a visible head as an exceptional case handled by making the head invisible, and says that rendering face modifiers without a face is "never used in actual sign languages." That is not a neutral preservation rule. It is another assumption about what facial writing will need to express.

## Why The Facial Model Fails

The facial-diacritic model makes a sufficiency claim that fails for production migration and general production authoring:

> A written face can be sufficiently represented by a head plus facial marks, and a renderer can reconstruct the written face from that data.

As a production-migration and production-authoring claim for general Sutton facial writing, that claim fails structurally.

The model stores component categories and leaves facial construction to rendering rules. A renderer that constructs the face from the mark list must decide ordering, attachment, hierarchy, collision handling, normal arrangements, valid combinations, and what counts as the same face.

Those are not merely graphic engineering decisions. They are orthographic assumptions.

The argument is:

1. Sutton production facial writing preserves writer-selected facial-symbol identity and authored facial arrangement as part of the written object.
2. In SignWriting, space can carry authored meaning.
3. The official Unicode facial-diacritic model stores `HEAD + facial marks`; it does not store the authored facial arrangement as text.
4. Missing authored arrangement cannot be recovered from a sequence that never stored it.
5. Therefore implementations should not present the official Unicode facial-diacritic model as a production-compatible representation or authoring model for general Sutton facial writing.

This is not a demand that users prove a currently canonical facial minimal pair. The problem is that the model discards the authored arrangement needed to evaluate such questions.

For simple faces, a font may produce a plausible conventional result from a component list. That does not prove production compatibility. A writing system is not defined only by simple cases. Complex, expressive, poetic, pedagogical, experimental, and community-specific faces are exactly where orthographic assumptions are least safe.

## Why This Is Not A Font Problem

All visible text depends on rendering. That is not the problem.

The problem is where the authored written information is stored.

In Sutton production SignWriting, the writer's facial composition is stored as part of the text model. A renderer may be technically complex, but it renders the writer's selected composition.

In the Unicode-specific facial composition model, the author supplies `HEAD + facial marks` and then sees what a particular font or renderer does with that list. For complex faces, the author may need to manipulate one implementation's assumptions, compromise when that implementation cannot construct the intended face, or accept a rendered result that is not independently preserved by the text.

If a particular complex face cannot be preserved by `HEAD + facial marks`, the answer may be: the font should improve. That answer is valid only if the encoded sequence is already accepted as the complete text identity of the written face. But that is exactly what this note disputes.

The question is not:

> Can a better font draw a plausible face from this sequence?

The question is:

> Did the stored text preserve the authored facial-symbol identity and arrangement before the font acted?

This is also not the ordinary complex-script case. Many writing systems require sophisticated shaping, positioning, contextual substitution, mark attachment, or rendering behavior. In ordinary complex-script cases, the encoded sequence is accepted as the text identity and rendering realizes conventional visual behavior downstream from that identity. Rendering is complex, but it does not supply missing authorship of the written object.

The Sutton facial issue is different because the point under dispute is whether `HEAD + facial marks` is an accepted production abstraction of the written face. Sutton production text stores writer-selected facial-symbol identity and authored facial arrangement as the written object.

## New Authoring Still Depends On The Renderer

This boundary is not only about migration from existing FSW/SWU data.

A new editor could support official Unicode Sutton SignWriting for some tasks. A writer might spatially arrange hands, movements, contacts, body symbols, and other written-sign components while using official Unicode characters as identifiers.

The facial model changes the authoring mode. For faces, the writer would not directly arrange production-level facial symbols in authored space. The writer would add facial marks to a head and see what a particular font or renderer constructs.

If the rendered face is simple or conventional and captures the writer's intention, the problem may remain hidden. The writer can keep working.

For complex faces, the writer may have to negotiate with the renderer's facial theory. The writer may need to try different mark choices, change the order of facial diacritics, use multiple heads or overlapping constructed faces, depend on private conventions, or leave the official model for FSW/SWU, images, or application-specific data.

That is not the same as authoring facial space as text. Mark order may become an indirect control for one renderer's behavior, but sequence order is not authored facial arrangement. A writer may need one tool for the spatial signbox and another tool for manipulating the facial sequence that drives the font.

Some arrangements may be structurally unavailable. The official model treats facial marks as nonspacing marks attached to a head. A facial mark without a visible face is treated as an exceptional invisible-head case in the proposal, not as a general coordinate-bearing facial symbol that the writer can place freely.

The result is renderer-dependent facial authorship. The writer is not only writing with an abstract facial-diacritic model. In difficult cases, the writer is writing against a specific font or renderer implementation. There is no demonstrated basis here for assuming that independently developed fonts would have the same facial coverage, ordering behavior, collision handling, or composition rules.

Even a polished font would not solve that production boundary by itself. It would show that one implementation can construct some faces from `HEAD + facial marks`. It would not show that the stored text preserves authored facial arrangement, that Unicode-native authoring is portable across independent renderers, or that the model is production-compatible with general Sutton facial writing.

## Why Spatial Authorship Matters

Sutton SignWriting conveys meaning through authored spatial relations. Facial writing is not exempt from that principle.

The issue is not that every facial placement difference must be canonical spelling. The issue is that a text model cannot decide in advance that facial space is non-meaningful and safely discard it.

The L2/12-321 / N4342 proposal itself states that SignWriting characters are combined spatially on two-dimensional canvases to form written signs, then says: "This spatial organization is spelling and is an essential part of the writing system." Its later layout discussion states the same production principle plainly: the writer decides the symbols and their placement.

The *FSW and SWU* paper in the Formal SignWriting series identifies the production symbol inventory used by FSW/SWU and describes the coordinate model used to specify spatial relationships between symbols. Because the production model stores selected symbols with authored coordinates, it can carry fine spatial information. The font renders the selected symbols and their placement; it does not invent the spatial relation.

That does not prove every facial arrangement is meaningful. It demonstrates the production principle that authored spatial relations among selected symbols can be written information. The facial argument applies that preservation principle to a model that omits facial arrangement from the text layer.

Facial orthography is living and developing. Different signing communities, teachers, dictionaries, editors, writers, and readers may not make the same decisions about which facial distinctions are canonical, variant, local, pedagogical, expressive, poetic, or erroneous. Those decisions belong to the affected writing communities.

A production text model should preserve authored facial composition first, so communities can later compare, teach, normalize, reject, revise, or standardize written forms. If a text model discards authored facial arrangement and stores only `HEAD + facial marks`, later communities cannot recover the omitted arrangement from the standard text. They can only reinterpret the component list, depend on particular fonts, or use another carrier such as FSW/SWU, private conventions, images, or application-specific data.

That is a loss of orthographic capacity.

A conformance suite can demonstrate failure when a model cannot preserve selected examples. It cannot prove future orthographic adequacy for a living writing system. Passing a selected suite would only show that the selected cases work. It would not show that the model can support future community distinctions, poetic uses, pedagogical forms, local practices, or complex facial arrangements that have not yet been standardized.

## The 2012 Mapping Claim Does Not Settle This Boundary

The L2/12-321 / N4342 proposal includes claims about mapping SignWriting material into the proposed Unicode structure. Those claims should be read within their scope.

In particular, section 5 describes previous data as reliably mappable to the proposed encoding structure, and section 9.1 describes one encoding choice as isomorphic to previous implementations.

For practitioners, the important distinction is simple: mapping symbol identifiers is not the same as preserving authored facial arrangement.

The facial-diacritic model makes a different claim from ordinary symbol mapping. It claims that a written face can be represented as a head plus facial marks, with the face constructed by rendering rules.

That is the claim at issue here.

For general FSW/SWU facial expressions, such an isomorphism cannot be supplied by the official facial sequence itself. Two authored faces may use the same facial components but arrange them differently. FSW/SWU can preserve that difference as selected symbols with authored coordinates. The Unicode facial sequence records the head and marks, not that authored arrangement. Those two production forms therefore collapse to the same official facial sequence unless additional data is carried outside the Unicode facial-diacritic model.

A higher-level protocol could use some Unicode characters while separately carrying authored coordinates or facial arrangement data. In that case, however, production compatibility comes from that coordinate-bearing production model, not from the official `HEAD + facial marks` sequence. A list of facial diacritics is not the same data as an authored facial arrangement.

This caveat is important: external coordinates do not automatically rescue the official facial sequence. If a Unicode facial mark cannot be independently selected, viewed, placed, and preserved as a Sutton production facial symbol, then adding coordinates around that mark preserves coordinates for the Unicode model, not necessarily production facial-symbol identity. Diagnostic mapping is not production citation.

## Production Path

This is a technical compatibility claim, not a claim of linguistic authority.

FSW/SWU compatibility means that a text model preserves the authored written data needed for parsing, rendering, searching, sorting, interchange, archives, corpora, and production workflows. It does not decide whether a written form is good, preferred, standard, local, poetic, pedagogical, or community-approved.

Within the Sutton-maintained production ecosystem and the cited Formal SignWriting materials, FSW remains the primary production encoding, and SWU remains the supported Unicode-oriented isomorphic representation. They are not official Unicode SignWriting. They are the working production representations that carry complete written-sign data.

Other production models are possible if they preserve the same necessary data. The key property is not the name FSW or SWU. The key property is preservation of selected symbols and authored spatial relations, including authored facial arrangement.

Any particular implementation can still be evaluated for normalization, rounding, coordinate handling, rendering consistency, and round-trip behavior. That is an ordinary implementation audit. It is different from a model that has no text-layer field for authored facial arrangement in the first place.

## Durable Boundary

Unicode stability makes this boundary durable, because the encoded facial model cannot realistically be redefined into a coordinate-bearing production model without changing what it is. Once encoded and documented as the official facial model, the head-plus-mark abstraction remains durable even if later communities need to preserve facial arrangements that the model did not store.

Future communities can work around the model, but they cannot rely on the official facial-diacritic model to preserve authored arrangements that the model never stored.

The practical response is community and implementation clarity: state the boundary, design tools around the data that must be preserved, and stop using official character support as a proxy for production Sutton text support. Official Unicode stability is Unicode stability. It is not production stability for Sutton SignWriting.

## What This Boundary Note Does Not Claim

This boundary note does not claim:

- that the Unicode block has no value
- that existing characters should be removed or renamed
- that FSW or SWU are official Unicode SignWriting
- that SWU adoption by itself proves official Unicode inadequacy
- that every facial arrangement difference is canonical spelling
- that every SignWriting use case must use the Sutton production stack
- that all future research, notation, or display uses of the Unicode block are invalid

It claims a narrower production fact:

> The official Unicode Sutton SignWriting encoding is a Unicode-internal character repertoire and Unicode-specific composition model, including a facial-diacritic model that is not production-compatible as a representation or general authoring model for Sutton facial writing.

## Supporting Documents

The companion documents in this entry support the boundary note:

- *Compatibility Matrix* compares FSW, SWU, and the Unicode Sutton SignWriting block across production-interchange questions.
- *Boundary Actions* records practical community, implementation, documentation, migration-warning, and authoring-warning outcomes.

The broader Unicode and SignWriting series supplies supporting context:

- *Unicode Overview*
- *Developer Notes*
- *Chronology and Record*
- *Wikimedia Brief*
- *Formal SignWriting in Practice*
- *Searching Signed Text*

## Closing

The official Unicode Sutton SignWriting block should be described according to what it provides: a Unicode-internal character repertoire and Unicode-specific composition model. It should not be mistaken for production-compatible interchange, production citation, production preservation, or general production authoring support for complete Sutton SignWriting written signs.

The practical next step is community clarity: route production work around the official Unicode facial model. Use FSW/SWU, Sutton-compatible tooling, or an equivalent coordinate-preserving production model for Sutton SignWriting. Treat the official Unicode block as a Unicode-scoped artifact, not as the text foundation for SignWriting.

## Sources And Evidence Anchors

- [Unicode 17 Core Specification, Chapter 21](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-21/)
- [Unicode Character Encoding Stability Policies](https://www.unicode.org/policies/stability_policy.html)
- [L2/12-321 / N4342 SignWriting proposal](https://www.unicode.org/L2/L2012/12321-n4342-signwriting.pdf)
- [Noto Sans SignWriting repository](https://github.com/notofonts/sign-writing)
- [ISWA 2010 Alphabet Viewer](https://steveslevinski.me/#page/iswa-alphabet)
- [FSW and SWU](https://doi.org/10.5281/zenodo.20272667)
- [Formal SignWriting series](https://doi.org/10.5281/zenodo.20074767)
- *Chronology and Record*
- *Formal SignWriting in Practice*
- *Searching Signed Text*
