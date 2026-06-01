# Facial Orthography Boundary

**Unicode Sutton SignWriting and renderer-supplied facial composition**

Status note: This is an author-stewardship technical boundary note prepared for public, implementation, preservation, and SignWriting community discussion. It is not an official Unicode publication, Wikimedia position, or standards-body decision.

This note is for people choosing text models, tools, corpora, datasets, archives, publications, and educational workflows for Sutton SignWriting.

The practical boundary is direct:

> The official Unicode Sutton SignWriting block provides a character repertoire and Unicode-specific composition model. It is not the Sutton production text model for complete written signs. Its official facial-diacritic model should not be used as a production representation of general Sutton facial writing.

For production Sutton SignWriting, use FSW/SWU, Sutton-compatible tooling, or an equivalent coordinate-preserving production model. Use the official Unicode block for the purposes it can serve: character citation, standards discussion, Unicode-model research, limited symbol display, and work explicitly scoped to the official block.

The reason is structural. The official facial-diacritic model represents facial writing as:

> `U+1D9FF SIGNWRITING HEAD` plus nonspacing facial marks.

For general FSW/SWU facial expressions, that sequence cannot supply a lossless production migration path by itself because authored facial arrangement is not present in the representation.

## Core Position

The official Unicode Sutton SignWriting encoding is a real standards artifact. It names characters, assigns code points, and defines a Unicode-specific model for representing some SignWriting material.

The compatibility problem is the official facial-diacritic model. It assumes that a written face can be represented as a head plus a list of facial components, with the final written face supplied by rendering rules.

That model may be usable for simple or conventional faces. It fails as a production representation for general Sutton facial writing because it has no place to store authored facial arrangement.

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

Use official Unicode Sutton SignWriting when the task is:

- character citation
- standards discussion
- character-level interchange or symbol citation scoped to the Unicode repertoire/model
- limited symbol display
- research explicitly scoped to the official block

Use FSW/SWU, Sutton-compatible tooling, or an equivalent coordinate-preserving production model when the task is:

- complete written signs
- dictionaries and lexical databases
- corpora and archives
- education and publication
- search, sorting, rendering, and revision
- datasets, AI, and machine-learning workflows

Noto Sans SignWriting demonstrates that a public font path for the official Unicode approach exists. It does not demonstrate audited production readiness, lossless migration from FSW/SWU, or compatibility across independent implementations.

Do not treat missing adoption of the official Unicode block as evidence that Sutton SignWriting lacks production use. The production path exists; it is not the official Unicode block.

If a higher-level protocol uses Unicode characters as symbol identifiers while separately carrying authored coordinates or facial arrangement data, production compatibility comes from that coordinate-bearing protocol, not from the official `HEAD + facial marks` sequence.

## What The Unicode Block Provides

Unicode encoded a Sutton SignWriting block in Unicode 8.0.0 and later versions. That block can name many symbols. It can support character citation, standards discussion, work scoped to the Unicode model, and some font-based rendering.

Those facts define the useful scope of the block. They do not establish production compatibility for complete written signs.

The Core Specification itself exposes the boundary. It describes SignWriting symbols as arranged in two-dimensional layout to form signs and states that spatial arrangement is essential to the writing system, while treating that arrangement as a higher-level protocol beyond the scope of the Unicode Standard. That is why official character support should not be mistaken for complete production text support.

In this note, **Unicode-specific facial composition model** means the official model in which facial expressions are represented by `U+1D9FF SIGNWRITING HEAD` plus nonspacing facial marks.

The Core Specification describes head and face characters as combining character sequences formed with `U+1D9FF SIGNWRITING HEAD` as a base followed by nonspacing marks for eyes, cheeks, mouth, and related expressions.

The L2/12-321 / N4342 SignWriting proposal describes the same design in section 6, "Faces and heads." The model consists of `U+1D9FF SIGNWRITING HEAD`, combining face characters, and fill modifiers that subcategorize those marks. The proposal says diacritics may occur after the head with eye and mouth diacritics combined in the sequence.

That is a categorical sequence model. It contains no coordinate field, no relative-placement field, and no authored-arrangement field for the facial components. Sequence order may identify which marks occur after the head; it does not preserve the writer's spatial arrangement of the written face.

The same section treats facial marks without a visible head as an exceptional case handled by making the head invisible, and says that rendering face modifiers without a face is "never used in actual sign languages." That is not a neutral preservation rule. It is another assumption about what facial writing will need to express.

## Why The Facial Model Fails

The facial-diacritic model makes a sufficiency claim that fails for production migration:

> A written face can be sufficiently represented by a head plus facial marks, and a renderer can reconstruct the written face from that data.

As a production-migration claim for general FSW/SWU facial expressions, that claim fails structurally.

The model stores component categories and leaves facial construction to rendering rules. A renderer that constructs the face from the mark list must decide ordering, attachment, hierarchy, collision handling, normal arrangements, valid combinations, and what counts as the same face.

Those are not merely graphic engineering decisions. They are orthographic assumptions.

The argument is:

1. Sutton production facial writing preserves writer-selected facial-symbol identity and authored facial arrangement as part of the written object.
2. In SignWriting, space can carry authored meaning.
3. The official Unicode facial-diacritic model stores `HEAD + facial marks`; it does not store the authored facial arrangement as text.
4. Missing authored arrangement cannot be recovered from a sequence that never stored it.
5. Therefore implementations should not present the official Unicode facial-diacritic model as production-compatible with general Sutton facial writing.

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

## Why Spatial Authorship Matters

Sutton SignWriting conveys meaning through authored spatial relations. Facial writing is not exempt from that principle.

The issue is not that every facial placement difference must be canonical spelling. The issue is that a text model cannot decide in advance that facial space is non-meaningful and safely discard it.

The L2/12-321 / N4342 proposal itself states that SignWriting characters are combined spatially on two-dimensional canvases to form written signs, then says: "This spatial organization is spelling and is an essential part of the writing system." Its later layout discussion states the same production principle plainly: the writer decides the symbols and their placement.

The *FSW and SWU* paper in the Formal SignWriting series identifies the production symbol inventory used by FSW/SWU and describes the coordinate model used to specify spatial relationships between symbols. Because the production model stores selected symbols with authored coordinates, it can carry fine spatial information. The font renders the selected symbols and their placement; it does not invent the spatial relation.

That does not prove every facial arrangement is meaningful. It demonstrates the production principle that authored spatial relations among selected symbols can be written information. The facial argument applies that preservation principle to a model that omits facial arrangement from the text layer.

Facial orthography is living and developing. Different signing communities, teachers, dictionaries, editors, writers, and readers may not make the same decisions about which facial distinctions are canonical, variant, local, pedagogical, expressive, poetic, or erroneous. Those decisions belong to the affected writing communities.

A production text model should preserve authored facial composition first, so communities can later compare, teach, normalize, reject, revise, or standardize written forms. If a text model discards authored facial arrangement and stores only `HEAD + facial marks`, later communities cannot recover the omitted arrangement from the standard text. They can only reinterpret the component list, depend on particular fonts, or use another carrier such as FSW/SWU, private conventions, images, or application-specific data.

That is a loss of orthographic capacity.

## The 2012 Mapping Claim Does Not Settle This Boundary

The L2/12-321 / N4342 proposal includes claims about mapping SignWriting material into the proposed Unicode structure. Those claims should be read within their scope.

In particular, section 5 describes previous data as reliably mappable to the proposed encoding structure, and section 9.1 describes one encoding choice as isomorphic to previous implementations.

For practitioners, the important distinction is simple: mapping symbol identifiers is not the same as preserving authored facial arrangement.

The facial-diacritic model makes a different claim from ordinary symbol mapping. It claims that a written face can be represented as a head plus facial marks, with the face constructed by rendering rules.

That is the claim at issue here.

For general FSW/SWU facial expressions, such an isomorphism cannot be supplied by the official facial sequence itself. Two authored faces may use the same facial components but arrange them differently. FSW/SWU can preserve that difference as selected symbols with authored coordinates. The Unicode facial sequence records the head and marks, not that authored arrangement. Those two production forms therefore collapse to the same official facial sequence unless additional data is carried outside the Unicode facial-diacritic model.

A higher-level protocol could use Unicode characters as symbol identifiers while separately carrying authored coordinates or facial arrangement data. In that case, however, production compatibility comes from that extra coordinate-bearing protocol, not from the official `HEAD + facial marks` sequence. A list of facial diacritics is not the same data as an authored facial arrangement.

## Production Path

This is a technical compatibility claim, not a claim of linguistic authority.

FSW/SWU compatibility means that a text model preserves the authored written data needed for parsing, rendering, searching, sorting, interchange, archives, corpora, and production workflows. It does not decide whether a written form is good, preferred, standard, local, poetic, pedagogical, or community-approved.

Within the Sutton-maintained production ecosystem and the cited Formal SignWriting materials, FSW remains the primary production encoding, and SWU remains the supported Unicode-oriented isomorphic representation. They are not official Unicode SignWriting. They are the working production representations that carry complete written-sign data.

Other production models are possible if they preserve the same necessary data. The key property is not the name FSW or SWU. The key property is preservation of selected symbols and authored spatial relations, including authored facial arrangement.

Any particular implementation can still be evaluated for normalization, rounding, coordinate handling, rendering consistency, and round-trip behavior. That is an ordinary implementation audit. It is different from a model that has no text-layer field for authored facial arrangement in the first place.

## Durable Boundary

Unicode stability makes this boundary durable, because the encoded facial model cannot realistically be redefined into a coordinate-bearing production model without changing what it is. Once encoded and documented as the official facial model, the head-plus-mark abstraction remains durable even if later communities need to preserve facial arrangements that the model did not store.

Future communities can work around the model, but they cannot rely on the official facial-diacritic model to preserve authored arrangements that the model never stored.

The practical response is community and implementation clarity: state the boundary, design tools around the data that must be preserved, and stop using official character support as a proxy for production Sutton text support.

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

> The official Unicode Sutton SignWriting encoding is a character repertoire and Unicode-specific composition model, including a facial-diacritic model that is not production-compatible with general Sutton facial writing.

## Supporting Documents

The companion documents in this entry support the boundary note:

- *Compatibility Matrix* compares FSW, SWU, and the Unicode Sutton SignWriting block across production-interchange questions.
- *Boundary Actions* records practical community, implementation, documentation, and migration-warning outcomes.

The broader Unicode and SignWriting series supplies supporting context:

- *Unicode Overview*
- *Developer Notes*
- *Chronology and Record*
- *Wikimedia Brief*
- *Formal SignWriting in Practice*
- *Searching Signed Text*

## Closing

The official Unicode Sutton SignWriting block should be described according to what it provides: a character repertoire and Unicode-specific composition model. It should not be mistaken for production-compatible interchange for complete Sutton SignWriting written signs.

The practical next step is community clarity: use the official Unicode block for the purposes it can serve, and do not use its facial-diacritic model as a production representation of Sutton facial writing.

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
