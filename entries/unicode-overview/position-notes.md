# Position Notes

**Short clarifications behind the overview**

## Unicode still matters

Unicode is highly relevant.

It shapes:

- public expectations
- font ecosystems
- open-source libraries
- Wikimedia and other public language infrastructure
- downstream software assumptions

The question is whether the current official Unicode SignWriting design is adequate and compatible.

This series uses production compatibility as the criterion: whether the official model can carry current data, tools, sorting, rendering, and publication practice without loss or redesign.

## Years of attempted engagement still matter

The present position comes after years of:

- proposals
- revisions
- collation discussions
- design alternatives
- attempts to find a workable path

## Bridge tooling still has a real role

Packages such as `@sutton-signwriting/unicode8` still have a real role.

They are useful because official Unicode SignWriting exists in the world and people need to:

- inspect it
- process it
- compare it
- convert it
- bridge it to FSW and SWU

It does not change the broader compatibility judgment.

## The central difference

Keep this distinction in view:

- characters can be named
- while stable writer-selected symbols are still not fully preserved
- and the practical written-sign problem remains unresolved

That is the real reason this subject keeps reappearing.
