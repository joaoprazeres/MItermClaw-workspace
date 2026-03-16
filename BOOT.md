# 🚀 OpenClaw Instance Boot

**Full documentation:** `~/openclaw-dev/projects/OPENCLAW-README.md`

## Quick Status

| Component | Status |
|-----------|--------|
| **God Layer** | ✅ 3-model fallback ready |
| **Memory** | ✅ 4-layer system working |
| **Internet** | ✅ Search + Research Loop |
| **RAG** | ✅ Vector index active |

## Agents

| Agent | Workspace | Purpose |
|-------|-----------|---------|
| **MItermClaw** 🦔 | `~/.openclaw/workspace/` | Main admin assistant (TUI/Browser landing) |
| **DailyClaw** 🔍 | `~/dailyclaw/` | WhatsApp-only (queryable) |
| **TutorClaw** 📚 | `~/tutor-workspace/` | Learning: Linux, Python, Rust, Go, Docker |
| **DevClaw** ⚙️ | `~/openclaw-dev/` | Development & OpenClaw docs |
| **ResearchClaw** 📡 | `~/research-workspace/` | Deep research, web searches, fact-finding |

## Spawnable from MItermClaw
- `tutorclaw` — for learning tasks
- `dev` — for OpenClaw config/dev questions
- `research` — for deep research tasks

## Channels
- WebChat ✅ (MItermClaw)
- WhatsApp ✅ (DailyClaw)

## Key Scripts
- `~/openclaw-dev/scripts/memory_index.py` - Vector memory
- `~/openclaw-dev/scripts/rag.py` - Knowledge index
- `~/openclaw-dev/scripts/internet.py` - Web research

## Recovery
```bash
~/openclaw-dev/scripts/openclaw-recover.sh -d  # Diagnostic
```

---

*See full docs: ~/openclaw-dev/projects/OPENCLAW-README.md*