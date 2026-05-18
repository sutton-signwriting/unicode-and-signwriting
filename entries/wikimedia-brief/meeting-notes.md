# Discussion Outline

**Public discussion structure for Unicode and SignWriting conversations**

## Purpose

Establish a shared factual baseline about the current production stack, the remaining technical gap, and the realistic scope of any platform-side discussion.

Full technical agreement is not required for an initial discussion.

Accurate understanding and a clear next step are enough for an initial discussion.

## Framing

A useful opening is to make the practical question explicit:

- why are FSW and SWU still in active use when Unicode already has a SignWriting block?
- what remains unresolved for real project use inside Wikimedia?
- what kind of documentation or technical clarification would actually be useful?

The core framing can stay simple:

- the Unicode block names characters, but it does not yet provide a complete, compatible solution for stable symbols and plane-based written signs
- current production tools, datasets, and real-world use therefore still rely on FSW and SWU
- the first discussion is about shared understanding, not forcing an immediate standards conclusion

## Suggested outline

### 1. Confirm the practical question

Start by confirming the reason for the conversation:

- documented SignWriting use on Wikimedia-facing infrastructure
- why existing projects still rely on FSW and SWU
- what the platform side actually needs to understand

### 2. Clarify the technical distinction

It helps to separate three ideas clearly:

- naming characters in Unicode
- preserving stable writer-selected symbols
- encoding complete plane-based written signs for storage, rendering, search, and reuse

This is usually the most important distinction in the conversation.

### 3. Review current production reality

The production baseline is:

- **FSW** as the canonical production encoding
- **SWU** as the supported Unicode-oriented isomorphic representation
- existing tools, dictionaries, corpora, and websites built around that stack
- bridge tooling such as `@sutton-signwriting/unicode8`

### 4. Note the existing Wikimedia footprint

This is not only a future-facing standards question.

Public Wikimedia records have documented a Wikimedia footprint:

- Wikidata property `P14164` ("SignWriting transcription") has been associated with a formatter URL for `https://steveslevinski.me/#page/formal-signwriting-analyzer/fsw/$1`
- Wikimedia Incubator has supported sign-language test wikis with a SignWriting gadget and related custom scripts
- older Wikimedia Cloud VPS / Labs services such as `swserver.wmflabs.org` and `swis.wmflabs.org` show that SignWriting support has already required custom bridge services

Because Wikimedia properties, gadgets, services, and Cloud VPS resources can change, operational planning should start from a fresh check of their current state.

For this release, P14164 and its formatter URL were checked on 2026-05-15.

That history matters because it shows both real demand and real drift.

### 5. Discuss Wikimedia-specific implications

Accurate handling affects:

- sign-language incubator projects
- sign-language lexemes in Wikidata
- reference examples and shared linguistic data
- rendering, search, and reuse across projects
- future public language infrastructure inside Wikimedia

### 6. Identify useful next steps

Useful next steps may include:

- confirming the current production stack and where the technical gaps remain
- reviewing bridge tooling and datasets
- deciding whether a future Unicode-level discussion would be worth reopening
- documenting the present limitations accurately in any public-facing support material

## Documents to send or keep ready

- **Wikimedia Brief**
- **Developer Notes**
- **Unicode Overview**
- **Draft UTC-Facing Technical Note**, if the discussion becomes concrete
- **Chronology and Record**, if history becomes relevant

## Useful outcome for an initial discussion

A strong discussion ends with:

- shared understanding of the current production ecosystem
- clear recognition that the issue is about encoding and interoperability, not only fonts
- a cooperative tone for future discussion
- a concrete next step

A weak outcome would be a public-facing statement that Unicode has already solved SignWriting in full, or that FSW and SWU are merely obsolete workarounds. That would repeat the confusion this discussion is meant to prevent.
