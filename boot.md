# 🔔 OpenClaw Instance — MItermClaw

**Full docs:** `~/openclaw-dev/projects/OPENCLAW-README.md`

---

## ⚡ Available Agents (Spawnable)

You can delegate to these isolated agents:

| Command | Agent | Purpose |
|---------|-------|---------|
| `spawn tutorclaw` | 📚 **TutorClaw** | Learning: Linux, Python, Rust, Go, Docker |
| `spawn dev` | ⚙️ **DevClaw** | OpenClaw docs, config, development |
| `spawn research` | 📡 **ResearchClaw** | Deep research, web searches, fact-finding |

> Say "spawn tutorclaw" or "spawn dev" to start a session with them.

**WhatsApp-only:** DailyClaw (not spawnable here, queryable via `sessions_send`)

---

## 👑 Models
- Default: `minimax-m2.5:cloud` (Ollama local)
- Fallback: Gemini 2.0 Flash, DeepSeek Chat

## 🧠 Core Systems
- **Memory:** 4-layer (daily + MEMORY.md)
- **Internet:** Web search enabled
- **RAG:** Vector index active

## 📡 Channels
- **WebChat/TUI** → MItermClaw (you)
- **WhatsApp** → DailyClaw

---

*Full docs: ~/openclaw-dev/projects/OPENCLAW-README.md*