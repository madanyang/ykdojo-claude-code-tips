# Project Instructions

## Git Commit Guidelines
- Never add "Generated with Claude Code" or similar AI attribution in commit messages

## Writing Style for Tips
- Stay close to the user's original voice when they dictate content
- Don't paraphrase too much or add information they didn't mention
- Keep a conversational, personal tone - not too dry
- Use first person ("I found that...") to maintain authenticity
- Never use em dashes

## Debugging: /context 400 Error

Running `/context` as the first command in a fresh Claude Code session causes a 400 error:

```
Error: 400
{"type":"error","error":{"type":"invalid_request_error","message":"messages: text content blocks must contain non-whitespace text"}}
```

### Reproduction via tmux

```bash
tmux kill-session -t repro-400 2>/dev/null
tmux new-session -d -s repro-400
tmux send-keys -t repro-400 'claude' Enter
sleep 2
tmux send-keys -t repro-400 '/context' Enter
sleep 0.5
tmux send-keys -t repro-400 Enter
sleep 1
tmux capture-pane -t repro-400 -p
```

This lets Claude control another Claude Code instance for testing.
