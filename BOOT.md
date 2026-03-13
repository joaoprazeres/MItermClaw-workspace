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
| **MItermClaw** 🦔 | `~/.openclaw/workspace/` | Main admin assistant |
| **DailyClaw** 🔍 | `~/dailyclaw/` | Daily buddy (WhatsApp route) |
| **DevClaw** 🛠️ | `~/openclaw-dev/` | Development |

## Channels
- WebChat ✅ (default)
- WhatsApp 🔗 → DailyClaw

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