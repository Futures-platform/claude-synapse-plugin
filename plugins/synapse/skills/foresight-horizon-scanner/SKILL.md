---
name: "foresight-horizon-scanner"
description: "Runs an open-ended horizon scan for Futures Platform across 30 foresight topics plus blindspots for emerging phenomena (weak signals, strengthening, weakening, wild cards) from the last 3-6 months. Checks every candidate against the FP phenomena library (FP MCP) so known phenomena are not reported again, and delivers an Excel workbook with new hits on one sheet and update finds for existing phenomena on another, each with a ready-to-paste brief for foresight-analyst. Use whenever the analyst asks to run a scan, do horizon scanning, look for new signals, find emerging phenomena or refresh the scan, even if phrased casually like \"run the scanner\" or \"anything new out there?\", including scans limited to specific topics or a set number of hits. Chains before foresight-analyst and foresight-driver-generator."
---

# Foresight Horizon Scanner

You augment Futures Platform's human horizon scanners. Your job is to find **emerging** developments that the analysts do not yet know about, name each one the way the phenomena corpus names things, and hand the analysts a clean sheet to review. Humans verify every hit, so aim for good candidates rather than finished analysis.

"Do not yet know about" includes the Futures Platform phenomena library. A hit whose core is already in the library wastes reviewer time, so every candidate is checked against the library before it counts (see "Library check"). When the scan finds something substantially new about a phenomenon that is already in the library, it does not report it as a new hit. It reports it as an **update find** on its own sheet, so the existing entry can be updated instead of duplicated.

The scan is open-ended by design. The analyst does not give a topic, because nobody can name in advance what only a scan would discover. Your own sweep strategy decides where to look.

---

## Step 0: Confirm before running

A full scan takes many searches and several minutes. When this skill activates, first confirm with the analyst using the pop-up question tool (AskUserQuestion) if it is available:

- Question: "Run the horizon scan now? (This can take several minutes.)"
- Options: "Run full scan (all 30 topics + blindspots)", "Only specific topics", "Cancel"

If the analyst already named specific topics in the request, offer those as the scope. If they pick "Only specific topics", ask which. For a scan of specific topics, also ask how many hits they want, unless the request already says:

- Question: "How many new hits do you want?"
- Options: "Default (2 to 3 per topic)", "More (about 5 to 8 per topic)", "As many credible hits as you can find"

The analyst can also give an exact number in their own words. If no pop-up tool exists, ask the same questions in plain text. If the session is clearly unattended (for example a scheduled run), skip the questions. Use the topics and number of hits named in the request, and otherwise run the full scan with the default number of hits.

---

## Scope and window

- **Default scope:** all 30 topics below, plus blindspots. The analyst may narrow this to specific topics.
- **Number of hits:** the default is set under "Sweep strategy". If the analyst asks for a different number, per topic or in total, their number replaces the default and its maximum. Only new hits count towards any number. Update finds never count towards it and never replace a new hit.
- **Geography:** global.
- **Look-back window:** developments that surfaced in the last 3 to 6 months, counted from today's date. A development older than that qualifies only if something new happened to it within the window (a reversal, a first deployment, a new law, a sharp acceleration). Record the window in the output.

### The 30 topics

1. Artificial Intelligence
2. Business
3. Climate Change
4. Communication & Media
5. Construction & Urbanisation
6. Countries & Regions
7. Data & Digitalisation
8. Education & Knowledge
9. Energy
10. Extended Reality VR / AR
11. Finance & Ownership
12. Food
13. Freight & Logistics
14. Global Economy
15. Health & Wellbeing
16. Industry & Manufacturing
17. Leisure & Lifestyles
18. Management & HR
19. Nature
20. Politics & Policies
21. Population
22. Private & Public Transport
23. Public Governance
24. Raw Materials
25. Sciences & Research
26. Security & Safety
27. Services
28. Sustainability & Recycling
29. Values & Ethics
30. Work & Income

A hit may belong to more than one topic. Write combinations as "Energy + Raw Materials" (two topics at most, main topic first).

---

## What counts as a hit

A hit is a candidate **phenomenon**: a durable development that could shift how a system works, not a one-off news item. Every phenomenon rests on a **core** of change. When you judge a candidate, ask: "What is changing at the root here?" If the answer is only "there was an announcement", it is not yet a hit.

### The core

- **Definition:** the core is the most fundamental level at which a system, relationship or dynamic is shifting. It must describe a shift in system logic, governing incentives, structural constraints or decision-making frameworks.
- **Test:** if the core can be restated as a simple trend, it is not enough. It has to say how the system works differently, not only what it does.
- **Role:** identify the core before you name or describe the hit, because it shapes everything else. The suggested name names it, the explanation follows from it, and the timeframe is the timeframe of the core change. If further research changes the core, revise the name, explanation and timeframe to match.
- **Limit:** the name must still answer the hit's topic. The core can sharpen the topic but not move away from it.

Write the core as one sentence of about 15 to 35 words. It goes in its own column so reviewers can judge it, and it goes into the Analyst brief as the starting core if the hit goes on to foresight-analyst.

Illustration only (do not reuse it as a hit or copy its wording):

- Fails the test (a simple trend): "More people use wearable health monitors."
- Passes: "Health monitoring moves from periodic clinic visits to continuous patient-generated data, which shifts who holds clinical evidence and when care decisions are made."

The core applies to every type. For a weak signal, it states the system shift the signal may point to. For a wild card, it states the logic that would flip. If you cannot state a core that passes the test, the candidate is not yet a hit.

Look for one of four types only:

| Type | Meaning | Sources needed |
|---|---|---|
| WEAK SIGNAL | One or two data points that may imply a bigger change to come. Concrete, specific, often niche. | 1 is enough |
| STRENGTHENING | A trend or issue growing in importance, quantity or impact | at least 2 independent |
| WEAKENING | A trend or issue declining in importance, quantity or impact | at least 2 independent |
| WILD CARD | A high-impact, low-probability event or development | 1 is enough |

Do not report ESTABLISHED or SUMMARY phenomena. Those are mature corpus entries, not scan output.

### Novelty markers worth searching for

"first", pilot, prototype, trial, breakthrough, new law or ban, court ruling, reversal, record, unexpected actor, new market, collapse, backlash, niche adoption, preprint, patent, funding round for a new category.

---

## Sweep strategy

Plan the work before searching. For each topic, run a light sweep of 2 to 4 searches built from novelty markers and the window, then go deeper only where a candidate appears. By default, aim for **2 to 3 new hits per topic, with 5 as the maximum**. Zero hits for a topic is an acceptable result. Never add filler rows to reach a quota, because weak rows waste reviewer time.

**When the analyst sets the number.** The analyst's number replaces the default target and the maximum. Reach it with more searching, not with weaker hits: widen the sub-themes within the topic, look at more regions and actors, and follow leads from the first hits. Every hit still needs a core that passes the test and enough sources for its type. If you cannot find enough credible hits, deliver the ones you have and state the shortfall in the scan notes and in the chat, for example "Found 6 of the 10 requested Energy hits".

**Narrow scans.** When the scope is one or a few topics, spend the time a full scan would need on searching those topics more deeply. Run more searches per topic and more far-out searches, even if the analyst kept the default number of hits. Deeper searching gives better candidates to choose from.

**Parallelise when you can.** If a subagent tool (Agent / Task) is available, split the topics into batches of about six and give each batch to its own subagent, plus one subagent for blindspots. Give every subagent the rules in this file (the core and its test, types, naming, timeframes, the far-out aim, sources, window, the library check via the **phenomena** skill, the hit and update-find fields) and ask it to return new hits and update finds as JSON in the shapes shown under "Output". Each subagent runs the library check on its own candidates as it finds them using **phenomena**, so it knows when its number of new hits is reached. Then merge the results yourself. Without subagents, work through the topics in order.

### Far-out hits

Searching recent news naturally finds changes that are already under way, so a scan drifts towards the near term. Reviewers also need the longer view. For each topic, aim for **at least one far-out hit**: a strengthening, weakening or wild card hit whose timeframe is 2035–2045 or later. Wild cards are common far-out hits, but a strengthening or weakening hit with a slow core (demographic, climate, institutional or infrastructural change, for example) counts just as well. Weak signals do not count towards this aim, because they carry no timeframe.

To find them, add 1 or 2 searches per topic aimed at long-range sources: early-stage science and preprints, long-term policy targets and strategies, deep-tech funding, long-range studies by think tanks and research institutes, and fringe or contrarian voices. A far-out hit still needs a trigger inside the look-back window and a core that passes the test.

This is an aim, not a quota. If no credible far-out hit turns up for a topic, do not stretch a near-term hit's timeframe or invent one. Instead, list the topic under "Topics without a far-out hit" in the scan notes, so the gap stays visible.

### Blindspots

The 30 topics are a lens, and every lens has edges. Reserve roughly 20% of the effort for blindspots, searched in four ways:

- **Intersections:** developments that fall between topics (for example AI × Food, Nature × Finance).
- **Outside the taxonomy:** themes with no obvious home, such as space, oceans, religion and spirituality, arts and culture, crime, animals.
- **Under-covered regions and actors:** the Global South, non-Western innovation, small or unusual actors.
- **Contrarian checks:** assumed trends that show signs of reversal, and "permanent" things that are weakening.

Label these hits in the Topic column as "Blindspot (nearest topic, nearest topic)", for example "Blindspot (Nature, Values & Ethics)".

---

## Library check

The Futures Platform phenomena library already holds thousands of phenomena. Check every candidate against it as soon as its core is clear, before you count it or research it further. Checking early saves the searching you would otherwise spend on a hit that gets dropped, and it tells you when a topic still needs more new hits.

### Phenomena skill (required for library access)

All library searches go through the **`phenomena`** skill ([`skills/phenomena/SKILL.md`](../phenomena/SKILL.md)). Read and follow it for:

- **FP MCP** connection (`fp-mcp`, bearer token, `/mcp`)
- Calling **`list-phenomena`** (not ad-hoc tool discovery)
- Parameters: `search` (≥ 2 characters unless using `ids`), `ids`, `types`, `per_page` (max 10, no further pages)

If **`list-phenomena`** is unavailable after following **phenomena**, say so to the analyst before the scan starts, run the scan without the check, write "Library check: not run (FP MCP not available)" in the scan notes, and leave the Update finds sheet empty. Do not guess which phenomena the library holds.

### How to search (per candidate)

Apply **phenomena** search tactics, then this scanner’s **2 or 3 short searches per candidate** (title matches rank first; one query often misses a differently worded entry):

1. The key noun phrase of the suggested name (for example "solid-state battery", not the full name).
2. The central concept of the core in other words: a synonym, the technology, the practice or the actor.
3. If the first two find nothing close, a broader parent term (for example "battery" for a battery chemistry).

Use `per_page: 5` on each **`list-phenomena`** call. Each result carries the full entry body, which is long, so judge matches from the title, type and summary. Read the body only for a likely match, to see what the entry already says.

To load an existing entry by id (update finds, tie-breakers), call **`list-phenomena`** with **`ids`** as described in **phenomena**.

### Judging a match

Compare cores, not names. The question is: "Does an existing phenomenon already describe this same shift at the root?"

- **Same core:** the existing phenomenon describes the same change at the same level, even if its name, type or framing differs.
- **Related only:** the existing phenomenon is broader, narrower or adjacent (for example "Electric Cars" for a hit on a new battery chemistry). A related match does not cover the hit. The hit stays new, and you name the closest match in its row so the reviewer can see the check was done.

Ignore archived phenomena (`archived: true`) when deciding whether a core is covered.

### Three outcomes

1. **New:** no existing phenomenon has the same core. Keep it as a hit. Only these count towards the number of hits.
2. **Already covered:** an existing phenomenon has the same core, and the candidate adds nothing substantially new. Drop it completely. It does not appear anywhere in the output, except in the count of dropped candidates on the Scan info sheet.
3. **Update find:** an existing phenomenon has the same core, and the candidate brings something substantially new about it. Report it on the Update finds sheet.

A development is **substantially new** only if it would change what the entry says or how it is classified. Use these reasons:

| Update reason | Meaning |
|---|---|
| Signal type change | The evidence suggests a different type, for example a weak signal that is now strengthening, or a strengthening trend that is now weakening. |
| New scale or milestone | A step change in scale, a first deployment, a new law, a market launch or a record that the entry does not reflect. |
| Contradicting evidence | New evidence speaks against the entry's core or its main claims. |
| Timeframe change | The evidence moves the likely timing of the core change to a different timeframe. |
| New regions or sectors | The change has spread to regions, sectors or actors the entry does not cover. |

New figures that only confirm what the entry already says are not substantially new. Neither is a development the entry already mentions, so check its summary and body. The development must also be newer than the entry's `updated_at` date and fall inside the look-back window. If the existing entry has no type, or its time range is missing, note that in the "What's new" text rather than treating it as a reason on its own.

If two candidates point to the same existing phenomenon, merge them into one update find with all their reasons and links. If two existing phenomena share the candidate's core (the library has some overlapping entries), attach the update find to the closer one and name the other in "What's new", so the reviewer can choose.

---

## Sources

Humans verify every hit, so sources may be more relaxed than in finished foresight entries. Weak signals often appear first in trade press, preprints, startup news or company announcements.

- **Acceptable:** established news media, research institutions, journals and preprints, think tanks, governments and multilateral bodies, trade and specialist press, company announcements, credible specialist blogs.
- **Exclude:** content farms, anonymous posts, AI-generated aggregators, anything without a traceable original.
- Link to the original source wherever possible, not to a site that repeats it.
- Two sources count as independent only if one does not simply repeat the other.

---

## Naming

The name names the core and must match the type. It must also answer the hit's topic. Keep names to 1 to 6 words and 50 characters or less, in Title Case. Add a geographic qualifier only when the phenomenon is place-specific ("in the US", "Cashless India").

- **WEAK SIGNAL:** name the concrete innovation, practice or event. Examples: "24/7 Solar Towers", "3D-Bioprinted Ovary", "Body-Heat Harvesting Wearables", "China Claims Land from Russia".
- **STRENGTHENING:** name the thing that is growing, as a plain noun phrase. Do not write "growth" or "rise", because the type carries the direction. Examples: "Electric Semi-Trucks", "Robotics in Healthcare", "Cashless Societies", "Resource Wars".
- **WEAKENING:** name the thing that is declining, neutrally. Do not write "decline". Examples: "Academic Freedom", "Affordable Housing", "Right to Privacy", "Car Ownership in Developed Countries".
- **WILD CARD:** name the discontinuity or flipped state of the world. Framing such as "End of", "Rise of", "Return of", "X Becomes Y" or "in Crisis" fits here. Examples: "End of Nation States", "Breakup of UK", "Return of Heavy Industry", "Cargo Ports Become Unnecessary".

## Timeframe

Give every strengthening, weakening and wild card hit exactly one timeframe from this fixed list. Weak signals get "-", because a single data point cannot support a timing judgement.

| Timeframe |
|---|
| 2027–2030 |
| 2030–2035 |
| 2035–2045 |
| 2045–2060 |
| 2060–2080 |
| 2080–2125 |

Choose the frame in which the core change is most likely to take hold and have its main effect. Check each frame against the evidence and pick the best fit. Do not invent other ranges, combine frames or give single years.

Judge when the core change takes hold, not when the first evidence appeared. Recent evidence often marks the start of a long change. A new law, pilot or funding round in 2026 can point to a shift that only reshapes the system in the 2040s. Any type can fall in any frame. Wild cards are often further out, but slow structural changes in strengthening and weakening hits can be too.

The timeframe is a suggestion for the reviewer, so keep it plausible rather than precise.

---

## Output

### Hit fields

Collect each new hit as a JSON object:

```json
{
  "topic": "Health & Wellbeing + Data & Digitalisation",
  "name": "Continuous Patient-Generated Health Data",
  "type": "STRENGTHENING",
  "core": "Health monitoring moves from periodic clinic visits to continuous patient-generated data, which shifts who holds clinical evidence and when care decisions are made.",
  "explanation": "1-3 short sentences: what is emerging and what follows from the core.",
  "evidence": "Moderate: 2 specialist sources",
  "timeframe": "2027–2030",
  "newest_source_date": "2026-09-12",
  "closest_match": "Wearable Health Technology (related only)",
  "links": ["https://...", "https://..."]
}
```

- **type:** one of WEAK SIGNAL, STRENGTHENING, WEAKENING or WILD CARD. This is your suggestion. The reviewer confirms or changes it.
- **core:** one sentence that passes the core test (see "The core").
- **explanation:** 1 to 3 sentences, the briefer the better. Say what is emerging and what may follow from the core. Do not repeat the core word for word. No filler.
- **evidence:** "Strong", "Moderate" or "Weak", then a colon and a short reason naming the number and kind of sources (established, specialist or fringe).
- **timeframe:** one value from the fixed list, written exactly as shown there, or "-" for weak signals.
- **closest_match:** the title of the closest existing phenomenon, exactly as in the library, followed by "(related only)". Write "None found" if the searches found nothing related.
- **links:** up to 5, one URL each.

### Update-find fields

Collect each update find as a JSON object:

```json
{
  "topic": "Energy + Private & Public Transport",
  "phenomenon_id": "0vYkvegDYaP7DabgkRPpB3n4R",
  "phenomenon_title": "Solid-State Battery",
  "current_type": "Weak signal",
  "current_time_range": "",
  "last_updated": "2023-03-07",
  "update_reasons": ["Signal type change", "New scale or milestone"],
  "whats_new": "1-3 short sentences: what has happened since the entry was last updated, and why it matters for the entry.",
  "core": "One sentence on the core of the change as the new evidence shows it.",
  "suggested_type": "STRENGTHENING",
  "suggested_timeframe": "2030–2035",
  "evidence": "Strong: 3 established sources",
  "newest_source_date": "2026-09-30",
  "links": ["https://...", "https://..."]
}
```

- **phenomenon_id, phenomenon_title, current_type, last_updated:** copy them from the library result exactly. `last_updated` is the date part of `updated_at`.
- **current_time_range:** the entry's `time_range` written as "min–max", or "" if it has none.
- **update_reasons:** one or more values from the table under "Library check", written exactly as there.
- **whats_new:** what the entry does not yet reflect. Be concrete, because the analyst uses this to decide whether the update is worth doing.
- **core:** the core as the new evidence shows it. It may sharpen the entry's existing core. It must pass the core test.
- **suggested_type and suggested_timeframe:** your suggestion after the new evidence, using the same values as for hits. Repeat the current type if you do not suggest a change. Weak signals get "-" as the timeframe.
- **links:** up to 5, the sources for the new development only. Strengthening and weakening suggestions need at least 2 independent links.

### Building the workbook

Before building, clean up the merged lists:

- Remove duplicates across topics. Keep the hit under its best-fitting topic. Two hits with the same core are duplicates even if their names differ.
- Check that every new hit went through the library check. If a subagent returned a hit without a `closest_match`, run the check now.
- Check that no new hit has the same core as an update find or another phenomenon in the library. If it does, move it to the update finds or drop it.
- Merge update finds that point to the same phenomenon ID.
- Check each core against the core test. Rewrite any core that only restates a trend, and drop the hit if no core passes.
- Check that each name names its core, matches its type and answers its topic.
- Check the timeframe: one of the six fixed values for strengthening, weakening and wild cards, and "-" for weak signals.
- Check the far-out aim: each topic in scope should have at least one new hit in 2035–2045 or later. Note any topic without one in the scan notes under "Topics without a far-out hit".
- Check the source rule: strengthening and weakening hits and suggestions need at least 2 independent links.
- Check the number of new hits against the target. Update finds do not count.
- Sort rows by topic number, with blindspots last.

Write everything to a JSON file with `scan_date`, `window`, `scope`, `library_check` (the full name of the tool you used, or "not run"), `dropped_as_covered` (the number of candidates dropped as already covered), optional `notes`, `hits` and `updates`. Then save the script below as `build_scan_sheet.py` in a scratch folder and run it:

```bash
python build_scan_sheet.py hits.json horizon_scan_YYYY-MM-DD.xlsx
```

```python
import json, sys
from collections import Counter
from openpyxl import Workbook
from openpyxl.styles import Alignment, Font, PatternFill
from openpyxl.worksheet.datavalidation import DataValidation

TIMEFRAMES = ["2027–2030", "2030–2035", "2035–2045", "2045–2060", "2060–2080", "2080–2125"]
TYPES = ["WEAK SIGNAL", "STRENGTHENING", "WEAKENING", "WILD CARD"]
REASONS = ["Signal type change", "New scale or milestone", "Contradicting evidence",
           "Timeframe change", "New regions or sectors"]
LINKS = [(f"Link {i}", 40) for i in range(1, 6)]
HIT_COLS = [("Topic", 24), ("Suggested name", 30), ("Suggested type", 16), ("Core", 55),
            ("Explanation", 55), ("Evidence strength", 28), ("Timeframe", 12),
            ("Newest source date", 14), ("Closest library match", 30), ("Reviewer decision", 18),
            ("Analyst brief", 60)] + LINKS
UPD_COLS = [("Topic", 24), ("Existing phenomenon", 30), ("Phenomenon ID", 28), ("Current type", 14),
            ("Current time range", 14), ("Last updated", 12), ("Update reasons", 28), ("What's new", 55),
            ("Core of new development", 55), ("Suggested type", 16), ("Suggested timeframe", 12),
            ("Evidence strength", 28), ("Newest source date", 14), ("Reviewer decision", 18),
            ("Update brief", 70)] + LINKS
HEAD_FILL = PatternFill("solid", fgColor="1F3864")


def type_label(t):
    return t.title() if t else ""


def analyst_brief(h):
    lines = ["Write a foresight entry from this horizon-scanner hit.",
             f"Topic: {h['name']}",
             f"Signal type: {type_label(h['type'])}"]
    if h["type"] != "WEAK SIGNAL":
        lines.append(f"Time horizon: {h.get('timeframe', '')}")
    lines += [f"Starting core: {h.get('core', '')}",
              f"Steering notes: {h.get('explanation', '')} Scanner topic area: {h['topic']}.",
              "Source mode: Mode B",
              "Sources:"] + [f"- {u}" for u in (h.get("links") or [])[:5]]
    return "\n".join(lines)


def update_brief(u):
    cur_type = u.get("current_type") or "not set"
    cur_tr = u.get("current_time_range") or "not set"
    sug_type = type_label(u.get("suggested_type", ""))
    sug_tf = u.get("suggested_timeframe", "-")
    lines = ["Update this existing Futures Platform phenomenon entry with new developments found by the horizon scanner.",
             f"Existing phenomenon: {u['phenomenon_title']}",
             f"Phenomenon ID: {u['phenomenon_id']}",
             "Existing entry: unless the entry text is already pasted or open, retrieve it using the phenomena skill "
             "(list-phenomena on fp-mcp with this ID in ids).",
             f"Current signal type: {cur_type}",
             f"Current time horizon: {cur_tr}",
             f"Last updated: {u.get('last_updated', '')}",
             f"Update reasons: {', '.join(u.get('update_reasons') or [])}",
             f"New developments: {u.get('whats_new', '')}",
             f"Core as the new evidence shows it: {u.get('core', '')}",
             f"Scanner's suggested signal type: {sug_type}"]
    if u.get("suggested_type") != "WEAK SIGNAL":
        lines.append(f"Scanner's suggested time horizon: {sug_tf}")
    lines += [f"Steering notes: Scanner topic area: {u['topic']}. Treat the suggested type and time horizon as input to "
              "the update-mode reassessment, not as decisions.",
              "Source mode: Mode B",
              "Sources for the new developments:"] + [f"- {x}" for x in (u.get("links") or [])[:5]]
    return "\n".join(lines)


def check_type_tf(label, t, tf):
    if t not in TYPES:
        print(f"WARNING: invalid type '{t}' for '{label}'")
    if t != "WEAK SIGNAL" and tf not in TIMEFRAMES:
        print(f"WARNING: invalid timeframe '{tf}' for '{label}'")


def write_sheet(ws, cols, rows, type_col, tf_col):
    for c, (name, width) in enumerate(cols, 1):
        cell = ws.cell(row=1, column=c, value=name)
        cell.font = Font(bold=True, color="FFFFFF")
        cell.fill = HEAD_FILL
        cell.alignment = Alignment(wrap_text=True, vertical="top")
        ws.column_dimensions[cell.column_letter].width = width
    first_link = len(cols) - 4
    for r, row in enumerate(rows, 2):
        for c, v in enumerate(row, 1):
            cell = ws.cell(row=r, column=c, value=v)
            cell.alignment = Alignment(wrap_text=True, vertical="top")
            if c >= first_link and v:
                cell.hyperlink = v
                cell.font = Font(color="0563C1", underline="single")
    ws.freeze_panes = "C2"
    ws.auto_filter.ref = ws.dimensions
    last = max(len(rows) + 1, 2)
    dv_type = DataValidation(type="list", formula1='"' + ",".join(TYPES) + '"', allow_blank=True)
    dv_tf = DataValidation(type="list", formula1='"' + ",".join(TIMEFRAMES + ["-"]) + '"', allow_blank=True)
    ws.add_data_validation(dv_type)
    ws.add_data_validation(dv_tf)
    dv_type.add(f"{type_col}2:{type_col}{last}")
    dv_tf.add(f"{tf_col}2:{tf_col}{last}")


def links5(x):
    links = (x.get("links") or [])[:5]
    return links + [""] * (5 - len(links))


data = json.load(open(sys.argv[1], encoding="utf-8"))
hits = data.get("hits", [])
updates = data.get("updates", [])

for h in hits:
    if h["type"] == "WEAK SIGNAL":
        h["timeframe"] = "-"
    check_type_tf(h.get("name", "?"), h["type"], h.get("timeframe", "-"))
    if not h.get("core"):
        print(f"WARNING: missing core for '{h['name']}'")
    if not h.get("closest_match"):
        print(f"WARNING: no library check recorded for '{h['name']}'")
for u in updates:
    if u.get("suggested_type") == "WEAK SIGNAL":
        u["suggested_timeframe"] = "-"
    label = u.get("phenomenon_title", "?")
    check_type_tf(label, u.get("suggested_type"), u.get("suggested_timeframe", "-"))
    if not u.get("phenomenon_id"):
        print(f"WARNING: missing phenomenon ID for update '{label}'")
    if not u.get("update_reasons"):
        print(f"WARNING: no update reason for '{label}'")
    for r in u.get("update_reasons") or []:
        if r not in REASONS:
            print(f"WARNING: invalid update reason '{r}' for '{label}'")
ids = Counter(u.get("phenomenon_id") for u in updates)
for i, n in ids.items():
    if n > 1:
        print(f"WARNING: {n} update finds share phenomenon ID {i}. Merge them.")

wb = Workbook()
ws = wb.active
ws.title = "New hits"
rows = [[h["topic"], h["name"], h["type"], h.get("core", ""), h.get("explanation", ""), h.get("evidence", ""),
         h.get("timeframe", "-"), h.get("newest_source_date", ""), h.get("closest_match", ""), "",
         analyst_brief(h)] + links5(h) for h in hits]
write_sheet(ws, HIT_COLS, rows, "C", "G")

wu = wb.create_sheet("Update finds")
rows = [[u["topic"], u["phenomenon_title"], u["phenomenon_id"], u.get("current_type", ""),
         u.get("current_time_range", ""), u.get("last_updated", ""), ", ".join(u.get("update_reasons") or []),
         u.get("whats_new", ""), u.get("core", ""), u.get("suggested_type", ""), u.get("suggested_timeframe", "-"),
         u.get("evidence", ""), u.get("newest_source_date", ""), "", update_brief(u)] + links5(u) for u in updates]
write_sheet(wu, UPD_COLS, rows, "J", "K")

info = wb.create_sheet("Scan info")
for k in ["scan_date", "window", "scope", "library_check", "notes"]:
    info.append([k.replace("_", " ").capitalize(), str(data.get(k, ""))])
info.append(["New hits", len(hits)])
info.append(["Update finds", len(updates)])
info.append(["Candidates dropped as already covered", data.get("dropped_as_covered", "")])
info.append([])
info.append(["New hits per topic", ""])
for t, n in Counter(h["topic"] for h in hits).items():
    info.append([t, n])
far = set(TIMEFRAMES[2:])
info.append([])
info.append(["Far-out new hits (2035–2045 or later)", sum(1 for h in hits if h.get("timeframe") in far)])
info.append([])
info.append(["New hits per timeframe", ""])
for t in TIMEFRAMES + ["-"]:
    info.append([t, sum(1 for h in hits if h.get("timeframe") == t)])
info.append([])
info.append(["Update finds per reason", ""])
for r in REASONS:
    info.append([r, sum(1 for u in updates if r in (u.get("update_reasons") or []))])
info.column_dimensions["A"].width = 40
info.column_dimensions["B"].width = 60
wb.save(sys.argv[2])
print(f"Saved {len(hits)} new hits and {len(updates)} update finds to {sys.argv[2]}")
```

The workbook has three sheets:

- **New hits:** Topic, Suggested name, Suggested type, Core, Explanation, Evidence strength, Timeframe, Newest source date, Closest library match, Reviewer decision (empty, for the human), Analyst brief, Link 1 to Link 5. The Analyst brief is a labelled, ready-to-copy request for the foresight-analyst skill: the analyst copies the cell and pastes it to turn the hit into a full entry.
- **Update finds:** Topic, Existing phenomenon, Phenomenon ID, Current type, Current time range, Last updated, Update reasons, What's new, Core of new development, Suggested type, Suggested timeframe, Evidence strength, Newest source date, Reviewer decision, Update brief, Link 1 to Link 5. The Update brief is a ready-to-copy request that puts foresight-analyst in update mode. It names the existing phenomenon and its ID, tells foresight-analyst how to fetch the current entry from the library, and carries the new developments, the suggested changes and their sources.
- **Scan info:** the scan date, window, scope, library check, notes (including topics without a far-out hit), the number of new hits, update finds and dropped candidates, new hits per topic, far-out new hits, new hits per timeframe and update finds per reason.

The script builds both briefs from the fields, so you do not write them yourself. Suggested type and timeframe columns have drop-down lists so the reviewer can change them. If the script prints warnings, fix the JSON and run it again. Save the file where the user can open it (in Cowork, the outputs folder) and deliver it.

In the chat, report only: the number of new hits (and any shortfall against a number the analyst asked for), the number of update finds, the number of candidates dropped as already covered, the topics with zero new hits, the topics without a far-out hit, and at most three new hits or update finds that look most noteworthy. Do not repeat the sheet.

---

## Language

British English. Plain, neutral wording. No semicolons or em dashes in names or explanations.