# Prompt 03 - Review Shadow-Mode Implementation
Please review the current shadow-mode implementation.
Do not modify files yet.
Check:
1. Does Gemini/ADK still receive the original Prompt/context?
2. Is the processor only running on a copy?
3. Are we avoiding logging raw prompt content?
4. Are metrics safe and useful?
5. Is latency measured?
6. Is there a config flag for off / shadow / active?
7. Is active mode disabled by default?
8. Are tests sufficient?
9. Is the code easy to remove if needed?
10. Are there any security or privacy risks?
Return:
- what is correct
- what is risky
- what must be fixed before merge
- what can wait
- whether this is safe for a first internal spike
