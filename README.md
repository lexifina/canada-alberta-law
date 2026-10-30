# Alberta: law history in git

The law of Alberta as a git history: one file per provision, one commit per law on the day it took effect, and the law that made each change as the commit's author. `git blame` names the law behind every paragraph; `git log` lists every change; picking a date gives the text in force that day.

It follows the shared design of [lexifina/global-law](https://github.com/lexifina/global-law).

## What this repository holds

**Metadata only, no law text, because the King's Printer's laws site, the official online source of Alberta's statutes, does not allow automated access, and permission to reuse it has not been obtained.** This repository records which bills received Royal Assent and when, with their chapters, and a handful of open facts about the province's legal system. To read a statute, go to the [Alberta King's Printer](https://kings-printer.alberta.ca). Text will be added if permission is granted.

| Folder | Act | Versions | History |
| --- | --- | ---: | --- |
| `catalogue/` | Catalogue of bills given Royal Assent: title, bill number, assent date and chapter only | 123 | 123 assent days from 31 May 2001 to 14 May 2026 (1025 bills, 25th Legislature, 1st session to the 31st Legislature, 2nd session) |
| `legal-system/` | Legal system facts from Wikidata (CC0) | 2 | The province's inception (1 September 1905), then the facts as Wikidata held them on 29 October 2026 |

## Source

The catalogue's bill numbers, titles, Royal Assent dates, chapters and coming-into-force lines are facts taken from the [Legislative Assembly of Alberta](https://www.assembly.ab.ca/assembly-business/bills/bills-by-legislature)'s record of each bill, 25th Legislature, 1st session to the 31st Legislature, 2nd session; no text of the bills or of those pages is reproduced. Source: Legislative Assembly of Alberta. The Wikidata facts are from [Wikidata](https://www.wikidata.org/wiki/Q1951) (CC0).

## Dates

A catalogue entry is dated by the day of Royal Assent the Assembly records, not by commencement, and is credited to a `catalogue-<date>` entry; the Assembly's coming-into-force line (a date, or "on proclamation") is listed in the entry. Commits are at noon, Alberta time (America/Edmonton, with daylight saving time). The Wikidata facts are dated by the province's inception where Wikidata gives a day, and otherwise by the latest revision of the Wikidata item (29 October 2026; retrieved 30 October 2026).

## How it is checked

Every version is read back from git on the day it took effect and on the day before (`tools/check_repo.py`) and must match `corpus.json`; results are in `REPRODUCE.md`.

## What "author" means

The author of a commit is the law (or, for facts, the retrieval) that made the change, with an e-mail address that cannot exist (`<law key>@assembly.ab.ca.invalid`). The committer is always Lexifina.

## Limits

Only bills given Royal Assent from the 25th Legislature, 1st session (2001) onward are listed; earlier statutes and the Revised Statutes of Alberta are not. Entries do not record later amendment or repeal. Nothing here is an official record of the statutes, and it is not made in affiliation with or endorsed by the Legislative Assembly of Alberta.
