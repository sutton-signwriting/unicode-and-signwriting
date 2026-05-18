# Requested Work

**What a renewed UTC discussion should actually do**

## The wrong next step

The wrong next step would be:

- assuming migration to the current official Unicode SignWriting encoding is the expected path
- assuming the remaining issue is only font completeness
- assuming the official character block already settled symbol identity
- treating disagreement as mainly social or historical rather than technical

Those moves would repeat the problem instead of clarifying it.

## The right first questions

A renewed UTC discussion should begin with a small set of direct questions:

1. Is the current official Unicode SignWriting encoding sufficient for compatible production use within the Sutton SignWriting ecosystem?
2. Does the current official design preserve stable writer-selected symbol identity across the full system?
3. In the facial system, is symbol formation defined by a shared symbol inventory or partly mediated through font behavior?
4. Is the written-sign problem solved by the current official design, or only part of the character problem?
5. Does the current official design provide a workable path for spatial composition?
6. Are collation and sorting issues merely tuning issues, or signs of deeper incompatibility?
7. Is there a credible migration path from current FSW and SWU production use to the official encoding without loss or redesign?

## Minimum requested acknowledgments

Before any larger proposal work, the following acknowledgments would already count as progress:

- the current official Unicode SignWriting encoding is not yet sufficient for compatible production use
- naming characters is not the same as preserving stable symbol identity
- the facial-diacritic model mediates part of symbol formation through font behavior
- spatial composition remains unresolved
- migration cannot be assumed
- current production use must be part of the evaluation standard

## Possible technical work areas

If UTC discussion does reopen, several work areas could be explored:

- renewed work on spatial-composition support
- direct review of collation and sorting limits
- explicit compatibility review against current FSW and SWU production use
- reconsideration of explicit first fill and first rotation values instead of inherent values
- reconsideration of the facial-diacritic model where it breaks writer-selected symbol identity
- reconsideration of minimal structural additions needed for usable written-sign encoding

Explicit first fill and first rotation values would preserve the writer's selected symbol directly in the encoding instead of inferring part of that identity from a canonical default.

The first requirement is honest acknowledgment of the current gap and its actual shape.
