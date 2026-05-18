# Compatibility Matrix

**Compact comparison of current encoding paths**

| Question | FSW | SWU | Official Unicode SignWriting |
| --- | --- | --- | --- |
| Names the character set | Yes | Yes | Largely yes |
| Preserves writer-selected symbol identity across the full system | Yes | Yes | Not cleanly |
| Preserves a closed shared symbol inventory in the facial system | Yes | Yes | No |
| Keeps first fill and first rotation explicit | Yes | Yes | No |
| Represents the two-part written word directly | Yes | Yes | No compatible completed model |
| Supports current Sutton SignWriting tool ecosystem cleanly | Yes | Yes, with supported tooling | Not fully |
| Drop-in compatibility with existing datasets | Yes | Supported by conversion and isomorphism | No |
| Sorting and collation aligned with current production practice | Yes, within current ecosystem | Yes, when treated as equivalent to FSW | Not adequately |
| Can serve as current canonical production text | Yes | Supported, but not usually canonical | No |
| Suitable for current AI and dataset workflows | Yes | Yes | Limited and ecosystem-dependent |
| Solves the written-sign problem by itself | Yes, in the current ecosystem | Yes, as equivalent form | No |
| Solves the writing-system problem as text | Yes, in the current ecosystem | Yes, in the current ecosystem | No, character layer only |

Here, "in the current ecosystem" means within the Sutton SignWriting production stack: existing FSW/SWU data, tools, rendering, search, sorting, corpora, dictionaries, and publication workflows.

## What this table is meant to show

The main distinction is not simply:

- Unicode versus non-Unicode

The main distinction is:

- naming characters
- preserving stable writer-selected symbol identity
- encoding written signs in a usable compatible way

The current official Unicode SignWriting encoding reaches the first point much more than the second or third.
