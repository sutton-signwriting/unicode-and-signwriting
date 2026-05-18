# Chronology and Record

**Official submissions, minutes, and related documents**

The public record relevant to Unicode and Sutton SignWriting runs through proposals, minutes, technical responses, and later public follow-up.

## Two-stage framing

One early understanding repeatedly matters:

> the plan for encoding Sutton SignWriting in Unicode was described as a two-stage process: first the symbol set, then an encoding that takes symbols and turns them into signs

That distinction remains central because the first stage moved forward while the second never became a workable compatible standard.

That distinction explains why later discussion kept circling back to layout, written-sign structure, and compatibility.

It also explains why later public statements of success did not settle the matter for the Sutton SignWriting production ecosystem.

Over time, the record clarified a second distinction:

- naming characters
- preserving stable symbol identity
- encoding complete written signs

## Main Unicode and related documents

### 2011

- **2011-04-06** — *Preliminary proposal for encoding the SignWriting script in the SMP of the UCS* — Michael Everson  
  - [WG2 N4015](https://www.unicode.org/wg2/docs/n4015.pdf)  
  - [L2/11-101](https://www.unicode.org/L2/L2011/11101-n4015-signwriting.pdf)

- **2011-05-06** — *Letter in support of SignWriting* — J. Albert Bickford  
  - [L2/11-174](https://www.unicode.org/L2/L2011/11174-supt-letter.pdf)

- **2011-08-05** — *Revised proposal for encoding the SignWriting script in the SMP of the UCS* — Michael Everson, Stephen Slevinski, Valerie Sutton  
  - [WG2 N4090](https://www.unicode.org/wg2/docs/n4090.pdf)  
  - [L2/11-217](https://www.unicode.org/L2/L2011/11217-n4090-signwriting.pdf)

This early revision cycle already matters because later Sutton SignWriting accounts describe concerns about sorting and structural compromise as beginning here rather than only much later.

### 2012

- **2012-10-14** — *Proposal for encoding Sutton SignWriting in the UCS* — Michael Everson, Martin Hosken, Stephen Slevinski, Valerie Sutton  
  - [WG2 N4342](https://www.unicode.org/wg2/docs/n4342.pdf)  
  - [L2/12-321](https://www.unicode.org/L2/L2012/12321-n4342-signwriting.pdf)

- **2012-12-04** — *UTC #133 Minutes*, including consensus item 133-C34  
  - [L2/12-343R2](https://www.unicode.org/consortium/utc-minutes/UTC-133-2012011.html)

- **2012-12-04** — Martin Hosken, *Encoding SignWriting Layout: An Initial Discussion*  
  - discussion document, not a submitted UTC proposal  
  - no public UTC registry link has been identified for this discussion note in the release record  
  - important as evidence that layout and composition remained unresolved

This discussion note matters even though it was not a formal UTC submission.

It shows that after the symbol-encoding stage, the actual written-sign problem was still unsettled enough to require exploratory design thinking.

### 2013

- **2013-05-23** — *Unconfirmed minutes of WG 2 meeting 60*, including SignWriting item M60.13  
  - [WG2 N4353](https://www.unicode.org/wg2/docs/n4353.pdf)

### 2015

- **2015-07-21** — *Addressing SignWriting Collation in DUCET* — Ken Whistler  
  - [L2/15-184](https://www.unicode.org/cgi-bin/GetMatchingDocs.pl?L2/15-184)

- **2015-07-22** — *A Response to L2/15-184 "Addressing SignWriting Collation in DUCET"* — Stephen Slevinski  
  - [L2/15-194](https://www.unicode.org/cgi-bin/GetMatchingDocs.pl?L2/15-194)

- **2015-07-23** — *Addressing SignWriting Collation in DUCET: Rejoinder to L2/15-194* — Ken Whistler  
  - [L2/15-202](https://www.unicode.org/cgi-bin/GetMatchingDocs.pl?L2/15-202)

- **2015-08-19** — *SignWriting Design, With Three Examples and Their Representation* — Stephen Slevinski, Deborah Anderson, Ken Whistler  
  - [L2/15-219](https://www.unicode.org/cgi-bin/GetMatchingDocs.pl?L2/15-219)

- **2015** — official addition of the Sutton SignWriting block in Unicode 8.0

2015 is the turning point that created much of the later confusion.

Many outside readers understandably inferred that SignWriting had therefore been fully solved in Unicode.

The remaining years of discussion show that this inference was too strong.

The symbol block had advanced.

That did not mean that stable symbol identity had been fully preserved across the system.

It also did not mean that written signs had a compatible encoding model.

Treat 2015 as:

- a major official milestone
- and the beginning of a larger public misunderstanding

### 2016

- **UTC #146 Minutes** — see decision and action items in C.3.1  
  - [L2/16-004](https://www.unicode.org/cgi-bin/GetMatchingDocs.pl?L2/16-004)

- **2016-08-03** — *SignWriting in Unicode Next* — Stephen Slevinski  
  - [L2/16-225](https://www.unicode.org/cgi-bin/GetMatchingDocs.pl?L2/16-225)

- **UTC #148 Minutes** — see C.16  
  - [L2/16-203](https://www.unicode.org/cgi-bin/GetMatchingDocs.pl?L2/16-203)

### 2017

- **2017-07-12** — *Design Options for Sutton SignWriting with examples and fonts* — Stephen Slevinski  
  - [L2/17-220](https://www.unicode.org/cgi-bin/GetMatchingDocs.pl?L2/17-220)

- **Recommendations to UTC #152 July-August 2017 on Script Proposals** — see point 29  
  - [L2/17-255](https://www.unicode.org/cgi-bin/GetMatchingDocs.pl?L2/17-255)

- **2017-08-01** — *Design Options for Sutton SignWriting Auxiliary* — Stephen Slevinski  
  - [L2/17-282](https://www.unicode.org/cgi-bin/GetMatchingDocs.pl?L2/17-282)

- **UTC #153 Minutes** — see C.10.1  
  - [L2/17-362](https://www.unicode.org/L2/L2017/17362.htm)

### 2020

- Google released **Noto Sans SignWriting**, the first high-visibility font implementing the official Unicode SignWriting design introduced in Unicode 8.0.0, including the facial-diacritic approach.

This mattered because it showed that a font could be produced for the official design, but it did not solve the broader compatibility, symbol-identity, and layout questions.

### 2026

- A brief Wikimedia-facing discussion showed that the Unicode issue can reappear when public-platform work runs into unresolved compatibility questions.

No formal UTC submission arose from that discussion, and no further public action is anticipated in the near future.

The point for this release is modest:

- the Unicode issue is not only historical
- future public-platform discussion should begin from the real production history rather than from a flattened story that the compatibility problem has already been solved

## Why this chronology matters

The current technical position is not based on misunderstanding what Unicode encoded.

It is based on years of proposals, minutes, collation responses, and attempts to find a workable path.

The core historical fact is this:

- character naming advanced
- a fully compatible symbol model did not
- the compatible writing-system solution did not

That remains the central documentary problem.

Everything else in the chronology is easier to interpret once that line is held in view.
