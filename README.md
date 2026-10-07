# Match Tagger

**A free football match-analysis tool that runs in your browser.** Play a match video, log every action with a key press or a tap on the pitch, and get professional-style analysis straight away: heatmaps, pass networks, expected threat (xT), player profiles with percentile radars, team stats and video clips of any player's actions.

Built by **Suryansh Somvanshi**.

> **Try it:** Match tagger - https://suryanshsomvanshi1996-creator.github.io/Match-Tagger/

---

## Contents
1. [Who it's for](#who-its-for)
2. [What you can do](#what-you-can-do)
3. [Quick start](#quick-start)
4. [Player profiles and percentiles, explained](#player-profiles-and-percentiles-explained)
5. [Metrics glossary](#metrics-glossary)
6. [Keyboard shortcuts](#keyboard-shortcuts)
7. [Saving, backups and moving between devices](#saving-backups-and-moving-between-devices)
8. [Limitations](#limitations)
9. [Privacy](#privacy)
10. [Credits](#credits)

---

## Who it's for
- **Match analysts**, to code a match the way data providers do (event by event, with pitch locations) without paid software.
- **Recruitment and scouting analysts**, to build player profiles, compare players like for like and back up the numbers with video clips.
- **Coaches**, to review their own team: where it wins the ball back, how it builds up, who connects with whom.
- **Students and people building a portfolio** who want to show Opta/StatsBomb-style analysis from footage they can watch themselves.

---

## What you can do

### 1. Tag a match
- **16 actions:** pass, cross, carry, dribble, shot, ball lost, tackle, interception, recovery, clearance, block, pressure, ground duel, aerial duel, foul and save.
- **Exact locations:** click (or tap) where the action happened on a 105 × 68 m pitch, plus where the ball ended for passes, crosses and carries.
- **Outcomes, receivers and shot results:** successful/unsuccessful, who received the pass, and goal / on target / off target / blocked for shots.
- **Pass tags:** mark passes as **through balls** and **line-breaking passes**.
- **Automatic phase of play** for every event (build-up, progression, chance creation, attacking/defensive transition, high press, mid block, low block, set piece). You can override any of them.
- **Two ways to tag:** keyboard shortcuts on a laptop, or big tap buttons on a phone or tablet.
- **Direction handling:** choose which way each team shoots and press *Half-time: switch sides* at the second-half kick-off. Every chart is then shown in the standard analyst view.
- **Mark clips** (M) and add notes (N) to any event.

### 2. Set line-ups, formations and substitutions
- **Formation picker:** 12 formations (4-3-3, 4-2-3-1, 4-4-2, 4-1-4-1, 4-4-2 diamond, 4-3-1-2, 4-2-2-2, 3-5-2, 3-4-3, 3-4-2-1, 5-3-2, 5-4-1). Pick a player for each spot from a drop-down; that sets the starting XI and every player's position in one go.
- **24 positions** (GK; RB, RCB, CB, LCB, LB, RWB, LWB; DM, RDM, LDM, CM, RCM, LCM, RM, LM; AM, RAM, LAM, RW, LW, SS, CF, ST).
- **Substitutions with times:** used to work out **minutes played** for every player, which powers the per-90 numbers.

### 3. Analyse
Filter any view by **team, player, action type, outcome, phase of play and time window**.

| View | What it shows |
|---|---|
| **Player profile** | Percentile radar, profile index, heatmap and an automatic written summary, with optional comparison against a second player |
| **Heatmap** | Where actions happened, as a smooth density map |
| **Pass map** | Every pass as an arrow; completed vs failed |
| **Threat (xT)** | Passes and carries that made the team more dangerous, drawn over the expected-threat grid |
| **Pass network** | Average positions and passing links. Click a player to highlight his connections, then jump to his profile or his clips |
| **Shot map** | Every shot, coloured by outcome |
| **Zones** | Counts in the same 18 zones (L/C/R × 1–6) as the Match Analysis Toolkit and Zone Map |
| **Player stats** | 40+ columns per player, as totals or **per 90 minutes**. Click a name to open his profile |
| **Team stats** | Possession, field tilt, PPDA, counter-press regains, passes per possession, box entries, direct speed and phase counts |

Every chart can be saved as a **PNG** for reports and presentations.

### 4. Watch clips
- **Player clips:** pick a player (or a whole team) and an action type, such as *Xavi → passes*, and every matching moment plays back to back from your video.
- **Play as clips:** turns whatever is filtered on the Analyse tab into a playlist.
- **Clip reel:** plays only the moments you marked with M.
- Adjustable seconds before and after each moment, loop, previous/next, and a **CSV of clip times** for cutting in a video editor.

### 5. Import and export
- **Export for Toolkit (CSV):** the Event Log columns of the Excel *Match Analysis Toolkit*, ready to paste.
- **Export full data (CSV):** every event with coordinates in both screen and analyst view, zones, phase, notes and pass tags.
- **Import:** a Match Tagger full-data CSV, or a *Match Analysis Toolkit* workbook (.xlsx). The workbook import reads teams, squads and the event log.
- **Back up all matches / Restore from backup:** one `.json` file with everything (see below).

### 6. Use it anywhere
- Works on **laptops, tablets and phones**, with a layout that adapts to the screen.
- **Dark, light or automatic theme** (button at the top; dark by default).
- A **Home page** explains the tool to anyone you share it with.

---

## Quick start
1. **Matches & squads → New match.** Type the match name, both team names and colours, and both squads, one player per line as `8 Iniesta`. Pick which way each team shoots at kick-off and click **Save match details**.
2. **Line-ups:** pick a formation for each team and put a player in every spot. Add substitutions with their video time.
3. **Tag tab → Choose video…** and open the match file. It plays from your device and is never uploaded.
4. **Tag:** type the shirt number (or tap the player), press the action key (or tap the button), click where it happened on the pitch (and where it ended for passes), then **Enter** for successful or **Z** for unsuccessful. For passes, type the receiver's number.
5. At the second-half kick-off, press **Half-time: switch sides**.
6. **Analyse:** explore the views, open player profiles, compare players and play clips.
7. **Back up:** Matches & squads → **Back up all matches**, and keep the file in OneDrive or Google Drive.

Want to look around first? Click **Explore the example match** on the Home page (made-up events).

---

## Player profiles and percentiles, explained

### What a percentile means
Raw numbers are hard to judge on their own: is 6 progressive passes per 90 good? A **percentile** answers that by comparing the player with a group of similar players.

> **Percentile = the share of the comparison group the player beats.** A percentile of **85** means he is better than 85% of the group on that metric. **50** is exactly typical, and **10** means only 10% of the group are worse.

How it's calculated:

```
percentile = (number of players below him + half the number level with him) ÷ group size × 100
```

Players level with him count as half, so if everyone in the group has the same value (for example, nobody made a tackle), everyone gets **50** rather than 0 or 100. For **ball losses**, fewer is better, so the comparison is flipped.

Colours on the stat cards: **green 80+**, light green 60–79, amber 40–59, red below 40.

### Step by step: how a profile is built
1. **Minutes played** come from the line-up: starters count from the start of the analysed part of the video, substitutes from their entry time, and anyone subbed off stops at that time. If no starters are ticked for a team, everyone counts as playing the whole time.
2. **Per 90:** every count is scaled to 90 minutes. *Example:* 4 progressive passes in 30 minutes = 4 × 90 ÷ 30 = **12 per 90**. Percentages (pass completion, duels won) are not scaled.
3. **The comparison group** is chosen with **Rank against**:
   - **Players in this match:** only players in the match that's open.
   - **Players in all my matches:** every player in every saved match. A player who appears in several matches has his actions and minutes added together first.
4. **Like for like:** within that group, only players in the **same position group** as the template are used (goalkeepers, centre-backs, full-backs, midfielders, attacking midfielders, wingers, strikers). If fewer than 3 players share that position group, all outfield players are used instead, and the profile says so.
5. **Template:** each position group has 8 metrics that matter for the role, and the template follows the player's position. You can switch it, for example to see a full-back through a winger's template.

| Template | Metrics |
|---|---|
| Goalkeeper | Passes, pass completion, long balls, progressive pass distance, recoveries, clearances, saves, ball losses |
| Centre-back | Pass completion, progressive passes, long balls, progressive pass distance, tackles won, interceptions, clearances, duels won % |
| Full-back | Progressive passes, progressive carries, crosses completed, key passes, xT added, tackles won, interceptions, recoveries |
| Midfielder | Passes, pass completion, progressive passes, line-breaking passes, xT added, tackles won, interceptions, recoveries |
| Attacking midfielder | Key passes, shot-creating actions, xT added, through balls, dribbles won, shots, received in final third, half-space receptions |
| Winger | Dribbles won, crosses completed, progressive carries, key passes, shot-creating actions, xT added, shots, received in final third |
| Striker | Shots, shots on target, goals, shot-creating actions, received in final third, half-space receptions, duels won %, pressures |

### Profile index
The **profile index** is the average of the player's 8 percentiles in the chosen template, from 0 to 100. Around **50** is a typical player for the group, **70+** stands out, and below **30** is weak in that role. It's a quick summary for ranking a shortlist, but read the radar for the shape: two players with the same index can be very different.

### Comparing two players
Pick a second player in **Compare with**:
- Both players get their own colour (solid shape vs dashed shape on the radar).
- Every metric shows **both values and both percentiles**, and **▲** marks who is better.
- Both **profile indexes** appear side by side.
- **Two heatmaps**, one per player, both drawn attacking left → right.
- A **head-to-head line**, e.g. *"Xavi is ahead on 5 of 8 (passes, pass completion, progressive passes, xT added, recoveries); Carrick on 1 (tackles won). Profile index 66 v 42."*

Both players are ranked against the same group (the one chosen by the template), so the numbers are directly comparable.

### Reading percentiles sensibly
- **Group size matters.** In one match a position group may have 3–6 players, so one action can move a percentile a lot. The more matches you tag, the more the percentiles behave like real scouting percentiles.
- **Minutes matter.** Under about 30 minutes, per-90 numbers are inflated or deflated by chance; the profile warns you.
- **Context matters.** Percentiles show how a player compares *within your data*: the teams, matches and game states you tagged. They are not a league-wide ranking.

---

## Metrics glossary
| Metric | Definition used here |
|---|---|
| **Progressive pass / carry** | Moves the ball at least **30 m** closer to goal within its own half, **15 m** from its own half into the opponent's, or **10 m** inside the opponent's half |
| **Final-third pass** | Completed pass that ends in the final third, starting outside it |
| **Key pass** | Completed pass or cross whose receiver shoots within 5 seconds |
| **Shot-creating actions (SCA)** | The two attacking actions (completed pass, cross, carry or dribble) by the shooting team directly before a shot, within 15 seconds. **Goal-creating actions (GCA)** are the same for goals |
| **Expected threat (xT)** | How much a completed pass or carry raised the chance of scoring soon, using a 12 × 8 grid of pitch values |
| **Half-space reception** | Completed pass received in the opponent's half, in the channel between the edge of the box and the six-yard-box line |
| **Long ball** | Pass of 32 m or more |
| **Switch** | Completed pass moving the ball 30 m+ across the pitch |
| **Through ball / line-breaking pass** | Tagged by you while tagging (Q / E) |
| **PPDA** | Opponent passes in their own 60% of the pitch ÷ your tackles, interceptions, duels and fouls in that area (lower = more pressing) |
| **Field tilt** | Your share of both teams' final-third passes |
| **Counter-press regains** | Times the ball was won back within 5 seconds of losing it, out of times it was lost |
| **Direct speed** | Average metres gained towards goal per second in possessions of 3 s or longer |

---

## Keyboard shortcuts
| Keys | Action |
|---|---|
| `0`–`99` | Pick a player by shirt number |
| `Tab` | Switch team |
| `P` `X` `C` `D` `S` `K` | Pass, cross, carry, dribble, shot, ball lost |
| `T` `I` `R` `L` `B` `H` | Tackle, interception, recovery, clearance, block, pressure |
| `U` `A` `F` `V` | Ground duel, aerial duel, foul, save |
| `Enter` / `Z` | Save as successful / unsuccessful |
| `G` `O` `W` `B` (after a shot) | Goal, on target, off target (wide), blocked |
| `Q` / `E` | Through ball / line-breaking (pass tags) |
| `Y` | Set piece |
| `M` / `N` | Mark last event as a clip / add a note |
| `Esc` / `Backspace` | Cancel / undo last event |
| `Space`, `←` `→`, `Shift + ←` `→`, `[` `]` | Play/pause, ±2 s, ±0.2 s, slower/faster |

On phones and tablets every action has a tap button, so no keyboard is needed.

---

## Saving, backups and moving between devices
- **This website saves matches in your browser, on your device.** They survive closing the page and restarting, but they are **not** shared with your other devices or browsers. They are **deleted** if you clear browsing data, use a private/incognito window or uninstall the browser.
- **Back up all matches** downloads one `.json` file with every match, its events, line-ups, formations, positions and substitutions. Keep it in OneDrive, Google Drive or iCloud.
- **Restore from backup** adds missing matches and updates older copies; a newer copy already in the browser is kept, so restoring never overwrites newer work.
- To move to a new device, back up on the old one and restore on the new one.
- Updating the website (a new `index.html` on GitHub) does **not** delete saved matches.

---

## Limitations
Match Tagger is an honest manual-coding tool. These are its limits:

**Data collection**
- **Tagging is manual.** Data quality depends on the analyst: a 90-minute match takes several hours to code in full. Nothing is detected automatically from the video.
- **Locations are judgement.** You click where you see the action on a 2D pitch; broadcast camera angles make this approximate (typically within a few metres), especially far from the camera.
- **The definitions are created on my own.** Progressive passes, key passes, SCA, PPDA and so on follow common public definitions but are not identical to Opta, StatsBomb or Wyscout, so numbers are not directly comparable with theirs.
- **Automatic phases are rule-based.** They use pitch zone and recent changes of possession, not the context a human sees (game state, shape). Check and edit them where it matters.
- **Toolkit (.xlsx) imports place events in the centre of their zone**, because the workbook stores zones, not coordinates. Heatmaps and pass maps from imported data are therefore blockier than from tagged data.

**Video and clips**
- **The video is never stored.** You open it from your device each session; clips need it open.
- **Clips use video time.** If events were logged with the match clock (e.g. in Excel) and the video is an edited extract, clips land at the wrong moment.
- **Very large videos** can be slow to seek on older phones and tablets.

**Analysis**
- **Small samples:** per-90 numbers from short clips (under ~30 minutes) are unreliable, and percentiles from one match compare a player with only a handful of others.
- **Percentiles are relative to your own data,** not to a league or a scouting database. A 90th percentile means "among the players you tagged".
- **Minutes depend on the line-up.** If starters and substitutions aren't entered, everyone is assumed to have played the whole time.
- **Expected threat (xT)** uses one model trained on Premier League 2015/16 open play. It values ball movement only (not off-ball runs, defending or set pieces) and doesn't adjust for league, opponent or game state.
- **No tracking data:** no distance covered, speed, off-ball runs or defensive shape. Only on-ball events are recorded.
- **Templates are fixed** at 8 metrics per position group; you can switch template but not edit the metrics.

**Storage and sharing**
- **One device, one browser** for the website version (see above). Back up regularly.
- **Browser storage is limited** (a few MB). That's enough for dozens of fully tagged matches; export or back up older ones if you reach the limit.
- **Single user:** there is no shared online database, so two analysts can't tag the same match at the same time. Share work by exporting CSVs or backup files.

---

## Privacy
Everything runs in your browser. **Videos are played from your own device and are never uploaded.** Matches stay in your browser until you export them. Match Tagger itself has no accounts, tracking or analytics. From the internet it loads only its fonts (Google Fonts) and, when you import an Excel workbook, the free SheetJS library; without a connection it still works with standard fonts.

---

## Credits
- **Built by Suryansh Somvanshi**: design, analysis methods and metric definitions.
- **Expected threat model:** a 12 × 8 grid trained with Karun Singh's method (*Introducing Expected Threat (xT)*) on the free [StatsBomb Open Data](https://github.com/statsbomb/open-data) for the Premier League 2015/16 (380 matches).
- **Excel import:** [SheetJS](https://sheetjs.com).
- **Fonts:** Barlow Condensed, Archivo and IBM Plex Mono (Google Fonts).
