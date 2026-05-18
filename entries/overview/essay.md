# Unicode and SignWriting

*Unicode history, compatibility, and standards-facing discussion*

Unicode questions around SignWriting keep returning, and they are too important to leave scattered across proposals, notes, meeting records, implementation practice, and side remarks in unrelated documents.

The materials are organized around four reader needs:

- developers need practical implementation guidance
- historians and standards readers need chronology and official references
- platform and public-infrastructure readers need a compact explanation of the current gap
- standards readers need a formal technical statement

> the official Unicode SignWriting encoding, introduced in Unicode 8.0.0 and maintained in later Unicode versions, is not currently a compatible production replacement for the established Sutton SignWriting production ecosystem

It does **not** mean:

- Unicode has no SignWriting symbols
- no one has tried to make Unicode support work
- fonts and libraries are irrelevant
- Unicode discussion should never happen again

It **does** mean:

- the current official Unicode SignWriting design does not carry the current Sutton SignWriting production ecosystem cleanly
- the unresolved writing-system issues are larger than character naming alone
- compatibility must be judged against real tools, real corpora, real publishing, and real data exchange
- future Unicode discussion is only worth the effort if it begins from those realities

That incompatibility is not only about fonts.

It also involves:

- writer-selected symbols versus font-mediated facial composition
- missing spatial composition
- sorting and collation problems
- dataset incompatibility
- tool and workflow breakage
- the difference between naming characters, preserving stable symbol identity, and encoding complete written signs

## Technical Position

The technical position is:

- the official Unicode SignWriting encoding, introduced in Unicode 8.0.0 and maintained in later Unicode versions, is not currently a compatible production replacement for the established FSW/SWU Sutton SignWriting production ecosystem
- FSW remains the canonical production encoding in practice
- SWU remains the isomorphic Unicode-oriented representation supported by the Sutton SignWriting Resources
- real-world corpora, publication, and current tooling should not be forced into the official Unicode encoding when that encoding cannot carry the writing system cleanly

One fact often causes confusion:

- there are Unicode-related packages and experiments inside the Sutton SignWriting ecosystem, including `@sutton-signwriting/unicode8`

That reflects the fact that official Unicode SignWriting exists in the world and must sometimes be processed, examined, converted, or bridged, even when it is not accepted as the main production path.

## Namespace and Status

| Term | What it is | What it is not |
| --- | --- | --- |
| Sutton SignWriting | Writing system and broader production ecosystem | Not an encoding by itself |
| ISWA 2010 | Symbol inventory and reference layer used by Sutton SignWriting Resources | Not a complete text model |
| FSW | ASCII Formal SignWriting production encoding | Not official Unicode |
| SWU | Unicode-oriented isomorphic representation of the Formal SignWriting model | Not the official Unicode SignWriting block |
| Official Unicode SignWriting | Unicode-side SignWriting encoding introduced in Unicode 8.0.0 | Not a compatible production replacement for FSW/SWU |
| Noto Sans SignWriting | Font support for the official Unicode model | Not proof that symbol identity, signbox modeling, collation, migration, or dataset compatibility are solved |
| `@sutton-signwriting/unicode8` | Bridge and inspection tooling for official Unicode SignWriting characters | Not evidence that official Unicode SignWriting is the canonical production path |
| `Sgnw` | ISO 15924 script code | Not a serialization model |

## Reading path

For most readers, this order works best:

1. **Unicode Overview**
   Start here for the baseline compatibility judgment.

2. **Wikimedia Brief** or **Developer Notes**
   Continue with the audience-specific path:
   Wikimedia Brief for platform and public-infrastructure conversations, Developer Notes for software, data, and tooling work.

3. **Chronology and Record**
   Follow the document trail and the turning points.

4. **Draft UTC-Facing Technical Note**
   End with the standards-facing argument and the disciplined technical closing.

5. **Standards Review in the Critical Review Series**
   Use the review-series interpretation when you want the Unicode issue evaluated through the broader writing-system framework.
   That review belongs to the separate Signed Language Writing Critical Review Series record, DOI `10.5281/zenodo.20042604`.

## Related series

Related work belongs in adjacent series:

- the public foundations for language and writing belong in the Foundations series
- the formal architecture of sign text belongs in the Formal SignWriting series
- Brazil and South Korea as empirical and institutional cases belong in the Evidence and Adoption series
- evaluative standards commentary belongs in the Critical Review series when the goal is to interpret the Unicode record rather than only document it

Start the foundations series with **Language Without Sound** and **The Shape of Writing**.

For the review-series interpretation, see **Official Unicode SignWriting: The Character Problem and the Written-Sign Problem**.

For the complementary encoding-governance statement from the production-encoding side, see **Encoding Stewardship and Stability** in the Formal SignWriting series.
