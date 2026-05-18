# Unicode Overview

**Current position and why the issue keeps returning**

The current official Unicode SignWriting encoding is not enough for the Sutton SignWriting production ecosystem.

That is not because Unicode has no SignWriting symbols.

It is because the official model does not preserve stable symbol identity cleanly across the full system, and it does not provide a compatible model for written signs.

## Current position

The Sutton SignWriting Resources currently hold that:

- the official Unicode SignWriting encoding, introduced in Unicode 8.0.0 and maintained in later Unicode versions, is not currently a compatible production replacement for the established FSW/SWU Sutton SignWriting production ecosystem
- the official model does not preserve stable symbol identity cleanly across the full ISWA layer
- the main unresolved issue is spatial composition
- sorting and collation are also not adequate
- production-ready tools, fonts, and datasets cannot simply be moved to the official encoding without loss or redesign
- FSW remains the main production encoding in practice
- SWU remains the Unicode-oriented isomorphic representation supported by the Sutton SignWriting Resources

The existing Sutton SignWriting ecosystem already carries too much real data, software, publishing, and international work to accept a nominal standard that breaks the ecosystem it claims to support.

The compatibility line used here is a production-compatibility line: whether the model can carry current Sutton SignWriting data, tools, sorting, rendering, and publication practice without loss or redesign. Other observers may weight the character-layer achievement differently, but that does not remove the production gap.

## Why this issue keeps returning

The issue keeps returning because many people reasonably assume that once Unicode encodes a script, the script problem is solved.

That assumption does not hold here.

Unicode encoded a SignWriting block, but it did not preserve the full symbol model cleanly, and it did not produce a compatible practical model for written signs.

There is a difference between naming characters, preserving writer-selected symbols, and encoding complete written signs.

That difference is why the issue keeps returning in:

- standards conversations
- developer questions
- Wikimedia support discussions
- package and library design
- public assumptions about whether the SignWriting problem has already been solved

It also returns because the official Unicode path became visible enough to shape public expectations, even though the deeper writing-system issues remained unresolved.

## What the official encoding does cover

The official Unicode SignWriting block covers:

- base characters
- fill modifiers
- rotation modifiers

That means it can name much of the symbol inventory at the base/fill/rotation character layer.

It does not mean that the full symbol model remains stable and writer-selected across the whole system.

It does not, by itself, provide a compatible solution for:

- full stable symbol identity across the facial system
- full written sign representation
- stable spatial composition
- direct compatibility with the existing Sutton SignWriting datasets
- clean migration of production fonts and tools
- straightforward sorting and collation

In the facial area, the official diacritic model introduces a deeper break.

Instead of simply preserving the writer's selected facial symbols and their authored placement, the model asks the writer for a sequence that the font then interprets and arranges into a rendered face.

That pushes part of symbol formation into font behavior and designer interpretation.

It also means that the official model does not merely fall short at the written-sign level.

It also destabilizes symbol identity at part of the symbol level.

It also leaves a more basic question unresolved:

how a written SignWriting word should be encoded so that it remains faithful to the writing system and usable in software

That question is where the gap between symbol encoding and writing support becomes most obvious.

## The practical difference

The difference can be stated simply:

- **official Unicode SignWriting** names much of the symbol block at the character layer, but does not preserve the full symbol model cleanly
- **Formal SignWriting** names and structures written signs

The writing system in practice needs more than a symbol block.

It needs a stable way to represent:

- sequence when sequence is written
- spatial composition when composition is written
- interchange with existing datasets
- search, sorting, rendering, and software processing

That is why the real disagreement is not best framed as:

- Unicode versus no Unicode

The better framing is:

- naming characters without fully preserving writer-selected symbols
- versus encoding complete written signs in a usable compatible way

That framing is more honest and more useful than treating the issue as personal resistance to Unicode itself.

## Why FSW and SWU still matter

FSW is still the true production encoding of the Sutton SignWriting Resources.

It is ASCII, durable, practical, and independent of the limits of official Unicode SignWriting.

SWU is the Unicode-oriented isomorphic representation used by the Sutton SignWriting Resources.

It makes the two-part word highly visible in one-dimensional text:

- a sequence of symbols
- followed by symbols with coordinates

That representation is currently usable not only for interchange and inspection, but also for AI and dataset work when enough data is available.

Its usefulness for AI and dataset work comes from preserving the Formal SignWriting two-part word structure in a Unicode-oriented form, with sign boundaries and symbol-coordinate structure still available for processing.

This is also why SWU should not be confused with official Unicode SignWriting.

They are not the same design.

That distinction should stay explicit whenever a reader sees the word "Unicode" and assumes all Unicode-oriented SignWriting work is one thing.

## Why the disagreement is not only about fonts

It is common to ask whether this is mainly a rendering problem.

It is not.

Better fonts alone do not solve:

- the facial-diacritic model, where font behavior mediates part of symbol formation
- the lack of a workable spatial composition model in official Unicode SignWriting
- incompatibility with existing encoded datasets
- sorting and collation problems
- required overrides and custom behavior in tools
- the gap between a symbol inventory and real written-word workflows

The distinction matters because a very good font can make an incomplete model look more complete than it really is.

That is part of why later public visibility increased confusion instead of reducing it.

This is also why the question cannot be reduced to "Unicode solved symbols and only writing remains."

At least in the facial system, the official model does not preserve symbol identity in a way that remains cleanly compatible with Formal SignWriting.

## The scale of the practical ecosystem

The Sutton SignWriting ecosystem already includes:

- real public websites
- real software tools
- real fonts
- real dictionaries
- real published materials
- substantial corpora and dictionaries documented elsewhere in the v1.0.0 release

Those assets are the standard by which any Unicode path should be judged.

The question is not whether another design can be imagined.

The question is whether it can carry real writing, real tools, and real data without breaking them.

The ecosystem should be judged as a real production environment, not as an unimplemented thought experiment.

## What would count as progress

Progress with Unicode would not require immediate agreement on everything.

It would require:

- acknowledgment that the current official Unicode SignWriting encoding is not sufficient for compatible production use
- acknowledgment that the facial-diacritic model does not preserve stable writer-selected symbol identity cleanly
- acknowledgment that spatial composition remains unresolved
- honest technical discussion of collation, compatibility, and migration
- a concrete path for renewed discussion only if meaningful technical and institutional interest actually exists

That is the minimum honest starting point.
