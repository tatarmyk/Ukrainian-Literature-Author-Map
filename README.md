# Ukrainian-Literature-Author-Map

An Obsidian vault that maps Ukrainian writers through **documented personal connections**: mentors and students, friends, co-editors, correspondents, family, dedications, translations, public disputes and influences the authors acknowledged themselves.

- One note per author in `Автори/`, written in Ukrainian.
- Each graph link connects exactly two people and cites a source that contains the evidence.
- Literary groups and eras (ВАПЛІТЕ, неокласики, Розстріляне відродження, …) are **tags, not notes**. Clusters in the graph therefore come only from personal ties. The graph colours nodes by group tag, so you can see whether those clusters match the known groups.
- Each note links to the author's works online. No texts are copied into the vault.

The full rules are in [.github/copilot-instructions.md](.github/copilot-instructions.md).

## Structure
| Path | Contents |
|---|---|
| `Автори/` | Author notes |
| `_service/шаблони/Автор.md` | Note template (Obsidian Templates core plugin) |
| `_service/черга.md` | Queue of authors to research |
| `.github/agents/` | The two Copilot agents |
| `.obsidian/` | Shared settings: graph colours, templates, app settings (personal workspace files are ignored) |

## Data sources and licences
| Source | Used for | Licence |
|---|---|---|
| [Wikidata](https://www.wikidata.org) | IDs, dates, structured relations | CC0 |
| [uk.wikipedia](https://uk.wikipedia.org) | Biography facts, people mentioned | CC BY-SA 4.0 (cited per note in `## Джерела`) |
| [Енциклопедія сучасної України](https://esu.com.ua) | Cross-checking | Cited, not copied |
| [Encyclopedia of Ukraine](https://www.encyclopediaofukraine.com) | Cross-checking | Cited, not copied |
| uk.wikisource, ukrlib.com.ua, izbornyk.org.ua, chtyvo.org.ua | Links to works | Linked only |

Biographies are written in our own words. Every source used is listed in the note's `## Джерела` section with the date it was checked.

## Working with the agents (VS Code Copilot)
Choose an agent in the Copilot Chat agent picker:
- **Scraper** researches 1–5 authors from the queue (or ones you name) and writes or updates their notes. It uses the web, has no terminal and no git, and writes only to `Автори/` and the queue. Hand-off button: **Перевір і закоміть**.
- **Maintainer** checks the notes (a source on every link, links written on both notes, file names, metadata, queue), owns the settings and commits and pushes. Hand-off button: **Досліджуй наступних з черги**.

Typical loop: Maintainer → *Досліджуй наступних з черги* → Scraper → *Перевір і закоміть* → Maintainer.

New notes are marked `статус: чернетка`. They become `перевірено` only after the sources of every link have been opened and confirmed.

## Obsidian
- Open the folder as a vault. The graph view is preset to show only `Автори/`, coloured by group tag. Authors without a note yet appear as grey nodes.
- The community plugin [Dataview](https://github.com/blacksmithgu/obsidian-dataview) is recommended. Relation lines are Dataview inline fields (`наставник:: [[…]]`), so you can query them.
