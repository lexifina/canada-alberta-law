# How this repository was made (Alberta)

This file is written by the build on 2026-10-30, the day the source data was retrieved.

## Sources

| Source | Address | Retrieved | Licence |
| --- | --- | --- | --- |
| Legislative Assembly of Alberta: bills by legislature, and each bill's record | <https://www.assembly.ab.ca/assembly-business/bills/bills-by-legislature> | 2026-10-30 | Facts only (bill number, title, Royal Assent date, chapter, coming-into-force line); no text of the bills or of the Assembly's pages is reproduced |
| Wikidata | <https://www.wikidata.org/wiki/Q1951> | 2026-10-30 | CC0 1.0 |

Every word of law in this repository comes from these sources. Lexifina reads them and records each act's dated versions, and the laws that made each change, in one corpus file. This repository is built from that file.

## What is in it

| Act | Title | Versions | Span |
| --- | --- | ---: | --- |
| `catalogue` | Catalogue of Alberta bills given Royal Assent (title, bill number, assent date and chapter only) | 123 | 2001-05-31 to 2026-05-14 |
| `legal-system` | Alberta: legal system facts (Wikidata) | 2 | 1905-09-01 to 2026-10-29 |

The build made 125 commits:

| Commits | Kind |
| ---: | --- |
| 2 | first version of an act |
| 123 | one law on its in-force day |
| 0 | changes no amendment note explains, credited to the publisher |

Other counts:
- 0 commits on the branch `future`: laws not yet in force on 2026-10-30.
- 1 commits dated 1 January 1970: in force before 1970, with the real day in their `In-force` trailer.
- 124 laws in the record.
- 248 tags.

## Dates

Each commit is dated at noon (America/Edmonton) on the day the change took effect. The other dates, enacted and published, are trailers.

When a law gives no date of its own, the default rule applies: Catalogue entries are dated by the day of Royal Assent recorded by the Legislative Assembly; they describe bills and are not law text. https://www.assembly.ab.ca/assembly-business/bills/bills-by-legislature

## How the history is built

`tools/build.py` turns the corpus into this history in one pass: one commit per law, on the day it took effect. The same corpus always gives the same commit hashes. `tools/check_repo.py` reads every version back from git and compares it with the corpus. `tools/on.py` shows the law as it stood on any date. The corpus format is described in `tools/SCHEMA.md`.

- Corpus: sha256 `348c0973b2afdec1566152e7e8dd1cc48095d7d9b9ab44a5574ec54c9c2a302f` (511515 bytes).
- Builder blob hashes (`git hash-object`): `build.py` `a97ff7ea62c3c7595c5668a297d533da0b74373c`, `check.py` `3e59cb6f05eccb94a9ec14431a7f6781221e83ef`, `on.py` `644a6c0857fbcc72562032b58d57aa113fee0641`.
- Python 3.12.10; git version 2.46.0.windows.1.

## Checks

125 versions of 2 acts read back from git on the day each took effect and on the day before: 0 mismatches. Trailers: 0 commits whose trailers git cannot parse. Health: 0 merge commits on main, 0 commit dates that go backwards, 0 commits dated after the build.

No second build of this corpus has been compared yet.

## Decisions made by hand

- No law text is published. The King's Printer's laws site, the official online source of Alberta's statutes, does not allow automated access to its pages, and permission to use it has not been obtained, so nothing was taken from it.
- The catalogue holds facts only: bill number and type, the title (without the site's money-bill and title-changed markers), the Royal Assent date, the S.A. chapter and the coming-into-force line (a date, or "on proclamation") as the Legislative Assembly's record of each bill gives them. The Assembly allows non-commercial use of its website with acknowledgement; titles, numbers and dates are facts, and no text of the bills or of the Assembly's pages is reproduced.
- Coverage: every bill with a Royal Assent date from the 25th Legislature, 1st session to the 31st Legislature, 2nd session (2001-05-31 to 2026-05-14): 1025 bills on 123 assent days; 1003 with a chapter, 706 with a coming-into-force line. Earlier sessions are not yet included.
- Every bill record in these sessions was read.
- Wikidata facts (CC0) form the "legal-system" act, dated by the province's inception where Wikidata gives a day, otherwise by the latest revision of the Wikidata item before retrieval (2026-10-29; retrieved 2026-10-30), so no commit lies after the build.

## What AI did and did not do

The scripts that read the sources and build this repository were written by Claude Code running Claude Opus 5.5 (`claude-opus-5-5`) under Lexifina's direction.

No model wrote, translated or corrected legal text. No model runs at build time. Every word of law in this repository comes from the official sources above.

The commit messages are written by `build.py` from the source data.

Model use at data-build time:
- Claude Code with Claude Opus 5.5 wrote Lexifina's code and chose the sources; it did not write or alter any legal text. The code is deterministic and runs no model.
