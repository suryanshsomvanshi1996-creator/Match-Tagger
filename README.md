# Match Tagger

A free, browser-based football match analysis tool.

Load a match video, tag every action with keyboard shortcuts (or tap buttons on a tablet or phone) and clicks on a pitch, then analyse the match straight away.

## What it does

- **Tagging**: passes, crosses, carries, dribbles, shots, tackles, interceptions, recoveries, clearances, blocks, pressures, duels, fouls and saves, with exact pitch locations, outcomes, receivers and an automatic phase of play.
- **Pass tags**: through balls and line-breaking passes.
- **Charts**: heatmaps, pass maps, expected-threat (xT) maps, pass networks, shot maps and an 18-zone grid. All in the analyst view (each team attacking left to right).
- **Player stats**: passes, progressive passes, key passes, shot- and goal-creating actions, xT added, progressive distance, half-space receptions, through balls, line-breaking passes, long balls, switches, defensive actions and more.
- **Team stats**: possession, field tilt, PPDA, counter-press regains, possessions, passes per possession, direct speed, xT, box entries and phase counts.
- **Exports**: CSV for the Match Analysis Toolkit (Excel), full data CSV with coordinates, and PNG images of every chart. Imports full-data CSVs and Toolkit workbooks (.xlsx).

## Privacy

Everything runs in your browser. Videos are played from your own computer and never uploaded; matches are saved in your browser on your device. Export a CSV to back up a match or move it to another device.

## Expected threat model

The xT grid (12 × 8) was trained with Karun Singh's expected-threat method on the free StatsBomb open data for the 2015/16 Premier League (380 matches).

## Credits

- Event data for the xT model: [StatsBomb Open Data](https://github.com/statsbomb/open-data)
- Excel import: [SheetJS](https://sheetjs.com)
- Expected threat: Karun Singh, *Introducing Expected Threat (xT)*
