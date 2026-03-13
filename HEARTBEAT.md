# HEARTBEAT.md

# Keep this file empty (or with only comments) to skip heartbeat API calls.

# Add tasks below when you want the agent to check something periodically.

## Context Monitoring
- Check session context sizes for main and daily agents
- If context > 60%, warn the user
- If context > 80%, **auto-run compaction** to free up context

Commands:
```bash
python3 ~/openclaw-dev/scripts/context_optimizer.py status
python3 ~/openclaw-dev/scripts/context_optimizer.py check
```

**Auto-compaction threshold:** 80% (102,400 tokens out of 128,000)

**Topic-shift detection:** Uses semantic similarity to detect topic changes and trigger appropriate compaction level.
