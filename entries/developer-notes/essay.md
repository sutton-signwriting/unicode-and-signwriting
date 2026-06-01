# Developer Notes

**Production encoding guidance and compatibility cautions**

## Current recommendation

For current Sutton SignWriting software and data work:

- use **FSW** as canonical production text
- use **SWU** when you need a Unicode-oriented isomorphic form
- use **ISWA 2010** as the symbol reference layer
- do not assume the official Unicode SignWriting model is a drop-in replacement for the Sutton SignWriting Resources

If the production judgment changes in the future because Unicode support genuinely becomes sufficient and compatible, then the recommendation can change too.

## Why FSW remains canonical

FSW remains the most practical canonical encoding because it is:

- ASCII
- stable for storage and transfer
- practical for regex and parsing
- already integrated into production tools and datasets
- independent of official Unicode SignWriting limitations

If a workflow already uses FSW successfully, that is not a temporary embarrassment.

It is the current production reality.

Production reality should outweigh theoretical convenience when the two diverge.

It also means developers should resist pressure to migrate simply because a standards label looks cleaner on paper.

## Why SWU matters

SWU matters because it gives an isomorphic Unicode-oriented view of the same model.

It is useful for:

- Unicode-oriented inspection
- one-dimensional display of encoded sign structure
- interchange where Unicode text is expected
- current AI and dataset workflows that benefit from a more visibly structured Unicode string

SWU is not official Unicode.

It is the Unicode-oriented representation supported by the Sutton SignWriting Resources.

This distinction is one of the main things developers tend to miss on first contact.

## What not to assume about official Unicode SignWriting

Do not assume that the official Unicode SignWriting model:

- names characters in a way that automatically preserves production-level symbol identity
- preserves the full ISWA symbol model cleanly
- can represent full written signs in a compatible way
- can replace FSW or SWU without redesign
- can sort or collate the way production workflows need
- can reuse the Sutton SignWriting production fonts without mismatch
- can solve layout by adding a font alone

It encodes much of the character set at the base/fill/rotation character layer.

That is not the same as preserving production-level writer-selected symbols.

It also does not currently provide a complete compatible written-sign solution.

In the facial system, the model is not simply "writer selects symbols and places them."

Instead, a sequence of Unicode facial mark categories is interpreted by the font and arranged into a rendered face.

That means the official facial model preserves Unicode facial mark categories, but not production-level writer-selected facial-symbol identity and authored facial arrangement in the FSW/SWU sense.

That means a developer should not infer from the existence of official characters that a full application stack is already settled.

This is the same mistake many outsiders make at the public level, but it causes more damage when it appears inside software decisions.

## Why this is not only a rendering problem

Rendering is part of the issue, but not the main issue.

The larger problem is interoperability.

Developers need:

- stable production-level writer-selected symbols
- stable production-level symbol identity
- reliable storage
- reliable interchange
- searchability
- predictable sorting
- stable relation to existing datasets

Fonts alone do not provide those things.

They also do not settle which production-level facial forms and authored arrangements are preserved when the model pushes composition into font interpretation.

This is the practical reason developer discussions drift quickly from fonts into encoding and conversion.

## Practical storage advice

If you are designing a current system:

- store FSW internally unless you have a strong reason not to
- derive SWU when you need Unicode-oriented display or export
- treat ISWA symbol identity as stable and shared
- treat rendering and style as a separate layer
- keep conversion routines explicit and testable

If you are exposing multiple encodings in one codebase, make the boundaries visible:

- what is canonical
- what is interchange
- what is legacy or compatibility support
- what is experimental

## Practical migration advice

If someone asks whether to migrate existing Sutton SignWriting data to official Unicode SignWriting, the safe answer is:

not without a clear compatibility study first

Before any migration, ask:

- are production-level writer-selected symbols preserved across the full system
- are production-level facial-symbol identity and authored facial arrangement preserved in the FSW/SWU sense
- can the full written sign be represented without loss
- can existing sorting be preserved
- can current fonts and renderers still work
- can search and parsing stay stable
- can round-tripping be guaranteed

If the answer is not clearly yes, migration is not yet justified.

The burden of proof should stay on the migration, not on the existing production stack.

## Practical AI and data advice

For AI and larger dataset work, the key constraint now is less the existence of a usable encoding and more the size and quality of the data.

In current practice:

- FSW remains a strong canonical form
- SWU is also usable for AI-oriented data preparation and model input

SWU is useful in those contexts because it preserves the Formal SignWriting two-part word structure in a Unicode-oriented form: sequence information, signbox symbols, coordinates, and sign boundaries remain available to software.

This shows the Sutton SignWriting production stack is still computationally relevant.

Unicode incompleteness is still a serious standards problem, but it is not the same thing as computational impossibility.

## Bottom line

In practice:

- **FSW** for canonical production text
- **SWU** for supported Unicode-oriented interchange and inspection
- **official Unicode SignWriting model** only with caution and only with a clear understanding that it does not currently replace the Sutton SignWriting production stack

## A note about `@sutton-signwriting/unicode8`

The package `@sutton-signwriting/unicode8` is still useful and worth linking for developers.

Its role is to process official Unicode SignWriting characters, from the model introduced in Unicode 8.0.0, where they exist and to bridge them with FSW and SWU inside JavaScript tooling.

Useful links:

- [Source](https://github.com/sutton-signwriting/unicode8)
- [Documentation](https://sutton-signwriting.github.io/unicode8/)
- [Distribution](https://unpkg.com/browse/@sutton-signwriting/unicode8/)
- [Issues](https://github.com/sutton-signwriting/unicode8/issues)

Real software still has to deal with official Unicode SignWriting, even when it is not the preferred production path.

Describe such packages as:

- compatibility tooling
- bridge tooling
- inspection tooling
