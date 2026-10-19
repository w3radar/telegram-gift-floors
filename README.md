# Telegram Gift Floors: open data

Daily floor prices of every Telegram collectible gift collection listed on [Fragment](https://fragment.com/gifts), collected by the radar behind **[TG Gifts](https://tggifts.com)** and the Telegram bot **[Web3 Radar](https://t.me/w3radar_bot)**.

- **Coverage:** 120 collections, one point per collection per day, since 2026-10-18.
- **Source:** public Fragment collection pages, scanned every 15 seconds; the first floor seen each UTC day is stored.
- **Live version:** [`https://tggifts.com/data/floors-daily.json`](https://tggifts.com/data/floors-daily.json) (free, no key, CORS enabled, cached 1 h). This repo holds dated snapshots of it.

## Files
| File | What it is |
|---|---|
| `data/floors-daily.csv` | `date, collection_slug, collection_name, floor_gram, recent_sales` (one row per collection per day) |
| `data/floors-daily.json` | same data as JSON, grouped by collection |
| `data/track-record.json` | snapshot of the radar's public [track record](https://tggifts.com/track-record): below-floor listings it alerted on and what happened to them afterwards (sold / still listed / unknown) |

`floor_gram` is the cheapest Fragment listing price in GRAM (formerly TON). `recent_sales` is the number of recent sales visible on the collection page that day.

## Method and limits
- How values are computed: [tggifts.com/how-we-value](https://tggifts.com/how-we-value).
- **Fragment only.** Off-chain markets (Portals, Tonnel, MRKT, Getgems off-chain) are not included, so collections that trade only there (e.g. new upgrades before they reach Fragment) have no or misleading floors.
- Gaps are possible if a scan failed that day. Nothing is interpolated or estimated in these files.
- Not affiliated with Telegram or Fragment. Not financial advice.

## License
Data: [CC BY 4.0](LICENSE). Please credit **TG Gifts (tggifts.com)** with a link.

Snapshot updated: 2026-10-19. Built and maintained by the Web3 Radar team.
