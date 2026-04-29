# The Daily Reflection Tree
### DT Fellowship Assignment — BA/DS Role

---

## Overview

A deterministic end-of-day reflection tool that walks an employee through three psychological axes:

1. **Locus of Control** (Victim ↔ Victor) — Did you navigate today, or did today happen to you?
2. **Contribution vs Entitlement** — Did you track what you gave, or what you were owed?
3. **Radius of Concern** — Was your view self-contained, or did it extend to others?

**No LLM is called at runtime.** The tool is a static decision tree walked by simple JavaScript logic. All branching is deterministic — same answers, same path, every time.

---

## Repository Structure

```
/tree/
  reflection-tree.json       ← Part A: full tree data (31 nodes)
/agent/
  index.html                 ← Part B: working web agent (open in any browser)
/transcripts/
  persona-1-transcript.md    ← Victim / Entitled / Self-centric path
  persona-2-transcript.md    ← Victor / Contributing / Altrocentric path
write-up.md                  ← Design rationale (2 pages)
README.md                    ← This file
```

---

## How to Run the Agent

**No installation required.**

1. Download `agent/index.html`
2. Open it in any modern web browser (Chrome, Firefox, Safari, Edge)
3. That's it — no server, no dependencies, no API keys

The agent loads the tree logic embedded in the HTML file. If you prefer to load the JSON externally, serve the files via a local server:

```bash
# Python (from project root)
python3 -m http.server 8000
# Then open: http://localhost:8000/agent/index.html
```

---

## How to Read the Tree (tree/reflection-tree.json)

Each node has:

| Field | Purpose |
|-------|---------|
| `id` | Unique identifier |
| `type` | `start`, `question`, `decision`, `reflection`, `bridge`, `summary`, `end` |
| `text` | What the user sees (strings with `{placeholder}` for interpolation) |
| `options` | For `question` nodes: pipe-separated user-visible choices |
| `decide` | For `question` nodes: routing logic (embedded in agent as switch logic) |
| `signal` | What this node records in state (`axis1:internal`, `axis2:contribution`, etc.) |
| `next` | For non-question nodes: where to go after this node |

### Tracing a path manually

Follow `next` fields from `START`. At `question` nodes, pick an option and follow the `decide` logic. At `reflection` and `bridge` nodes, follow `next`. Reach `SUMMARY` when all three axes are complete.

### Decision logic

Decision routing is embedded in the agent as:
```javascript
decide: (answer) => ["option A", "option B"].includes(answer) ? "NODE_X" : "NODE_Y"
```

This is equivalent to the TSV routing syntax: `answer=A|B:NODE_X;else:NODE_Y`

---

## Tree Statistics

| Metric | Count |
|--------|-------|
| Total nodes | 31 |
| Question nodes | 10 |
| Decision nodes | 7 (embedded in question nodes) |
| Reflection nodes | 6 |
| Bridge nodes | 2 |
| Summary nodes | 1 |
| Start/End nodes | 2 |
| Unique conversation paths | 16 |
| Per-axis signal combinations | 2³ = 8 closing insights |

---

## Psychological Grounding

- **Axis 1** — Rotter's Locus of Control (1954) + Dweck's Growth Mindset (2006)
- **Axis 2** — Campbell et al.'s Psychological Entitlement (2004) + Organ's OCB (1988)
- **Axis 3** — Maslow's Self-Transcendence (1969) + Batson's Perspective-Taking (2011)

See `write-up.md` for full design rationale.

---

## Design Principles

1. **No moralizing** — Someone on the "external/entitlement/self" path gets reflection, not a grade
2. **Honest options** — Every option set includes choices a real person would actually make
3. **Axis continuity** — Each axis opening references the previous axis's insight
4. **Interpolation** — Summary references the user's actual answers, not generic text
5. **Determinism** — Zero randomness, zero LLM calls at runtime
