# Telegram Gift Floors: open data

Daily floor prices of every Telegram collectible gift collection listed on [Fragment](https://fragment.com/gifts), collected by the radar behind **[TG Gifts](https://tggifts.com)** and the Telegram bot **[Web3 Radar](https://t.me/w3radar_bot)**.

- **Coverage:** 122 collections, one point per collection per day, since 2026-10-18.
- **Source:** public Fragment collection pages; each collection's floor is re-read about every 15 minutes (the newest-listings feed is checked every 15 seconds for below-floor listings). The first floor seen each UTC day is stored.
- **Live version:** [`https://tggifts.com/data/floors-daily.json`](https://tggifts.com/data/floors-daily.json) (free, no key, CORS enabled, cached 1 h). This repo holds dated snapshots of it.

## TG Gifts Index (TGGI)
A daily, chain-linked, liquidity-weighted index of Fragment gift collection floors (base 100 on 2026-10-18). Latest: **107.13** on 2026-10-27. Methodology (v1.0), constituents and weights: [tggifts.com/index](https://tggifts.com/index). Published values are frozen; corrections are listed on that page.

## Files
| File | What it is |
|---|---|
| `data/index.csv` | TG Gifts Index history: `date, value, change_pct, constituents` |
| `data/index.json` | TG Gifts Index: latest value, history, today's constituents and weights, method version |
| `data/floors-daily.csv` | `date, collection_slug, collection_name, floor_gram, recent_sales` (one row per collection per day) |
| `data/floors-daily.json` | same data as JSON, grouped by collection |
| `data/weekly/<YYYY-Www>.csv` | one file per published [weekly market report](https://tggifts.com/reports): week-over-week floor change per collection (`open_date, open_floor_gram, close_date, close_floor_gram, change_pct, recent_sales_at_close, days_with_data`) |
| `data/models/<YYYY-MM-DD>.csv` | per-model floors for that day: `date, collection_slug, collection_name, model, rarity_permille, floor_gram, buy_now_listings` (one row per model with a listing that day; live JSON: [`/data/models-daily.json`](https://tggifts.com/data/models-daily.json)) |
| `data/track-record.json` | snapshot of the radar's public [track record](https://tggifts.com/track-record): below-floor listings it alerted on and what happened to them afterwards (sold / still listed / unknown) |

`floor_gram` is the cheapest Fragment listing price in GRAM (formerly TON). `recent_sales` is the number of recent sales visible on the collection page that day.

## Reading the data: guides
Plain explanations of the terms in these files (EN / RU / FA): [all guides](https://tggifts.com/guides) · [what a floor price is](https://tggifts.com/guide/telegram-gift-floor-price) · [gift rarity (‰) explained](https://tggifts.com/guide/telegram-gift-rarity) · [most expensive gifts right now](https://tggifts.com/guide/most-expensive-telegram-gifts) · [GRAM vs TON](https://tggifts.com/guide/gram-vs-ton) · [glossary](https://tggifts.com/guide/telegram-gifts-glossary) · [флор подарков (RU)](https://tggifts.com/ru/guide/flor-podarkov-telegram) · [گیفت تلگرام چیست (FA)](https://tggifts.com/fa/guide/what-are-telegram-gifts).

## Method and limits
- How values are computed: [tggifts.com/how-we-value](https://tggifts.com/how-we-value).
- **Fragment only.** Off-chain markets (Portals, Tonnel, MRKT, Getgems off-chain) are not included, so collections that trade only there (e.g. new upgrades before they reach Fragment) have no or misleading floors.
- Gaps are possible if a scan failed that day. Nothing is interpolated or estimated in these files.
- Not affiliated with Telegram or Fragment. Not financial advice.

## License
Data: [CC BY 4.0](LICENSE). Please credit **TG Gifts (tggifts.com)** with a link.

Snapshot updated: 2026-10-27. Built and maintained by the Web3 Radar team.
