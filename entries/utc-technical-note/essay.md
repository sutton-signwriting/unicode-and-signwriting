# Draft UTC-Facing Technical Note

**Technical note on compatibility, symbol identity, spatial composition, and next steps**

Status note: This is an author-stewardship technical position note prepared for possible future Unicode-facing discussion. It is not a Unicode Technical Committee document, not a UTC resolution, and not an official Unicode publication.

The Sutton SignWriting Resources regard the current official Unicode SignWriting encoding as insufficient for compatible production use within the established Sutton SignWriting ecosystem.

Prior Unicode encoding work should be understood as a good-faith character-level effort. The critique here concerns production compatibility, symbol identity, spatial composition, sorting, and migration, not the sincerity of past participants.

## Summary

The current official Unicode SignWriting encoding does not fully solve symbols cleanly, and it does not solve written signs.

The core distinction is this:

- naming characters is not the same as preserving stable symbol identity
- preserving stable symbol identity is not the same as encoding complete written signs

The current official encoding can name much of the SignWriting character set at the base/fill/rotation character layer.

It does not provide a workable compatible solution for:

- stable writer-selected symbol identity across the full system
- written signs as they exist in current production use
- spatial composition
- sorting and collation aligned with current practice
- migration from existing data, fonts, and tools without redesign

In the facial system specifically, the official model does not simply preserve the writer's choice of facial symbols and their authored placement in the signbox.

Instead, the writer enters a sequence of facial elements and the font takes on part of the job of arranging them into a rendered face.

That means symbol formation is partly mediated by font behavior and designer interpretation rather than being fixed by a shared writer-selected symbol inventory.

This breaks compatibility at the symbol layer before the larger written-sign problem is even fully considered.

If renewed Unicode-level discussion is pursued, it should begin from a compatibility review rather than from the assumption that migration to the current official encoding is already the expected path.

## Terms

- **Sutton SignWriting**: the writing system and broader technical ecosystem
- **FSW**: Formal SignWriting in ASCII, the main production encoding in practice
- **SWU**: SignWriting in Unicode, the Unicode-oriented isomorphic representation supported by the Sutton SignWriting Resources
- **official Unicode SignWriting**: the current SignWriting encoding standardized in Unicode 8 and later versions

## Current problem

The current problem is not whether Unicode can name SignWriting characters.

It can.

The current problem is whether the official Unicode SignWriting encoding can carry the established Sutton SignWriting production ecosystem without loss, redesign, or incompatible workarounds.

Under the production-compatibility criteria used here, it cannot.

This is an interoperability judgment about what the current official encoding can carry in practice, not about the sincerity of past participants.

The related production-encoding governance question is treated from the Formal SignWriting side in **Encoding Stewardship and Stability**.

## Character naming is not enough

The official Unicode SignWriting block covers:

- base characters
- fill modifiers
- rotation modifiers

That means it can name much of the character set at the base/fill/rotation character layer.

That does not mean:

- the full symbol model remains stable and writer-selected across the whole system
- the facial system has a closed shared inventory comparable to ISWA symbol selection
- written signs can be encoded in a compatible practical way

The standards question cannot stop at character naming.

It also has to ask:

- whether symbol identity remains stable
- whether writers still select symbols directly
- whether written words can be encoded without breaking the writing system

## Symbol identity breaks in the facial system

In the facial system, the official model does not preserve direct writer control over a stable set of selected facial symbols and their authored placement.

Instead, the writer enters a sequence of facial elements that the font interprets and arranges into a rendered face.

That shifts part of symbol formation into font behavior and designer interpretation.

It also means the font can end up deciding more than simple drawing details.

It can affect how facial elements are stacked, grouped, normalized, or spatially resolved, even though those choices can matter to the writing itself.

This is not a small rendering detail.

It means the official model does not merely encode a symbol inventory imperfectly.

It changes how final facial symbols come into being.

There is no closed master list of facial-diacritic combinations that functions as a shared exhaustive inventory in the same way as ISWA symbol selection.

As a result, font implementations are pushed toward copying a previous interpretation or inventing one.

This is why the current official encoding should not be described as though it solved symbols cleanly and only left writing unresolved.

At least in the facial system, it does not preserve stable symbol identity in a way that remains fully compatible with Formal SignWriting.

## Spatial composition remains unresolved

The core writing-system issue is spatial composition.

SignWriting is not only a symbol inventory.

It is a writing system in which the visible written sign depends on spatial composition.

Earlier framing around Unicode SignWriting described a two-stage path:

- first the symbol set
- then an encoding that takes symbols and turns them into signs

The first stage advanced.

The second did not become a workable compatible standard.

The unresolved issue is not merely how to draw a symbol string.

It is how to encode a written sign in a way that remains:

- faithful to the writing system
- processable in software
- compatible with current data

This is the point where the standards question and the software question become the same question.

## Collation and sorting remain unresolved

Sorting and collation are not incidental details.

They affect:

- dictionaries
- corpus order
- search behavior
- software workflows
- interoperability across tools

The problem is not simply that a sort order has not yet been tuned.

The problem is that the current official model does not align cleanly with the established Sutton SignWriting production ecosystem and its practical needs.

Two design choices matter directly here:

- the facial-diacritic model, which moves part of symbol identity into font interpretation
- inherent first fill and first rotation values, which weaken explicit symbol identity and complicate stable sorting

If the facial-diacritic model were removed and explicit first fill and first rotation values were restored instead of being inherent, compatibility and sorting would move much closer to the Formal SignWriting model.

This is why collation should be treated as a signal of deeper incompatibility rather than as a small secondary defect.

## Compatibility with current production use

The current Sutton SignWriting production ecosystem includes:

- real tools
- real websites
- real fonts
- real corpora
- real dictionaries
- real published materials

That ecosystem currently relies on FSW and SWU.

The official Unicode SignWriting encoding does not currently provide a compatible migration path that preserves:

- direct writer-selected symbol identity across the full system
- existing data
- current production tooling
- practical search and sorting workflows
- stable written-sign representation

That should matter to UTC because an encoding standard becomes much more valuable when it can serve as a stable interchange layer for real production use.

Without that, formal standardization risks naming a script without actually serving its living technical ecosystem.

## Why this is not only a font issue

The issue is sometimes framed as though a sufficiently complete font would solve the problem.

That framing is too narrow.

Fonts matter, but the deeper issues remain:

- stable writer-selected facial symbols and authored placement in the facial system
- a shared symbol inventory that does not depend on font-mediated composition
- representation of written signs, not only characters
- compatibility with existing encoded data
- sorting and collation
- workflow and software integration
- the absence of a completed compatible spatial-composition model

Strong fonts can hide structural gaps temporarily.

They cannot remove them.

## Practical position

The practical position of the Sutton SignWriting Resources is:

- FSW remains the main production encoding
- SWU remains the supported Unicode-oriented isomorphic representation
- the official Unicode SignWriting encoding is not currently used as the main production path

That position is not based on refusal to engage Unicode in principle.

It is based on incompatibility in practice.

It is also compatible with continued technical engagement if a serious path opens.

That path would need to begin by acknowledging that the current official model did not fully solve symbols cleanly, and did not solve writing.

## Evidence from current use

The real-world ecosystem is now large enough that compatibility should be judged against production use, not only theoretical possibility.

The current ecosystem includes substantial dictionaries and corpora documented elsewhere in the v1.0.0 release, together with real software, public resources, and published materials.

In addition, current country-level cases such as Brazil and South Korea show that encoded SignWriting is not hypothetical or merely local.

They also show why the standard of evaluation should be real writing and real infrastructure, not only abstract standards elegance.

## Disciplined next step

A disciplined next step would be modest and concrete:

- acknowledgment that current official Unicode SignWriting is not sufficient for compatible production use
- acknowledgment that symbol identity is not preserved cleanly across the full system
- acknowledgment that the facial-diacritic model mediates part of symbol selection and arrangement through font behavior
- acknowledgment that spatial composition remains unresolved
- renewed technical review of compatibility, collation, and migration
- a concrete path for follow-up discussion only if meaningful technical and institutional interest exists

Start with honest technical acknowledgment of the present gap.

## Closing

The current official Unicode SignWriting encoding should not be treated as though it already solved the practical writing-system problem.

It did not fully solve symbols cleanly.

It did not solve the compatible written-sign problem.

In the facial system, it displaced writer-selected symbol identity with font-mediated composition.

That distinction remains the central technical issue.

Everything else depends on whether that distinction is acknowledged clearly.
