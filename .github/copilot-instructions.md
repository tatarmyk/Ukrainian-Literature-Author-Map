# Ukrainian Literature Author Map — shared rules

This repo is an Obsidian vault. One note per author in `Автори/`. Graph links connect **only two people** and every link needs a cited source. Literary groups are **tags, never notes**, so clusters in the graph come only from documented personal connections.

Notes are written in Ukrainian. Never copy text from sources: biographies are written in our own words, works are linked, not copied.

## File names
- Path: `Автори/Ім'я Прізвище.md` — the name the author is best known by (as in the uk.wikipedia title, without patronymic). Pseudonyms win if that is how the author is known (`Микола Хвильовий`, not `Микола Фітільов`).
- Apostrophe: always the straight ASCII `'` (U+0027), in file names and in links.
- Name collision: append the birth year, e.g. `Іван Петренко (1890)`.
- Always link by the file name (`[[Микола Зеров]]`), never by alias.

## Note metadata (YAML frontmatter)
```yaml
---
type: автор
aliases: [Микола Костянтинович Зеров, Зеров]   # full name, real name, pseudonyms
народження: 1890-04-26                     # ISO date; YYYY or YYYY-MM if unknown
смерть: 1937-11-03
місця: [Зіньків, Київ, Сандармох]           # plain text, no [[links]]
wikidata: Q123456                          # Q-ID only (placeholder here)
tags: [епоха/розстріляне-відродження, рух/неокласики]
статус: чернетка                           # чернетка | перевірено
оновлено: 2026-11-20                       # date of last edit
---
```
- Every note needs at least one `епоха/…` tag; add `рух/…` tags for documented membership. `епоха/` marks the generation, not the fate (survivors like Рильський keep `розстріляне-відродження`).
- `місця`: birth place, main places of study/work, place of death — at most ~6.
- Dates: if sources conflict, use the Wikidata (Gregorian) date and report the conflict.
- `статус: перевірено` is set only after the sources of every link were opened and confirmed (Maintainer spot-check or the user). Scraper always writes `чернетка`.
- Template: `_service/шаблони/Автор.md`.

## Tags (group membership — never links)
- `епоха/`: `розстріляне-відродження`, `модернізм`, `шістдесятники`, `празька-школа`, `мур`
- `рух/`: `вапліте`, `неокласики`, `гарт`, `плуг`, `молодняк`, `панфутуристи` (incl. Нова генерація), `марс`, `ланка`, `березіль`
- Lowercase, hyphens instead of spaces, no apostrophes. Add a new tag only if no existing one fits, and report it.

## Note sections (in this order)
1. Intro: 1–2 sentences (who, years, why notable). No heading.
2. `## Біографія` — 200–400 words, own words, no copied sentences. Keep the dry facts short and make the person come alive (see below).
3. `## Зв'язки` — relation lines (see below).
4. `## Твори` — links to works.
5. `## Джерела` — every source used, as `- [Назва](URL) — переглянуто YYYY-MM-DD`.

## Biography style
The note should feel personal, not like an encyclopedia entry.
- Facts (dates, studies, jobs, arrest) in compact sentences; give the space to character.
- Include 2–4 vivid details: anecdotes, habits, bold character traits, nicknames, how they looked or spoke, famous gestures or scandals.
- Up to 2 short quotes **by other people** about the author (a contemporary, friend, critic): ≤ 2 sentences each, in «…», with who said it, e.g. `Юрій Шерех називав його «…»`. The author's own words are allowed the same way.
- Every anecdote and quote must come from a source listed in `## Джерела`. Mark legends and single-memoir stories as such («за спогадами …», «за переказом»). Never invent or embellish.

## Link rules (`## Зв'язки`)
A link is added **only** for a documented personal connection between two people. One line per connection, as a Dataview inline field:

```
- наставник:: [[Микола Зеров]] — вів семінар, у якому навчався автор — [ЕСУ](https://esu.com.ua/...)
```
Format: `- <тип>:: [[Інший автор]] — <коротке свідчення> — [<джерело>](<URL>)`. The source URL must point to the page that contains the evidence.

The key names the relation **as seen from this note**. Every link is written on **both** notes with the inverse key:

| Key on note A | Meaning | Key on note B |
|---|---|---|
| `наставник:: [[B]]` | B was A's mentor/teacher | `учень:: [[A]]` |
| `учень:: [[B]]` | B was A's student | `наставник:: [[A]]` |
| `друг:: [[B]]` | friends | `друг:: [[A]]` |
| `співпраця:: [[B]]` | co-editing, joint almanac, co-authorship, director staging the other's play in documented joint work | `співпраця:: [[A]]` |
| `листування:: [[B]]` | documented correspondence | `листування:: [[A]]` |
| `родина:: [[B]]` | family (state the relation in the evidence) | `родина:: [[A]]` |
| `присвята:: [[B]]` | A dedicated a work to B | `присвята-від:: [[A]]` |
| `переклад:: [[B]]` | A translated B's work | `переклад-від:: [[A]]` |
| `полеміка:: [[B]]` | public dispute | `полеміка:: [[A]]` |
| `зустріч:: [[B]]` | documented private time together, once or recurring: home literary evenings, feasts or drinking, hunting, trips or holidays, shared lodging, visits | `зустріч:: [[A]]` |
| `вплив:: [[B]]` | B influenced A — **only if A acknowledged it** | `вплив-на:: [[A]]` |

- **Not** a reason for a link: same group, same city, same era, same journal issue, same arrest/trial without a personal tie, being on the same side of a debate, attending the same public event (congress, official meeting, mass rally). Those go into tags or the biography text.
- `зустріч` is for private, informal time where a source puts both people together. Many records from those years were destroyed, so an exact date or place is **not** required: recurring gatherings («суботи» at someone's home, regular hunting trips) or an approximate setting («в харківські роки») are fine. Give whatever detail the source has and put the anecdote in the evidence, e.g. `— їздили разом на полювання, Хвильовий подарував Кулішеві сетера Джоя`. One line per distinct occasion or habit; a `друг` line for the same pair does not replace it.
- Several lines for the same pair are fine when they are different facts (e.g. mutual dedications: `присвята` and `присвята-від` on both notes).
- `вплив` needs the author's own words (letter, memoir, interview) cited by the source; an encyclopedia saying "influenced by" is not enough.
- `наставник`/`учень` needs the source to describe teaching, a seminar or explicit mentorship ("учень", "вчитель"); mere support or promotion is not enough.
- `друг` needs the source to call them friends ("друг", "приятель", "товариш" in the sense of friend), not just classmates or colleagues.
- Link only people of Ukrainian literature: writers, poets, translators, literary critics/scholars, and theatre directors who worked with writers. No composers, painters, non-literary scholars or foreign authors — mention them in the biography instead.
- If the other author has no note yet, still write the link (it shows as a grey node) and add the name to the queue. The inverse line is added when that note is created.
- Before creating a note, search `Автори/` for existing links to this author and add every missing inverse line.
- When unsure, do not add the link — report it as a doubt.

## Works (`## Твори`)
One line per work, links only:
```
- *Камена* (1924) — [Вікіджерела](URL) · [УкрЛіб](URL)
```
Source preference: uk.wikisource (public domain) → ukrlib.com.ua → izbornyk.org.ua → chtyvo.org.ua → other public digital libraries (e.g. elib.nlu.org.ua, diasporiana.org.ua). Only URLs that were opened and show the work. No notes per work (exception for later: a work that itself creates a connection).

## Source ranking
1. Wikidata (IDs, dates, structured relations) — CC0
2. uk.wikipedia — CC BY-SA, cite page
3. ЕСУ — Енциклопедія сучасної України (esu.com.ua)
4. Encyclopedia of Ukraine (encyclopediaofukraine.com)

Memoirs, diaries and letters of contemporaries (e.g. on litopys.org.ua, diasporiana.org.ua, chtyvo.org.ua) and well-referenced articles by literary historians are the main sources for anecdotes, quotes and `зустріч` links; cite the exact page.

Cross-check dates and relations between at least two sources. ЕСУ is published only for letters А–О; for other names cross-check with Encyclopedia of Ukraine. Other reputable sources (academic publications, museum sites) are allowed as evidence; mention them as such in the report.

## Queue (`_service/черга.md`)
Plain names, no `[[links]]` (keeps the queue out of the graph):
```
- [ ] Микола Зеров — рух/неокласики
- [ ] Ім'я Прізвище — згадано в: Микола Зеров
- [x] Максим Рильський
```
Tick `[x]` when the note exists. Add newly mentioned authors under `## Згадані`. If a linked author is already in the queue, append the source note to that line (`— згадано в: Микола Зеров, Павло Тичина`). `згадано в` means "this note links to them and is waiting for the inverse line".

## Copyright
Never copy texts of works or paragraphs of biographies. Link instead. Short attributed quotes about a person (≤ 2 sentences, max 2 per note) are allowed. No stored portraits or images.

## Git
Shell commands are prefixed with `rtk` (e.g. `rtk git status`). Never force-push, rewrite history or delete branches.
