# Text Architecture And Written Signs

**Why complete written signs require authored spatial data**

## Purpose

This companion explains the text-architecture point behind the Unicode and SignWriting compatibility position.

The issue is not only that the current official Unicode SignWriting model is inconvenient for current tools.

The issue is that the official Unicode SignWriting block encodes much of the symbol repertoire while leaving the essential spatial organization of complete written signs outside the official model.

That distinction matters because SignWriting's two-dimensional signbox is written content, not decoration.

## The Universality Gap

Unicode presents itself as a universal character encoding for written languages and writing systems.

The Unicode core specification also describes Sutton SignWriting as a system in which visually iconic basic symbols are arranged in two-dimensional layout to form written signs, and it states that this spatial arrangement is an essential part of the writing system.

That creates the central tension:

- the official Unicode model recognizes SignWriting's symbol layer
- it also acknowledges that spatial arrangement is essential
- but it places that spatial arrangement beyond the scope of the Unicode Standard

This is not a minor implementation footnote.

If the essential written-unit organization of a natural-language writing system is outside the encoding model, then the official encoding is incomplete for that writing system as text.

The careful claim is not that Unicode is useless or that the SignWriting block has no value.

The careful claim is:

> The official Unicode SignWriting block is a real character-level recognition of SignWriting symbols, but it does not fulfill the complete written-sign encoding task for Sutton SignWriting.

That is why the earlier Unicode block can be politically and historically valuable while still technically incomplete.

It names and stabilizes many symbols.

It does not encode complete written signs in the way the production ecosystem requires.

## Definitional Completeness Comes Before Routine Compatibility

A common mistake is to judge an encoding mainly by whether ordinary text tools immediately produce every meaningful linguistic result.

FSW and SWU can work well with ordinary text-processing tools, especially because their written-sign structure is encoded in the text.

But tool convenience is not the primary test.

Many scripts and notational systems encoded in Unicode require specialized shaping, rendering, parsing, collation, or scholarly support before general-purpose software can handle them well.

The primary test is whether the text model preserves the written units and their meaningful distinctions.

The primary encoding question is definitional:

- are the stable textual units defined?
- are their identities durable?
- can the writing system's meaningful distinctions be preserved?
- can complete written units be stored and exchanged without losing what makes them written units?

For SignWriting, that means the encoding must preserve not only symbol identity, but also authored spatial relation inside the signbox.

FSW and SWU satisfy that definitional need for the Sutton production ecosystem because coordinates are in the text string.

They are not external metadata.

They are part of the written-unit model.

## Rendering Requirements Do Not Disqualify Text

Another common mistake is to treat specialized rendering as evidence that SignWriting is not plain text.

That standard would fail many accepted writing systems.

Complex scripts routinely depend on shaping engines, font tables, positioning rules, contextual substitution, mark attachment, or script-specific layout behavior.

Arabic, Indic scripts, Tibetan, and many other scripts are not disqualified from plain text because visible output requires more than placing one glyph after another.

The architectural question is whether the information needed for correct rendering is present in the text model and can be interpreted by a defined rendering layer.

In FSW and SWU, the coordinates needed for signbox composition are encoded directly.

A renderer, shaping layer, specialized font path, or SVG generator can read those coordinate values and produce the visible sign.

That is compatible with the general text architecture:

```text
encoded text -> shaping/rendering process -> visible output
```

The difference is that SignWriting's spatial relations are more open-ended than the attachment and shaping patterns of many linear scripts.

That openness is not a defect in the encoding.

It reflects the writing system.

For a script where spatial relation is authored content, writer-specified coordinates are the correct textual representation.

## Why Coordinates Belong In The Text

If coordinates were treated as external layout metadata, a written sign would be split between text and presentation.

That would make the signbox unstable.

It would also blur the boundary between:

- the written form
- downstream rendering
- optional styling
- page layout

FSW and SWU avoid that problem by putting the signbox structure in the text itself.

The text carries:

- symbol identity
- signbox marker
- coordinate values
- symbol placement
- optional sequence information when present

Rendering remains downstream.

The canonical text still carries the written sign.

This is the same basic architectural boundary used across the Formal SignWriting series:

> canonical text first, rendering second, optional styling later.

## What This Changes In The Unicode Argument

This architecture note sharpens the Unicode critique.

The strongest argument is not:

> Official Unicode SignWriting is bad because standard text tools do not handle it well.

The stronger argument is:

> The official Unicode SignWriting model is incomplete as a production text model because it does not define complete written signs as text, even though spatial arrangement is essential to the writing system.

The strongest defense of FSW and SWU is not:

> They are convenient workarounds.

The stronger defense is:

> They are complete plain-text encodings of the Sutton SignWriting model because they preserve symbol identity and authored signbox coordinates in the text stream.

That is the central architectural point.

The Unicode gap is a limitation of the official model's scope for SignWriting, not a failure of SignWriting to be textual.

## Standards-Facing Use

For standards-facing use, this point should be translated carefully.

Avoid broad claims that Unicode is simply linear or that Unicode cannot handle complex layout.

Unicode already supports many scripts that require shaping, directionality, mark positioning, and higher-level layout behavior.

The narrower, stronger claim is:

> The current official Unicode SignWriting model encodes character-level resources but leaves the essential spatial organization of written signs outside the standard. A compatibility review should distinguish default text-tool behavior from definitional completeness. FSW and SWU remain important because they preserve the complete written-unit model, including authored coordinates, as text.

That framing keeps the critique technical.

It also avoids letting the discussion collapse into whether ordinary string functions can process SignWriting meaningfully.

## Source Anchors

The central source points are:

- [Unicode 17 Core Specification, Chapter 21](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-21/), especially its Sutton SignWriting discussion of two-dimensional layout, spatial spelling, and higher-level protocols.
- [Unicode Technical Introduction](https://www.unicode.org/standard/principles.html), for the general character-encoding frame.
- [FSW and SWU](https://doi.org/10.5281/zenodo.20272667), in the Formal SignWriting series, for the coordinate-bearing FSW/SWU production model.
- [Formal SignWriting series](https://doi.org/10.5281/zenodo.20074767), for the broader technical account of signbox text, rendering, search, and production interchange.
