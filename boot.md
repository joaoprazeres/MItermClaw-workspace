# 🔔 OpenClaw Instance Status

## Quick Reference - Full docs: ~/openclaw-dev/projects/OPENCLAW-README.md

### 👥 Agents
- **MItermClaw** (🦔) - Main assistant - `~/.openclaw/workspace/`
- **DevClaw** (🛠️) - Development - `~/openclaw-dev/`
- **DailyClaw** (🔍) - Daily companion + WhatsApp - `~/dailyclaw/`

### 👑 God Layer (Models)
1. Local Ollama: minimax-m2.5:cloud (default)

### Core Systems
- **Memory:** 3-layer (Short/Mid/Long) + Named memories
- **Internet:** SearXNG + Gemini search, Research loop
- **RAG:** Project-isolated vector indexes (nomic-embed-text)

### Channels
- WebChat ✅ (MItermClaw)
- WhatsApp ✅ → DailyClaw

### Recovery
- Script: `~/openclaw-dev/scripts/openclaw-recover.sh`
- Run: `-d` (diagnostic), `-g` (gateway), `-c` (config), `-a` (all)

### ⚡ Context Management (IMPORTANT)
If conversation gets long and you notice context issues:
- Keep responses concise
- Don't repeat previous content unnecessarily
- Reference memory files instead of restating
- If context error occurs, acknowledge and continue gracefully

---

*Full documentation: ~/openclaw-dev/projects/OPENCLAW-README.md*