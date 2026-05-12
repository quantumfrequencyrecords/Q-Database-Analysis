# Q Archive — Research Database
## Offline-First Research Tool · v1.0.0

A structured, neutral investigative archive for researching alleged Q / QAnon drops.
All content treated as unverified claims. Fact, theory, context, and open questions are clearly separated.

---

## File Structure

```
qarchive/
├── index.html        ← Main interface (open this)
├── manifest.json     ← Master index of all drops and metadata
├── drop_001.json     ← Individual drop data files
├── drop_002.json
├── drop_003.json
├── ... (one per drop)
└── README.md
```

---

## How to Run

### Option 1 — Python Local Server (Recommended)
```bash
cd qarchive/
python3 -m http.server 8000
# Then open: http://localhost:8000
```

### Option 2 — Node.js
```bash
npx serve qarchive/
```

### Option 3 — File Picker (in-browser)
Open index.html directly, click **"Select Archive Folder…"** and select this folder.

> **Note:** Due to browser security restrictions, opening `index.html` via `file://` 
> directly will not be able to load the JSON files automatically. Use one of the 
> server options above for the best experience.

---

## Adding New Drops

1. Create a new `drop_NNN.json` file following the schema below
2. Add an entry to `manifest.json` under the `"drops"` array
3. Click **"⟳ Refresh"** in the archive sidebar

No changes to `index.html` are needed.

---

## Drop JSON Schema

```json
{
  "drop_number": 1,
  "datetime": "2017-10-28T15:44:00Z",
  "platform": "4chan /pol/",
  "board": "/pol/",
  "tripcode": "Q !ITPb.qbhqo",
  "title": "Short descriptive title",
  "summary": "2-3 sentence neutral summary of the drop's content and significance.",
  "raw_text": "The exact text of the drop as posted.",
  "themes": ["Theme1", "Theme2"],
  "related_drops": [2, 3],
  "sources": [
    {
      "label": "Source name",
      "url": "https://...",
      "note": "What this source provides"
    }
  ],
  "lines": [
    {
      "text": "A single line or meaningful segment from the raw drop",
      "fact": "Documented, verifiable information. Clearly state what is and is not confirmed.",
      "theory": "Interpretations and theories. Label as such. Do not present as fact.",
      "context": "Background information that helps a reader understand the line.",
      "questions": "Open questions a researcher should ask about this line.",
      "confidence": 50,
      "sources": [
        {"label": "Source label", "url": "https://..."}
      ]
    }
  ]
}
```

### Confidence Scale
- **0–20**: Claim is contradicted by evidence or is a failed prediction
- **21–40**: Claim is unverified speculation; no supporting evidence found
- **41–60**: Mixed or ambiguous; partial evidence exists
- **61–80**: Likely accurate based on available evidence; some uncertainty
- **81–100**: Verified by primary sources or official documentation

---

## Manifest.json Schema

```json
{
  "version": "1.0.0",
  "drops": [
    {
      "num": 1,
      "file": "drop_001.json",
      "date": "2017-10-28",
      "datetime": "2017-10-28T15:44:00Z",
      "platform": "4chan /pol/",
      "preview": "First ~150 chars of raw text for sidebar display",
      "tags": ["tag1", "tag2"],
      "themes": ["Theme1"]
    }
  ],
  "topics": ["Topic1", "Topic2"],
  "abbreviations": [
    {
      "abbr": "HRC",
      "meaning": "Hillary Rodham Clinton",
      "category": "Named Individuals",
      "certainty": "confirmed",
      "notes": "Standard initials"
    }
  ]
}
```

### Certainty Values for Abbreviations
- `confirmed` — Verified by primary sources
- `likely` — Strong contextual evidence
- `disputed` — Multiple competing interpretations
- `unknown` — No reliable basis for interpretation

---

## Keyboard Shortcuts

| Key | Action |
|-----|--------|
| `←` or `h` | Previous drop |
| `→` or `l` | Next drop |
| `b` | Toggle bookmark |
| `/` | Focus search |
| `Esc` | Clear search focus |

---

## Research Principles

This archive is built on the following principles:

1. **Separation of fact and theory** — Every analysis block is labeled
2. **Primary sources** — Claims are linked to primary documents where available
3. **Failed predictions documented** — Specific, falsifiable predictions that did not occur are noted
4. **Context provided** — Background information helps readers evaluate claims independently
5. **No advocacy** — The archive does not endorse or promote Q claims
6. **Antisemitic tropes flagged** — Where Q content echoes documented antisemitic conspiracy theories, this is noted with academic sources

---

## Recommended External Resources

- **qalerts.app** — Drop aggregator and reference index
- **ADL QAnon research** — adl.org
- **Snopes QAnon fact-checks** — snopes.com
- **Reuters fact-checking** — reuters.com/fact-check
- **Media Manipulation Casebook** — mediamanipulation.org
- **Stanford Internet Observatory** — cyber.fsi.stanford.edu

---

*This is a research tool. Think critically. Consult primary sources.*
