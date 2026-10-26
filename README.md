# wod-wiki-seed-crossfit

A Wod.Wiki community seed source — grouped workout notebooks, validated and
compiled into versioned seed artifacts by the `wod` CLI
([@bitcobblers/wod-wiki-tools](https://www.npmjs.com/package/@bitcobblers/wod-wiki-tools)),
published via GitHub Pages, and imported by the
[wod-wiki](https://github.com/bitcobblers/wod-wiki) app as an independent
seed source (own manifest, version, and sync checkpoint).

Split out of the [wod-wiki-community](https://github.com/bitcobblers/wod-wiki-community)
corpus; notebook chunk ids are unchanged so app-side sync state survives.

## Notebooks

| notebook | kind | items |
|---|---|---:|
| `crossfit-games-2007` | collection | 3 |
| `crossfit-games-2008` | collection | 4 |
| `crossfit-games-2009` | collection | 8 |
| `crossfit-games-2010` | collection | 9 |
| `crossfit-games-2011` | collection | 10 |
| `crossfit-games-2012` | collection | 15 |
| `crossfit-games-2013` | collection | 12 |
| `crossfit-games-2014` | collection | 13 |
| `crossfit-games-2015` | collection | 13 |
| `crossfit-games-2016` | collection | 15 |
| `crossfit-games-2017` | collection | 13 |
| `crossfit-games-2018` | collection | 14 |
| `crossfit-games-2019` | collection | 12 |
| `crossfit-games-2020` | collection | 11 |
| `crossfit-games-2021` | collection | 15 |
| `crossfit-games-2022` | collection | 14 |
| `crossfit-games-2023` | collection | 10 |
| `crossfit-games-2024` | collection | 10 |
| `crossfit-games-2025` | collection | 10 |
| `crossfit-games-2026` | collection | 20 |
| `crossfit-girls` | collection | 18 |
| `crossfit-heroes-2005` | collection | 3 |
| `crossfit-heroes-2006` | collection | 1 |
| `crossfit-heroes-2007` | collection | 4 |
| `crossfit-heroes-2008` | collection | 7 |
| `crossfit-heroes-2009` | collection | 5 |
| `crossfit-heroes-2010` | collection | 27 |
| `crossfit-heroes-2011` | collection | 25 |
| `crossfit-heroes-2012` | collection | 23 |
| `crossfit-heroes-2013` | collection | 26 |
| `crossfit-heroes-2014` | collection | 18 |
| `crossfit-heroes-2015` | collection | 20 |
| `crossfit-heroes-2016` | collection | 15 |
| `crossfit-heroes-2017` | collection | 16 |
| `crossfit-heroes-2018` | collection | 8 |
| `crossfit-heroes-2020` | collection | 4 |
| `crossfit-heroes-2021` | collection | 5 |
| `crossfit-heroes-2022` | collection | 2 |
| `crossfit-heroes-2023` | collection | 1 |
| `crossfit-heroes-2026` | collection | 3 |
| `crossfit-programming` | feed | 8 |

> Note: the Games and Heroes corpora were split from single notebooks
> (`crossfit-games`, `crossfit-heroes`) into per-year notebooks. Note ids are
> path-derived, so these splits reset app-side sync state for those notes once —
> existing installs re-import them as new.

## Layout

```
markdown/            the corpus (the only thing most PRs touch)
  collections/       named workout libraries — one dir per catalog, README + items
  feeds/             dated programming — feeds/<slug>/<yyyy-mm-dd>/<item>.md
dist/                build output (gitignored)
```

## Build & publish

```
npm install
npx wod build --out dist   # validate + compile (same gate the CI runs)
```

Pushes to `main` publish `dist/` to GitHub Pages
(.github/workflows/main.yml); PRs get a validation build + sticky report
(.github/workflows/pull-request.yml). The seed dir URL is
`https://<owner>.github.io/<repo>/` — `manifest.json` plus content-hashed
chunk files.
