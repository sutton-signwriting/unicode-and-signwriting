# Compatibility Matrix

**Compact comparison after the facial-orthography boundary note**

This table compares suitability for Sutton SignWriting-compatible production workflows, not general Unicode validity or all possible higher-level protocols.

| Question | FSW | SWU | Official Unicode block/model |
| --- | --- | --- | --- |
| Conformant official Unicode SignWriting | No | No | Yes |
| Names an official Unicode character repertoire | No | No | Yes |
| Functions as a production character layer for Sutton SignWriting | Yes | Yes, as a production-isomorphic representation | No |
| Functions as a de facto production standard in Sutton SignWriting-compatible workflows | Yes | Yes | No |
| Demonstrated in current production text use | Yes | Yes | Not as the primary production path |
| Drop-in compatibility with existing datasets | Yes | Supported by conversion and isomorphism | No |
| Can serve as current canonical production encoding | Yes | Supported, but not usually canonical | No |
| Suitable for current AI and dataset workflows | Yes | Yes | No for production datasets |
| Preserves writer-selected symbol identity across the production model | Yes | Yes | No in the FSW/SWU production sense |
| Keeps the Sutton SignWriting facial symbols selected by the writer | Yes | Yes | No |
| Preserves authored facial-symbol arrangement | Yes | Yes | No for `HEAD + marks` |
| Identifies the authored written face before rendering | Yes | Yes | No for `HEAD + marks` |
| Supports renderer-independent facial authoring for complex faces | Yes | Yes | No for `HEAD + marks` |
| Uses a head-plus-mark facial-diacritic model | No | No | Yes |
| Requires renderer-supplied facial orthography for nontrivial faces | No | No | Yes, under `HEAD + marks` |
| Keeps unsettled facial orthographic decisions with writers and communities | Yes | Yes | No for `HEAD + marks` |
| Avoids assuming orthographic closure before community closure exists | Yes | Yes | Not for `HEAD + marks` |
| Supports community-specific facial orthographic development from preserved written evidence | Yes | Yes | No for `HEAD + marks` |
| Allows future fonts to recover authored facial composition from stored data | Yes, because the production data is preserved | Yes, because it is production-isomorphic | No for `HEAD + marks` |
| Fits ordinary complex-script rendering analogy | Not the issue | Not the issue | Only if HEAD plus marks are accepted as the production text identity |
| Had demonstrated lossless production migration at encoding time | Already production | Production-isomorphic support | No |
| Requires leaving the official facial model when complex faces exceed it | No | No | Yes, for production work |
| Demonstrates a lossless migration path from existing FSW/SWU data | Already production | Production-isomorphic support | No |
| Solves the written-sign production problem by itself | Yes, in the current ecosystem | Yes, as equivalent form | No |

Here, "in the current ecosystem" means within the Sutton SignWriting production stack: existing FSW/SWU data, tools, rendering, search, sorting, corpora, dictionaries, and publication workflows.

## What This Table Is Meant To Show

The main distinction is not simply:

- Unicode versus non-Unicode

The main distinction is:

- preserving Sutton SignWriting production text
- naming characters
- preserving selected ISWA 2010 symbol identity
- preserving selected Sutton SignWriting facial symbols and authored arrangement
- leaving facial orthographic decisions with writers and communities
- supporting ordinary production workflows without requiring a renderer to complete the written face

The current official Unicode SignWriting block reaches the Unicode character-naming point much more clearly than the production facial-writing point.

The strongest compatibility question is not whether official Unicode names Unicode SignWriting characters. It does. The question is whether its head-plus-mark facial-diacritic model should be treated as a Unicode-specific composition model rather than a realistic production migration or general authoring path for Sutton SignWriting facial writing.

It should be treated as a Unicode-specific composition model. It should not be treated as a production character layer, production citation layer, or production foundation for Sutton SignWriting.

Production compatibility is a preservation and authoring claim. The official block does not identify a tested, lossless migration path from existing FSW/SWU data or a renderer-independent authoring path for general Sutton SignWriting facial writing. The burden should not be reversed onto production users to assume compatibility until they disprove it case by case.

A conformance suite can demonstrate selected failures of the official model. It cannot prove future orthographic adequacy for a living writing system. Passing selected tests would not show that the model can preserve future community distinctions, local practices, pedagogical uses, poetic writing, expressive forms, or complex facial arrangements that may become important later.

This is not a claim of linguistic authority. FSW/SWU compatibility means that a text model preserves authored written data needed for parsing, rendering, searching, sorting, interchange, archives, corpora, and production workflows. It does not decide whether a written form is good, preferred, standard, local, poetic, pedagogical, or community-approved.

FSW and SWU should be understood as de facto production standards within Sutton SignWriting-compatible interchange. SWU is not official Unicode SignWriting and should not be described as conformant use of the official block. That distinction is not proof by itself that the official Unicode model is inadequate; SWU use can reflect history, tooling, migration costs, and ecosystem preference. It is still an important production fact and warning: implementers should not infer production compatibility from official Unicode status when the working ecosystem uses a different, production-isomorphic model.

Official Unicode stability is Unicode stability. It is not production stability for Sutton SignWriting. A stable Unicode-scoped artifact can still be structurally inadequate as a production text model.

## Historical Compatibility Burden

The official block should not be treated as a proven production migration or authoring target merely because it was encoded.

The historical record matters because the compatibility claim was prospective. The early Unicode path treated SignWriting as a staged problem: first encode a Unicode character repertoire, then address the encoding that turns symbols into written signs. The character block advanced. The demonstrated production-compatible migration path did not.

By Unicode 8.0.0, no tested lossless migration path from general FSW/SWU production data had been identified. No production adoption of the official facial model by the Sutton SignWriting ecosystem had been demonstrated. Later font support, including Noto Sans SignWriting, demonstrates that a public font path for the official Unicode approach exists; it does not demonstrate audited production readiness, lossless migration from FSW/SWU, renderer-independent facial authoring, or compatibility across independent implementations.

## Renderer-Supplied Facial Orthography

All visible text depends on rendering. That is not the issue.

The issue is whether the stored text identifies the written face before the renderer acts. In the Sutton SignWriting production model, a writer selects facial symbols and authors their arrangement. A renderer may be technically complex, but it renders that selected composition.

In the official Unicode facial model, the stored sequence identifies a head plus Unicode facial mark categories. The font or renderer then supplies a facial-construction theory: ordering, attachment, collision handling, hierarchy, normal arrangements, invalid combinations, and what counts as the same face.

That is a different orthographic identity model, not merely a font-quality problem.

This is also not answered by pointing to Arabic, Devanagari, Tibetan, or other complex-script shaping. In ordinary complex-script cases, the encoded sequence is accepted as the written text identity and rendering realizes conventional visual behavior downstream from that identity. For Sutton SignWriting production facial writing, the disputed point is exactly whether `HEAD` plus marks are the production text identity of the written face. If they are not, then shaping sophistication cannot replace the missing authored data.

Simple facial examples can hide the problem because a font may supply a plausible conventional face. Complex, unsettled, poetic, pedagogical, expressive, or community-specific facial writing reveals the problem more clearly: the author is no longer only writing stored text, but negotiating with a particular implementation's facial theory.

When the implementation cannot construct the intended face, the author may need to leave the official model for FSW/SWU, private conventions, image rendering, application-specific data, or another workaround. A workaround may complete the author's practical task, but it does not make the official Unicode sequence a portable production text record of the authored face.

The same issue affects future orthographic development. Communities need preserved authored facial compositions in order to compare forms, teach distinctions, normalize spelling, and decide which differences matter. A model that stores an under-specified facial-mark sequence cannot assume that future fonts will recover a community's later facial orthography from data that did not preserve the authored face in the first place.

## Noto Sans SignWriting

Noto Sans SignWriting should be treated as a public font path for the official Unicode 8 approach.

That does not settle the production-compatibility question. Noto Sans SignWriting demonstrates that a public font path for the official Unicode approach exists. It does not demonstrate audited production readiness, lossless migration from FSW/SWU, renderer-independent facial authoring, or compatibility across independent implementations.

Even a fully corrected font would not change the preservation boundary: a renderer cannot recover authored facial arrangement from a sequence that did not store it.
