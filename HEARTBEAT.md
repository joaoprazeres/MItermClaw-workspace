# HEARTBEAT.md

# Keep this file empty (or with only comments) to skip heartbeat API calls.

# Add tasks below when you want the agent to check something periodically.

## Context Monitoring
- Check session context sizes for main and daily agents
- If context > 60%, warn the user
- If context > 80%, suggest compaction

Commands:
```bash
~/openclaw-dev/scripts/context-wrapper.sh status --agent main
~/openclaw-dev/scripts/context-wrapper.sh status --agent daily
```
