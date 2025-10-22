# ShareVolume

Your assigned company: Broadridge Financial Solutions (BR), CIK 0001383312.

Fetch https://data.sec.gov/api/xbrl/companyconcept/CIK0001383312/dei/EntityCommonStockSharesOutstanding.json (set a descriptive User-Agent per SEC guidance).
Read `.entityName`. Filter `.units.shares[]` for entries whose `fy` > "2020" and
includes a numeric `val`.
Save `data.json` with this structure:
`{"entityName": "Broadridge Financial Solutions", "max": {"val": ..., "fy": ...}, "min": {"val": ..., "fy": ...}}`
where `max` and `min` refer to the highest and lowest `.val`. Break ties however you like.

Render a visually appealing `index.html` that `fetch()`es `data.json` and displays:
- `<title>` and `<h1>` must include the live `entityName`.
- Present the max/min figures clearly marking with these IDs:
  `share-entity-name`, `share-max-value`, `share-max-fy`,
  `share-min-value`, `share-min-fy`.

If the page is opened as `index.html?CIK=0001018724` (or any other 10-digit CIK),
`fetch()` from the SEC endpoint for that CIK using any proxy, e.g. AIPipe,
replace every ID listed above and the title and H1 without reloading the page.

Also commit the attachment uid.txt as-is.