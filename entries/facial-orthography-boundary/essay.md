# Facial Orthography Boundary

**Why official Unicode SignWriting is not a production basis for facial writing**

Status note: This is an author-stewardship technical boundary note prepared for public, implementation, preservation, and SignWriting community discussion. It is not an official Unicode publication, Wikimedia position, or standards-body decision.

This note is for people choosing text models, tools, corpora, datasets, archives, publications, educational workflows, and AI workflows for Sutton SignWriting.

This note is not asking Unicode to change course. It is warning SignWriting users, archivists, implementers, educators, publishers, corpus builders, and dataset builders not to mistake official Unicode encoding for a production-preserving Sutton SignWriting text model.

Recognize the Unicode artifact. Do not use it as the production basis. Protect the writers.

## Verdict

The official Unicode SignWriting block should not be used as the basis for Sutton SignWriting production text.

The official Unicode block is a Unicode-scoped character-encoding artifact. It defines an official Unicode character repertoire and Unicode-specific composition model. It is not the Sutton SignWriting production symbol repertoire, not the Sutton SignWriting production text model, and not a production foundation for complete written signs.

The facial-diacritic model is the decisive failure point. Official Unicode represents facial writing as:

> `U+1D9FF SIGNWRITING HEAD` plus nonspacing facial marks.

That model is not a partial version of Sutton SignWriting production facial writing. It is a different model. It stores a head plus component categories and asks the renderer to construct the face. It does not store the Sutton SignWriting facial symbols the writer selected or the authored facial arrangement.

## Production Requirement

Sutton SignWriting production text must preserve the written sign the author composed.

For facial writing, that means preserving:

- the Sutton SignWriting facial symbols the writer selected
- authored facial arrangement
- spatial distinctions that may carry written meaning
- enough information for rendering, search, sorting, citation, archiving, corpus work, datasets, AI, machine-learning workflows, publication, and production reuse
- the capacity for communities to develop facial orthography over time

ISWA 2010 remains the Sutton SignWriting production symbol repertoire. FSW/SWU preserve selected ISWA 2010 symbols and authored spatial relations in the working Sutton SignWriting ecosystem. Other production models are possible, but only if they preserve the same necessary data: selected symbols, sign boundaries, authored spatial relations, and authored facial arrangement.

Production compatibility is not a status claim. It is a preservation claim.

## What Unicode Encoded

The official Unicode SignWriting block names Unicode characters, assigns code points, and defines a Unicode-specific model for representing some SignWriting material. That is a real standards artifact.

That status should not be inflated. Official Unicode SignWriting code points are useful for talking about official Unicode SignWriting code points. That is not the same as being useful for working with Sutton SignWriting production text.

The Core Specification describes SignWriting symbols as arranged in two-dimensional layout to form signs and treats that arrangement as a higher-level protocol outside Unicode. The L2/12-321 / N4342 proposal also states that spatial organization is spelling and that the writer decides the symbols and their placement.

For facial writing, however, official Unicode did not merely leave placement for later. It encoded a facial abstraction:

```text
HEAD + facial marks
```

The proposal describes `U+1D9FF SIGNWRITING HEAD`, combining face characters, and fill modifiers that subcategorize those marks. It says diacritics may occur after the head with eye and mouth diacritics combined in the sequence.

That is a categorical sequence model. It contains no coordinate field, no relative-placement field, and no authored-arrangement field for the facial components. Sequence order may identify which marks occur after the head. It does not preserve the writer's spatial arrangement of the written face.

The objection here is not to Base+Fill+Rotation triplet mapping for individual Sutton SignWriting symbols in general. It is to the official facial head-plus-diacritic abstraction, which does not preserve authored facial arrangement as production text.

The same proposal treats facial marks without a visible head as an exceptional invisible-head case and says that rendering face modifiers without a face is "never used in actual sign languages." That is not a neutral preservation rule. It is an orthographic assumption about what facial writing will need to express.

That kind of statement does not merely describe an implementation detail. It narrows the expressive space before signing communities have had the written evidence needed to decide their own facial conventions.

## Why The Facial Model Fails

The official facial model makes a sufficiency claim:

> A written face can be sufficiently represented by a head plus facial marks, and a renderer can reconstruct the written face from that data.

As a production claim for general Sutton SignWriting facial writing, that claim fails.

The reason is structural. The official model stores component categories and leaves facial construction to rendering rules. A renderer that constructs the face from the mark list must decide ordering, attachment, hierarchy, collision handling, normal arrangements, valid combinations, and what counts as the same face.

Those are not merely graphic engineering decisions. They are orthographic assumptions.

The argument is direct:

1. Sutton SignWriting production facial writing preserves selected Sutton SignWriting facial symbols and authored facial arrangement as part of the written object.
2. In SignWriting, space can carry authored meaning.
3. The official Unicode facial-diacritic model stores `HEAD + facial marks`; it does not store the authored facial arrangement as text.
4. Missing authored arrangement cannot be recovered from a sequence that never stored it.
5. Therefore the official Unicode facial-diacritic model should not be used as a production-compatible representation, production identifier layer, or general production authoring model for Sutton SignWriting facial writing.

This is not a demand that users prove a currently canonical facial minimal pair. The problem is that the model discards the authored arrangement needed to evaluate such questions.

For simple or conventional faces, a font may produce a plausible result from a component list. That does not prove production compatibility. A writing system is not defined only by simple cases. Complex, expressive, poetic, pedagogical, experimental, and community-specific faces are exactly where orthographic assumptions are least safe.

## Why A Higher-Level Protocol Does Not Rescue The Official Block

A higher-level production model may preserve Sutton SignWriting. That does not rescue the official Unicode block as a production basis.

If a production model preserves ISWA 2010 identity, selected symbols, authored coordinates, sign boundaries, and authored facial arrangement, then that production model is the basis. Any use of Unicode code points for comparison, diagnostics, display experiments, or historical discussion is incidental. Production compatibility comes from the production model, not from the official Unicode facial sequence.

The common escape route is to say that Unicode can be the symbol layer and a higher-level protocol can add coordinates. That framing fails for facial writing.

First, official Unicode facial marks are nonspacing marks attached to a head. Treating them as independently placeable production symbols smuggles in an orthographic decision: that facial marks are not independent written objects and must be mediated by a head. SignWriting communities have not made that universal decision, and different communities may not make the same decision.

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

## Why New Unicode-Native Authoring Still Fails

This boundary is not only about migration from existing FSW/SWU data.

A new editor could support official Unicode SignWriting for limited Unicode-scoped tasks. A writer might spatially arrange hands, movements, contacts, body symbols, and other written-sign components while using official Unicode characters as identifiers.

The facial model changes the authoring mode. For faces, the writer would not directly arrange production-level facial symbols in authored space. The writer would add facial marks to a head and see what a particular font or renderer constructs.

If the rendered face is simple or conventional and matches the writer's intention, the problem may remain hidden.

When the intended face is complex, the writer's control becomes indirect: choose marks, change mark order, accept or avoid a particular renderer's behavior, or compromise when the renderer cannot construct the intended face.

Some arrangements may be structurally unavailable. The official model treats facial marks as nonspacing marks attached to a head. A facial mark without a visible face is treated as an exceptional invisible-head case in the proposal, not as a general coordinate-bearing facial symbol that the writer can place freely.

That is renderer-dependent facial authorship. The written text does not independently preserve the authored facial composition. It preserves a sequence that one implementation may render acceptably and another may not.

A Unicode-native editor can therefore support limited official-Unicode workflows. It does not make the official facial-diacritic model a general production authoring model for Sutton SignWriting facial writing.

## Why A Conformance Suite Is Not The Path Forward

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

## Durable Boundary

This boundary is durable because the issue is not a missing font feature, a missing conformance suite, or a missing external coordinate layer. The issue is the encoded facial model itself.

The official Unicode facial model already chose a head-plus-mark abstraction. Once that model is encoded and documented as the official Unicode representation, later implementation improvements cannot make the original sequence preserve authored facial arrangements it never stored.

Better fonts may improve display. Conformance tests may document behavior. A later higher-level protocol may define a separate production-preserving model. None of those changes would make the current official facial-diacritic sequence a production-preserving Sutton SignWriting facial-writing model.

For this boundary to change, there would need to be a new, community-vetted, production-preserving SignWriting encoding or model that preserves selected symbols, authored coordinates, sign boundaries, and authored facial arrangement. That would be a new production basis, not an ordinary repair of the existing facial-diacritic model.

Existing Unicode characters are not going away. A future model might work around them, supersede them for production purposes, or define a separate production-preserving path. But the current official facial-diacritic sequence would remain what it is: a Unicode-specific abstraction, not a production-preserving Sutton SignWriting facial-writing model.

Official Unicode stability is Unicode stability. It is not production stability for Sutton SignWriting. A stable Unicode-scoped artifact can still be structurally inadequate as a production text model.

## Common Misreadings

### "Unicode Can Be The Symbol Layer And FSW Can Be The Layout Layer"

That is wrong for production facial writing.

The official facial model does not preserve independently placeable Sutton SignWriting facial symbols. It stores a head plus nonspacing facial marks whose internal arrangement is supplied by rendering. A production model may use its own symbol identifiers and authored coordinates, but then that production model is the basis, not the official Unicode facial sequence.

### "A Higher-Level Protocol Can Add Coordinates"

Coordinates can only preserve data that exists.

If the Unicode facial sequence preserved only `HEAD + facial marks`, then adding coordinates around that sequence does not restore selected Sutton SignWriting facial symbols or authored facial arrangement. If the mark's position inside the head is supplied by the font, the writer has not authored that facial arrangement as text.

### "A Second Stage Could Complete Unicode SignWriting"

Not as a production basis for facial writing.

The theoretical second stage is not a current production path, and it would not repair the facial boundary identified in this note. The official facial model already chose `HEAD + facial marks`. Later signbox coordinates cannot make those marks independently authored production facial symbols, and they cannot recover facial arrangement the sequence never stored.

A future higher-level protocol could define a separate production model that preserves selected symbols, authored coordinates, sign boundaries, and authored facial arrangement. But then that production model is the basis. The official Unicode facial sequence remains a Unicode-specific abstraction, not a production-preserving Sutton SignWriting facial-writing model.

### "A Conformance Suite Could Prove Whether Unicode Works"

A conformance suite can prove failure. It cannot prove future orthographic adequacy.

Passing a selected suite would not prove that the official model can support future community distinctions, local practices, poetic uses, pedagogical forms, or complex facial arrangements that have not yet been standardized.

### "The Unicode Block Is Still Useful As A Production Citation Layer"

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

Treat the official Unicode block as a Unicode-scoped artifact, not as the text foundation for SignWriting.

## Sources And Evidence Anchors

- [Unicode 17 Core Specification, Chapter 21](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-21/)
- [Unicode Character Encoding Stability Policies](https://www.unicode.org/policies/stability_policy.html)
- [L2/12-321 / N4342 SignWriting proposal](https://www.unicode.org/L2/L2012/12321-n4342-signwriting.pdf)
- [Noto Sans SignWriting repository](https://github.com/notofonts/sign-writing)
- [ISWA 2010 Alphabet Viewer](https://steveslevinski.me/#page/iswa-alphabet)
- [FSW and SWU](https://doi.org/10.5281/zenodo.20272667)
- [Formal SignWriting series](https://doi.org/10.5281/zenodo.20074767)

Title-only entries below are companion artifacts in released platform series. Use the linked series DOI records to locate the current published versions.

- *Chronology and Record* - companion artifact in the [Unicode and SignWriting series DOI record](https://doi.org/10.5281/zenodo.20075119)
- *Formal SignWriting in Practice* - companion artifact in the [Formal SignWriting series DOI record](https://doi.org/10.5281/zenodo.20074767)
- *Searching Signed Text* - companion artifact in the [Formal SignWriting series DOI record](https://doi.org/10.5281/zenodo.20074767)
