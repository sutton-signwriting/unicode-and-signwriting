# Facial Orthography Boundary

**Why official Unicode SignWriting is not a production basis for facial writing**

Status note: This is an author-stewardship technical boundary note prepared for public, implementation, preservation, and SignWriting community discussion. It is not an official Unicode publication, Wikimedia position, or standards-body decision.

This note is for people choosing text models, tools, corpora, datasets, archives, publications, educational workflows, and AI workflows for Sutton SignWriting.

This note is not asking Unicode to change course. It is warning SignWriting users, archivists, implementers, educators, publishers, corpus builders, and dataset builders not to mistake official Unicode encoding for a production-preserving Sutton SignWriting text model.

This note evaluates the official Unicode artifact by the production function people are likely to assign to it. It does not depend on proving that Unicode or UTC promised a complete Sutton SignWriting production text model. The boundary is that the artifact cannot safely serve that production function.

Several sections address arguments that appear in standards discussions or implementation documentation. They are included so that readers can recognize those arguments when they encounter them and understand why they do not change the production boundary.

Recognize the Unicode artifact. Do not use it as the production basis. Protect the writers.

## Verdict

The official Unicode SignWriting block should not be used as the basis for Sutton SignWriting production text.

The official Unicode block is a Unicode-scoped character-encoding artifact. It defines an official Unicode character repertoire and Unicode-specific composition model. It is not the Sutton SignWriting production symbol repertoire, not the Sutton SignWriting production text model, and not a production foundation for complete written signs.

The facial-diacritic model is the decisive failure point. Official Unicode represents facial writing as:

> `U+1D9FF SIGNWRITING HEAD` plus nonspacing facial marks.

That model is not a partial version of Sutton SignWriting production facial writing. It is a different model. It stores a head plus component categories and asks the renderer to construct the face. It does not store the Sutton SignWriting facial symbols the writer selected or the authored facial arrangement.

This note focuses on facial writing because the facial-diacritic model is the most structurally irreparable failure point. Other compatibility problems exist, including spatial composition, sorting, collation, dataset compatibility, and tooling, and they are addressed in companion documents. Facial writing is the decisive test case because the official sequence does not store authored facial arrangement in the first place.

## Core Argument

The boundary can be stated directly:

1. Sutton SignWriting production text must preserve the written sign the author composed.
2. For facial writing, that includes the Sutton SignWriting facial symbols the writer selected and the authored facial arrangement.
3. Official Unicode facial writing stores `HEAD + facial marks`; it does not store the authored facial arrangement as text.
4. Missing authored arrangement cannot be recovered from a sequence that never stored it.
5. Therefore official Unicode SignWriting should not be used as the production basis for Sutton SignWriting facial writing.

The sections that follow explain why this is a text-model problem rather than a font, coordinate placement, conformance, adoption, or implementation-support problem.

## Production Requirement

Sutton SignWriting production text must preserve the written sign the author composed.

For facial writing, that means preserving:

- the Sutton SignWriting facial symbols the writer selected
- authored facial arrangement
- spatial distinctions that may carry written meaning
- enough information for rendering, search, sorting, citation, archiving, corpus work, datasets, AI, machine-learning workflows, publication, and production reuse
- the capacity for communities to develop facial orthography over time

Preserving authored facial arrangement does not mean declaring every facial placement difference to be canonical spelling in advance. It means keeping the written evidence available so communities can later compare, teach, normalize, reject, or standardize those forms as part of their own orthographic development.

ISWA 2010 remains the Sutton SignWriting production symbol repertoire. FSW/SWU preserve selected ISWA 2010 symbols and authored spatial relations in the working Sutton SignWriting ecosystem. Other production models are possible, but only if they preserve the same necessary data: selected symbols, sign boundaries, authored spatial relations, and authored facial arrangement.

Production compatibility is not a status claim. It is a preservation claim.

This requirement becomes more important as SignWriting is used in AI, machine-learning, corpus, and dataset workflows. Those fields depend on reliable text interchange: stable units, preservable structure, searchable forms, citable examples, and reproducible transformations. If the complete written sign is not preserved as a textual unit, downstream systems cannot reliably learn from, compare, cite, transform, or extend Sutton SignWriting data.

## What Unicode Encoded

The official Unicode SignWriting block names Unicode characters, assigns code points, and defines a Unicode-specific model for representing some SignWriting material. That is a real standards artifact.

That status should not be inflated. Official Unicode SignWriting code points are useful for talking about official Unicode SignWriting code points. That is not the same as being useful for working with Sutton SignWriting production text.

The Core Specification describes SignWriting symbols as arranged in two-dimensional layout to form signs and treats that arrangement as a higher-level protocol outside Unicode. The L2/12-321 / N4342 proposal also states that spatial organization is spelling and that the writer decides the symbols and their placement.

For facial writing, however, the resulting official model is not only a model that leaves placement to a higher-level protocol. It encodes a facial abstraction:

```text
HEAD + facial marks
```

The proposal describes `U+1D9FF SIGNWRITING HEAD`, combining face characters, and fill modifiers that subcategorize those marks. It says diacritics may occur after the head with eye and mouth diacritics combined in the sequence.

That is a categorical sequence model. It contains no coordinate field, no relative-placement field, and no authored-arrangement field for the facial components. Sequence order may identify which marks occur after the head. It does not preserve the writer's spatial arrangement of the written face.

The objection here is not to Base+Fill+Rotation triplet mapping for individual Sutton SignWriting symbols in general. It is to the official facial head-plus-diacritic abstraction, which does not preserve authored facial arrangement as production text.

The same proposal treats facial marks without a visible head as an exceptional invisible-head case and says that rendering face modifiers without a face is "never used in actual sign languages." That is not a neutral preservation rule. It is an orthographic assumption about what facial writing will need to express.

As a production basis, that kind of assumption would not merely describe an implementation detail. It would narrow the expressive space before signing communities have had the written evidence needed to decide their own facial conventions.

## Plain Text, Text Elements, Space, And Serialization

For Sutton SignWriting, a complete written sign is a written-sign text element: a bounded written object composed from selected symbols and authored spatial relations. It does not need to be a single Unicode character to be text. It may be represented by a sequence, but the sequence must preserve the structure the writing system uses.

The issue is not only what SignWriting symbols represent. The issue is how selected symbols are organized into complete written signs. Sutton SignWriting writes signed languages through complete written signs composed in signboxes: selected symbols are authored into spatial relation inside a bounded primary written unit.

Authored spatial layout is therefore not rich-text decoration. It is part of the written sign.

A text model for Sutton SignWriting does not need to preserve every visual rendering choice. It does need to preserve the written information the author selected: symbols, sign boundaries, authored spatial relations, and authored facial arrangement. If spatial placement is part of spelling, then preserving that placement is a plain-text requirement for the writing system, not an optional formatting layer.

Unicode's core work is plain-text encoding for written human languages. For many notation systems, Unicode can reasonably encode useful symbols while leaving full layout to higher-level protocols. Sutton SignWriting is different. It is a writing system for signed languages whose primary written unit is spatially composed, and its authored spatial relations are part of the written sign.

A higher-level protocol may be higher-level for Unicode. It is not higher-level for Sutton SignWriting if it carries spelling. If Unicode places essential structure of a written-language text element outside its own scope, then official Unicode SignWriting cannot be treated as production plain text for Sutton SignWriting.

That is the plain-text issue. The storage issue is different: a spatial writing system can be serialized without becoming a linear script.

A spatial writing system can be serialized as text if the serialization preserves the spatial information. FSW/SWU demonstrate that a linear string can preserve selected ISWA 2010 symbols, sign boundaries, coordinates, and authored spatial relations.

The problem with official Unicode SignWriting is therefore not that it is serialized. The problem is that its serialization does not preserve the Sutton SignWriting production object. For facial writing, `HEAD + facial marks` serializes a renderer-mediated abstraction rather than the writer-selected facial symbols and authored facial arrangement.

## The Preservation Mismatch

The preservation mismatch is this: the Unicode record acknowledges that Sutton SignWriting spatial organization is essential to the writing system, and the proposal record states that spatial organization is spelling. Yet the official Unicode artifact that resulted does not preserve signbox spatial relation as plain text, instead assigning it to a higher-level protocol.

If official Unicode SignWriting is defended as a notation-style encoding rather than as a production writing-system text model, that defense confirms the boundary rather than weakening it. Sutton SignWriting is used as a writing system for signed languages. That categorization is also visible in FSW/SWU-based corpus, dataset, machine-translation, and language-modeling workflows, where complete written signs are treated as language text units for modeling, alignment, search, and generation rather than as notation-only graphics. A notation-scoped Unicode artifact may still be useful for Unicode documentation, standards history, or limited display experiments, but it should not be treated as production text support for Sutton SignWriting. If the official block is presented as writing-system support, then it must be evaluated by whether it preserves the complete written sign.

That exclusion is not equivalent to excluding font size, color, page margins, typographic style, or surrounding document layout. If spatial relation is spelling, then excluding spatial relation excludes part of the written form.

Unicode does not need to encode a complete Sutton SignWriting sign as a single character. A complete written sign may be represented by a sequence or by another production text model. But a production text model for Sutton SignWriting must preserve the complete written-sign text element: selected symbols, sign boundary, authored spatial relations, and authored facial arrangement.

Official Unicode SignWriting does not do that. It encodes a Unicode-scoped repertoire and composition model while excluding or abstracting structure needed to preserve the written sign as production text. That is why official Unicode SignWriting can be a real Unicode artifact without being a Sutton SignWriting production text model.

Readers may encounter a MusicXML analogy in standards discussions: Unicode music symbols are not a production score format, and full scores use higher-level protocols. That analogy does not resolve the SignWriting problem because musical notation and Sutton SignWriting are not the same category of system. A full musical score is a specialized notation document. Sutton SignWriting is a writing system for human language. The complete written sign is not surrounding document layout; it is a bounded written-language text element internal to the writing system. For music, it may be reasonable for Unicode to encode useful symbols while leaving score-preserving structure to a higher-level protocol. For Sutton SignWriting, excluding signbox spatial relation excludes part of the written-language text element itself.

## Why Authored Coordinates Are Not Font Coordinates

A common technical objection is that putting coordinates in text makes font behavior unreliable. That objection applies the wrong model to Sutton SignWriting.

The objection to encoded coordinates assumes that coordinates are merely glyph-positioning instructions. That assumption is false for Sutton SignWriting.

All shaped text involves positioning. In spoken-language scripts, many positioning decisions are supplied by the font: mark attachment, kerning, contextual placement, and other glyph-positioning behavior. Those coordinates express script conventions and typographic rules. The writer of ordinary Latin text does not author the exact position of an acute accent over a letter. The text stores the characters, and the font supplies the conventional placement.

Sutton SignWriting is different. Signbox coordinates are not merely typographic placement rules. They record the writer's authored spatial composition inside the written sign. Different signs may use the same symbols in different authored positions. Those positions are not recoverable from the symbol sequence alone.

So the question is not whether coordinates are involved. Coordinates are involved in both cases. The question is what the coordinates represent and where they belong. For spoken scripts, many coordinates represent conventional glyph positioning and belong in the font. For Sutton SignWriting, signbox coordinates represent authored written content and must be preserved by the production text model and serialization.

The requirement is not that coordinates be encoded as ordinary Unicode characters. The requirement is that coordinates, or equivalent authored spatial relations, be preserved in the production text model and serialization.

A font can draw stored SignWriting data. It cannot supply unstored authored spatial relations without inventing, normalizing, or replacing the writer's composition. Moving authored spatial relations into renderer behavior does not avoid coordinates. It moves authorial information out of the text, where it cannot reliably serve preservation, citation, search, corpus work, datasets, AI workflows, or interchange. Treating SignWriting spatial layout as something the font should construct is therefore not a font-engineering solution. It is a category error about what spatial placement is in this writing system.

## Why The Facial-Diacritic Model Fails As A Production Basis

Any attempt to use the official facial-diacritic model as a Sutton SignWriting production basis depends on a sufficiency claim:

> A written face can be sufficiently represented for production use by a head plus facial marks, and a font or renderer can reconstruct the authored written face from that data.

As a production claim for general Sutton SignWriting facial writing, that claim fails.

The reason is structural. The official model stores component categories and leaves facial construction to rendering rules. A renderer that constructs the face from the mark list must decide ordering, attachment, hierarchy, collision handling, normal arrangements, valid combinations, and what counts as the same face.

Those are not merely graphic engineering decisions. They are orthographic assumptions.

This is the decisive case behind the core argument stated above: the official Unicode sequence omits the authored facial arrangement that production text must preserve.

This is not a demand that users prove a currently canonical facial minimal pair. The problem is that the model discards the authored arrangement needed to evaluate such questions.

For simple or conventional faces, a font may produce a plausible result from a component list. That does not prove production compatibility. A writing system is not defined only by simple cases. Complex, expressive, poetic, pedagogical, experimental, and community-specific faces are exactly where orthographic assumptions are least safe.

## Why A Higher-Level Protocol Does Not Rescue The Official Block

This framing appears regularly in standards and implementation discussions.

A higher-level production model may preserve Sutton SignWriting. That does not rescue the official Unicode block as a production basis.

If a production model preserves ISWA 2010 identity, selected symbols, authored coordinates, sign boundaries, and authored facial arrangement, then that production model is the basis. Any use of Unicode code points for comparison, diagnostics, display experiments, or historical discussion is incidental. Production compatibility comes from the production model, not from the official Unicode facial sequence.

Nor does the official block become a production basis by being treated as a symbol layer completed elsewhere. A production basis is the model that preserves the complete written-sign text element for interchange. If a higher-level protocol supplies sign boundaries, authored coordinates, and authored facial arrangement, then that protocol is the production basis. The Unicode characters may be used incidentally inside that model, but production compatibility comes from the model that preserves the written sign, not from the official block alone.

The common escape route is to say that Unicode can be the symbol layer and a higher-level protocol can add coordinates. That framing fails for facial writing.

First, official Unicode facial marks are nonspacing marks attached to a head. Treating them as independently placeable production symbols imports an orthographic decision: that facial marks are not independent written objects and must be mediated by a head. SignWriting communities have not made that universal decision, and different communities may not make the same decision.

Second, signbox coordinates cannot reach inside a font-constructed face. If a facial mark is rendered as part of a constructed head, placing the whole sequence in the signbox does not let the writer author the mark's position within facial space. The mark's internal placement remains controlled by the font or renderer.

Third, coordinates cannot recover production data that the sequence never stored. If the official sequence preserved only `HEAD + facial marks`, then adding coordinates around that sequence does not restore selected Sutton SignWriting facial symbols or authored facial arrangement. Diagnostic mapping is not production citation.

For facial writing, Unicode facial marks should not be assumed to be valid production symbol identifiers unless they correspond to independently preservable Sutton SignWriting production symbols. The official model does not establish that correspondence.

## Why This Is Not A Font Problem

All visible text depends on rendering. That is not the problem.

The problem is what the stored text gives the renderer.

A better font can improve the appearance of official Unicode SignWriting. It can make simple or conventional faces render plausibly. It may even handle many complex sequences better than current fonts.

That still does not make the official facial sequence production-preserving. The stored sequence gives the font `HEAD + facial marks`. It does not give the font the Sutton SignWriting facial symbols the writer selected or their authored placement in facial space.

For complex faces, the font must decide internal ordering, attachment, hierarchy, collision behavior, normal arrangements, and what combinations count as the same written face. Those decisions may be well engineered, but they are still renderer decisions made after the text has already omitted the authored arrangement.

A better font can draw a better result from the official sequence. It cannot turn an unstored authored facial composition into stored Sutton SignWriting production text.

## Why New Unicode-Native Authoring Still Fails As A Production Basis

This boundary is not only about migration from existing FSW/SWU data.

A new editor could support official Unicode SignWriting for limited Unicode-scoped tasks. A writer might spatially arrange hands, movements, contacts, body symbols, and other written-sign components while using official Unicode characters as identifiers.

The facial model changes the authoring mode. For faces, the writer would not directly arrange production-level facial symbols in authored space. The writer would add facial marks to a head and see what a particular font or renderer constructs.

If the rendered face is simple or conventional and matches the writer's intention, the problem may remain hidden.

When the intended face is complex, the writer's control becomes indirect: choose marks, change mark order, accept or avoid a particular renderer's behavior, or compromise when the renderer cannot construct the intended face.

Some arrangements may be structurally unavailable. The official model treats facial marks as nonspacing marks attached to a head. A facial mark without a visible face is treated as an exceptional invisible-head case in the proposal, not as a general coordinate-bearing facial symbol that the writer can place freely.

That is renderer-dependent facial authorship. The written text does not independently preserve the authored facial composition. It preserves a sequence that one implementation may render acceptably and another may not.

A Unicode-native editor can therefore support limited official-Unicode workflows. It does not make the official facial-diacritic model a general production authoring model for Sutton SignWriting facial writing.

## Why Conformance Tests Do Not Settle The Production Boundary

Readers may encounter the suggestion that the official Unicode facial model should be tested against a public conformance suite before being rejected for production use.

A public conformance suite may be useful for researchers, implementers, or critics who want to demonstrate particular failures of the official Unicode facial model. It is not the correct practical path for Sutton SignWriting production communities.

The reason is asymmetry. A conformance suite can show that a model fails when it cannot preserve selected examples. It cannot prove that the model is orthographically adequate for a living writing system. Passing a selected suite would only show that the selected examples work. It would not show that the model can support future community distinctions, local practices, pedagogical uses, poetic writing, expressive forms, or complex facial arrangements that may become important years later.

Community-developed orthography takes time. Different signing communities may make different decisions about which facial distinctions are meaningful, optional, conventional, local, poetic, pedagogical, or erroneous. A text model for production use should preserve authored facial composition before those decisions are finalized. It should not require communities to prove in advance every distinction they may later need.

The purpose of preserving authored facial arrangement is not to declare every placement difference meaningful in advance. It is to keep the written evidence available while communities decide what those differences mean. If the text model discards the arrangement first, later communities cannot compare, argue over, normalize, reject, or standardize the authored forms as text. The orthographic question has been pre-decided by omission.

For that reason, a conformance suite is at most a diagnostic tool. It is not a productive requirement for communities that already reject the official Unicode facial model on structural grounds. The structural boundary is already sufficient: the official model represents facial writing as `HEAD + facial marks`; those marks are not independently preserved as coordinate-bearing Sutton SignWriting production symbols; and their placement within the head is supplied by the font or renderer rather than stored as authored facial arrangement.

The practical path is not to build production work around the official Unicode block and then test whether it can be made adequate. The practical path is to state the boundary clearly: do not use the official Unicode block as the basis for Sutton SignWriting production work.

## Production Path

The production path is preservation-first.

Use FSW/SWU, Sutton SignWriting-compatible tooling, or an equivalent coordinate-preserving production model when the task involves:

- complete written signs
- production authoring
- migration from existing Sutton SignWriting data
- production citation
- dictionaries and lexical databases
- corpora and archives
- education and publication
- search, sorting, rendering, and revision
- datasets, AI, and machine-learning workflows
- long-term preservation

The key property is not the name FSW or SWU. The key property is preservation of selected symbols and authored spatial relations, including authored facial arrangement.

Any particular implementation can still be evaluated for normalization, rounding, coordinate handling, rendering consistency, and round-trip behavior. That is an ordinary implementation audit. It is different from trying to rescue a model that has no text-layer field for authored facial arrangement in the first place.

## What The Official Unicode Block Can Serve

The official Unicode block can be discussed as a Unicode-scoped character-encoding artifact. It can serve:

- Unicode-model documentation
- standards history
- implementation audits of the official block or Noto-style font path
- compatibility warnings and loss analysis
- limited display experiments
- research explicitly scoped to what Unicode encoded

Those are real Unicode-scoped uses. They are not production-basis uses for Sutton SignWriting. Their value is in understanding, auditing, documenting, or warning about the Unicode model.

Noto Sans SignWriting demonstrates that a public font path for the official Unicode approach exists. It does not demonstrate audited production readiness, lossless migration from FSW/SWU, renderer-independent facial authoring, or compatibility across independent implementations.

Do not treat missing adoption of the official Unicode block as evidence that Sutton SignWriting lacks production use. The production path exists; it is not the official Unicode block.

## Implementation Claims Can Create Production Confusion

Supporting the official Unicode SignWriting block is not wrong when the task is Unicode-scoped. Operating systems, fonts, libraries, distributions, and platforms may have legitimate reasons to expose official Unicode SignWriting characters.

The risk is the claim made from that support.

The gap between "official Unicode SignWriting support" and "Sutton SignWriting production text support" is not always visible from inside an implementation task. A developer may correctly add support for official Unicode characters while never intending to make a claim about Sutton SignWriting production text.

But implementation claims travel. A platform or distribution may describe that work as SignWriting support. That claim may then be cited as evidence that Unicode is the production path for Sutton SignWriting. From there, writers, educators, archivists, dataset builders, and platform maintainers can be pushed toward a model that does not preserve what writers authored.

That confusion harms the production community even when the implementation was well-intentioned. A platform can correctly implement official Unicode characters and still increase confusion unless it clearly states what is and is not being supported.

The boundary is therefore practical: implement official Unicode SignWriting if the task is Unicode-scoped, but do not market, document, or route it as production support for Sutton SignWriting.

## Durable Boundary

This boundary is durable because the issue is not a missing font feature, a missing conformance suite, or a missing external coordinate layer. The issue is the encoded facial model itself.

The official Unicode facial model already chose a head-plus-mark abstraction. Once that model is encoded and documented as the official Unicode representation, later implementation improvements cannot make the original sequence preserve authored facial arrangements it never stored.

Better fonts may improve display. Conformance tests may document behavior. A later higher-level protocol may define a separate production-preserving model. None of those changes would make the current official facial-diacritic sequence a production-preserving Sutton SignWriting facial-writing model.

For this boundary to change, there would need to be a new, community-vetted, production-preserving SignWriting encoding or model that preserves selected symbols, authored coordinates, sign boundaries, and authored facial arrangement. That would be a new production basis, not an ordinary repair of the existing facial-diacritic model.

Existing Unicode characters are not going away. A future model might work around them, supersede them for production purposes, or define a separate production-preserving path. But the current official facial-diacritic sequence would remain what it is: a Unicode-specific abstraction, not a production-preserving Sutton SignWriting facial-writing model.

Official Unicode stability is Unicode stability. It is not production stability for Sutton SignWriting. A stable Unicode-scoped artifact can still be structurally inadequate as a production text model.

## Common Misreadings

### "A Complete Sign Is Just Layout"

It is not.

A complete Sutton SignWriting sign has a rendered appearance, but it is not reducible to appearance or surrounding document layout. It is a written-sign text element: a bounded written object composed from selected symbols and authored spatial relations.

Font style, stroke thickness, scale, color, antialiasing, and typographic variation belong to rendering. Selected symbols, sign boundaries, authored spatial relations, and authored facial arrangement belong to the written object.

Calling the complete sign "layout" does not settle the question. Some layout is formatting. Some spatial relation is writing-system structure. In Sutton SignWriting, authored spatial relation can belong to the written sign itself. A production text model must preserve that structure before a renderer draws the visible forms.

### "Unicode Can Be The Symbol Layer And FSW Can Be The Layout Layer"

That is wrong for production facial writing.

The official facial model does not preserve independently placeable Sutton SignWriting facial symbols. It stores a head plus nonspacing facial marks whose internal arrangement is supplied by rendering. A production model may use its own symbol identifiers and authored coordinates, but then that production model is the basis, not the official Unicode facial sequence.

### "A Higher-Level Protocol Can Add Coordinates"

Coordinates can only preserve data that exists.

If the Unicode facial sequence preserved only `HEAD + facial marks`, then adding coordinates around that sequence does not restore selected Sutton SignWriting facial symbols or authored facial arrangement. If the mark's position inside the head is supplied by the font, the writer has not authored that facial arrangement as text.

### "A Second Stage Could Complete Unicode SignWriting"

This argument may appear in discussions of future Unicode work or higher-level protocols.

Not as a production basis for facial writing.

The theoretical second stage is not a current production path, and it would not repair the facial boundary identified in this note. The official facial model already chose `HEAD + facial marks`. Later signbox coordinates cannot make those marks independently authored production facial symbols, and they cannot recover facial arrangement the sequence never stored.

A future higher-level protocol could define a separate production model that preserves selected symbols, authored coordinates, sign boundaries, and authored facial arrangement. But then that production model is the basis. The official Unicode facial sequence remains a Unicode-specific abstraction, not a production-preserving Sutton SignWriting facial-writing model.

### "A Conformance Suite Could Prove Whether Unicode Works"

A conformance suite can prove failure. It cannot prove future orthographic adequacy.

Passing a selected suite would not prove that the official model can support future community distinctions, local practices, poetic uses, pedagogical forms, or complex facial arrangements that have not yet been standardized.

### "The Unicode Block Is Still Useful As A Sutton SignWriting Production Citation Layer"

It is not.

Unicode can cite Unicode SignWriting characters. That is not the same as citing every Sutton SignWriting production symbol or written object. ISWA 2010 remains the Sutton SignWriting production symbol repertoire. Production citation belongs to the production model.

### "Official Unicode Support Means SignWriting Has Production Unicode Support"

It does not.

Official Unicode support means Unicode encoded a Unicode-specific model. It does not mean Unicode encoded a production-compatible Sutton SignWriting text model.

## What This Boundary Note Does Not Claim

This boundary note does not claim:

- that existing Unicode characters should be removed or renamed
- that FSW or SWU are official Unicode SignWriting
- that SWU adoption by itself proves official Unicode inadequacy
- that every facial arrangement difference is canonical spelling
- that every SignWriting use case must use the Sutton SignWriting production stack
- that the official Unicode block has no value as a Unicode-scoped artifact
- that research into the Unicode model is invalid

It does claim:

> The official Unicode SignWriting encoding is a Unicode-scoped character repertoire and Unicode-specific composition model. It is not the Sutton SignWriting production symbol repertoire, not the Sutton SignWriting production text model, and not a production basis for complete written signs. Its facial-diacritic model is not production-compatible as a representation or general authoring model for Sutton SignWriting facial writing.

## Closing

The practical next step is not to build production work around the official Unicode block and then test whether it can be made adequate.

The practical next step is community clarity: route production work around the official Unicode facial model. Use FSW/SWU, Sutton SignWriting-compatible tooling, or an equivalent coordinate-preserving production model for Sutton SignWriting.

Protecting writers means keeping production claims tied to models that preserve what writers authored.

Treat the official Unicode block as a Unicode-scoped artifact, not as the text foundation for SignWriting.

## Sources And Evidence Anchors

- [Unicode 17 Core Specification, Chapter 2](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-2/)
- [Unicode 17 Core Specification, Chapter 21](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-21/)
- [Unicode Character Encoding Stability Policies](https://www.unicode.org/policies/stability_policy.html)
- [OpenType GPOS - Glyph Positioning Table](https://learn.microsoft.com/en-us/typography/opentype/spec/gpos)
- [L2/12-321 / N4342 SignWriting proposal](https://www.unicode.org/L2/L2012/12321-n4342-signwriting.pdf)
- [L2/17-255 Script ad hoc recommendations](https://www.unicode.org/L2/L2017/17255-script-ad-hoc.pdf)
- [L2/17-282 SignWriting design options](https://www.unicode.org/L2/L2017/17282-signwriting-design-aux.pdf)
- [L2/17-362 UTC #153 minutes](https://www.unicode.org/L2/L2017/17362.htm)
- [Noto Sans SignWriting repository](https://github.com/notofonts/sign-writing)
- [ISWA 2010 Alphabet Viewer](https://steveslevinski.me/#page/iswa-alphabet)
- [FSW and SWU](https://doi.org/10.5281/zenodo.20272667)
- [Formal SignWriting series](https://doi.org/10.5281/zenodo.20074767)

Title-only entries below are companion artifacts in released platform series. Use the linked series DOI records to locate the current published versions.

- *Chronology and Record* - companion artifact in the [Unicode and SignWriting series DOI record](https://doi.org/10.5281/zenodo.20075119)
- *Formal SignWriting in Practice* - companion artifact in the [Formal SignWriting series DOI record](https://doi.org/10.5281/zenodo.20074767)
- *Searching Signed Text* - companion artifact in the [Formal SignWriting series DOI record](https://doi.org/10.5281/zenodo.20074767)
