# OpenClaw Development Progress

**Last Updated:** 2026-03-13 20:38 UTC

---

## 🎯 Current Focus

- Context window optimization (compaction settings too tight - agents can't handle follow-up questions)
- Memory/context issue: tightened too much, causing memory to be too short

---

## 🚧 In Progress

| Item | Location | Notes |
|------|----------|-------|
| Context optimization | `projects/TODO-context-optimization.md` | Topic-based compaction design |
| Compaction settings tuning | OpenClaw config | Need to adjust reserveTokens/keepRecentTokens |
| Restore plugins section | `openclaw.json` | Missing from damaged config |

---

## 🛑 Blocked

- **Compaction too aggressive** — memory too short, agents can't answer follow-up questions
- Need to find and adjust Pi compaction settings (reserveTokens, keepRecentTokens)

---

## ✅ Done

### Infrastructure
- [x] GitHub backup (3 repos: MItermClaw, MItermClaw-workspace, MItermClaw-dev)
- [x] God layer config (minimax-m2.5:cloud → phi4-mini:3.8b → phi4)
- [x] Dev workspace (`~/openclaw-dev/`)

### Memory System
- [x] Architecture designed (4 layers: short/mid/long/named)
- [x] `memory_index.py` - Vector search using nomic-embed-text
- [x] Folder structure created

### Internet Access
- [x] Architecture designed
- [x] `internet.py` - Simple search + Research loop
- [x] SearXNG integration working

### RAG
- [x] Architecture designed
- [x] `rag.py` - Full CLI implementation
- [x] Index created for projects

### Skills
- [x] `project-management-2` installed via clawdhub

---

## 📋 Next Steps

1. **Fix compaction** — Adjust reserveTokens/keepRecentTokens to be less aggressive
2. **Test topic shift detection** — Implement or tune the trigger
3. **Restore plugins** — Add web-search plugin from damaged config
4. **Test memory catch-up** — Verify progress file works after context loss

---

## 📁 Key Files

| Purpose | Path |
|---------|------|
| Dev workspace | `~/openclaw-dev/` |
| Main workspace | `~/.openclaw/workspace/` |
| Config | `~/.openclaw/openclaw.json` |
| Roadmap | `~/openclaw-dev/projects/openclaw-v1 roadmap.md` |
| Memory arch | `~/openclaw-dev/projects/memory-architecture.md` |
| Context TODO | `~/openclaw-dev/projects/TODO-context-optimization.md` |
| Internet script | `~/openclaw-dev/scripts/internet.py` |
| RAG script | `~/openclaw-dev/scripts/rag.py` |
| Memory script | `~/openclaw-dev/scripts/memory_index.py` |

---

## 🔗 Repos

- `github.com/joaoprazeres/MItermClaw` — OpenClaw module
- `github.com/joaoprazeres/MItermClaw-workspace` — Main workspace
- `github.com/joaoprazeres/MItermClaw-dev` — Dev workspace

---

*Read this file at session start to catch up quickly*