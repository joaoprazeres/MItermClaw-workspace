# Context Optimizer - Hybrid Approach Plan

## Current State (Pre-Implementation)
- **Main session:** 129,834 tokens (101% - OVERFLOW)
- **Daily session:** 8,045 tokens (6%)
- **Workspace files:** ~5,250 tokens (~4%)
- **User history:** ~124,500 tokens (~96%)
- **Threshold:** 80% (too late)

## Problem
Context overflow causes agent to freeze/hang with no output. The session accumulates too much before compaction triggers.

## Proposed Hybrid Solution

### Tier 1: Proactive Monitoring (Continuous)
- Check context usage every 10 messages or 5 minutes (whichever comes first)
- Threshold lowered to **50%** for warning, **70%** for action
- Use a lightweight cron job or heartbeat check

### Tier 2: Smart Summarization (Before Truncation)
Instead of just deleting old messages:
1. Take last N messages before truncation point
2. Ask LLM to summarize them into 2-3 sentences
3. Save to `memory/summarized/YYYY-MM-DD.json`
4. Keep summarized version in context instead of raw messages

### Tier 3: Context Injection (On-Demand)
- Don't load full chat history
- Use semantic search to find relevant past messages
- Inject only relevant context for current topic
- Keep a "memory index" of what's been discussed

### Tier 4: Session Archiving (Topic Shift)
When topic shift detected:
1. Archive current session to `memory/sessions/archived-YYYY-MM-DD-HHMM.jsonl`
2. Start fresh session
3. Add context anchor: "Previous topic: X. Summary: Y"

## Implementation Steps

### Step 1: Hotfix - Emergency Context Trim
- Run immediately to reduce main from 101% to ~50%
- Method: Keep last 50 messages, summarize older to memory file

### Step 2: Update context_optimizer.py
- Add `check_interval` config (default: 10 messages)
- Add `warn_threshold` (50%) and `action_threshold` (70%)
- Implement summarize_old_messages() function
- Implement archive_session() function

### Step 3: Create memory/summarized/ structure
- Directory for archived summaries
- JSON format: {"date": "", "topic": "", "summary": "", "message_count": N}

### Step 4: Integration with HEARTBEAT.md
- Add context check to heartbeat
- Add automatic recovery if agent hangs

## Recovery Procedure (If Agent Hangs)
1. Detect no response for >2 minutes during agent turn
2. Kill current session
3. Load last summary from `memory/summarized/`
4. Resume with: "We were discussing X. Here's the summary: Y"

## Files to Modify
- `~/openclaw-dev/scripts/context_optimizer.py` (main logic)
- `~/openclaw/workspace/HEARTBEAT.md` (add context check)
- Create: `memory/summarized/` directory
- Create: `memory/sessions/` for archiving

## Expected Result
- Keep context under 70% at all times
- Never lose conversation context (summarized, not deleted)
- Agent recovers automatically if hangs

---
**Status:** Awaiting approval to implement
**Created:** 2026-03-14