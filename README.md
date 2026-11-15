# Filament Viewer

A one-file viewer (`index.html`) for MyTechFun's results spreadsheet: table, scatter, bars, radar.
The .xlsx is read in the browser and kept there (IndexedDB) for next time; nothing is uploaded.

**Open it:** double-click `index.html` (it needs the internet for SheetJS and Chart.js from
cdnjs), then drop the .xlsx on it. Or serve the Print-Lab folder (`filament-viewer` in
`.claude/launch.json`: `python -m http.server 4180 --directory projects/Print-Lab`) and open
`http://localhost:4180/filament-viewer/?xlsx=../inputs/mytechfun/<file>.xlsx`.

**Host it** like the original (Firebase Hosting, `*.web.app`), or GitHub Pages / Netlify: it is
a static page, publish `index.html` alone. Don't publish the spreadsheet (a Patreon gift); each
visitor opens their own copy.

**Computed creep:** deflection on day D minus day 0 (mm, and % of day 0). D is the last day
every row shown has data for: day 1 across the whole sheet, day 5 once filtered to rows with
day-5 data ("Rows" under Creep). "Each row's own last day" uses every row's last day instead
(the day is printed beside it; mixed horizons don't compare fairly).

**On a phone:** ☰ Filters opens the filters as a drawer; pinch the table to zoom (or − / +), drag to scroll both ways. On a computer, Ctrl + wheel or a trackpad pinch zooms the table.

Claude reads the same sheet with `uv run tools/filaments.py` (same parsing and creep).
