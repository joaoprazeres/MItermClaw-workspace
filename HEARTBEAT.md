# HEARTBEAT.md

# Keep this file empty (or with only comments) to skip heartbeat API calls.

# Add tasks below when you want the agent to check something periodically.

## Context Monitoring (HYBRID CONTEXT OPTIMIZER)

**Check frequency:** Every ~10 messages OR every 5 minutes (rotate checks)

### Thresholds:
- **50%** (64,000 tokens): WARN user
- **70%** (89,600 tokens): AUTO-ACTION - summarize + archive
- **80%** (102,400 tokens): Force compaction

### Commands:
```bash
# Quick status check
python3 ~/openclaw-dev/scripts/context_optimizer.py status

# Auto-optimize (hybrid)
python3 ~/openclaw-dev/scripts/context_optimizer.py check-optimize

# Manual options
python3 ~/openclaw-dev/scripts/context_optimizer.py summarize main
python3 ~/openclaw-dev/scripts/context_optimizer.py archive main
```

### Auto-Recovery (if session hangs):
1. Save state to `memory/2026-03-14.md`
2. Check `memory/summarized/` for last summary
3. Load last summary and resume from there
4. If needed, restore from `memory/sessions/archived/`

### Files Created:
- `memory/summarized/` - Summary archives by date
- `memory/sessions/archived/` - Full session backups

### Topic-shift Detection:
Still active - uses semantic similarity to detect topic changes.