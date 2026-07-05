# Prompt 02 - Smallest Shadow-Mode Implementation Plan
Based on your verified analysis, propose the smallest safe implementation plan for shadow-mode pre-LLM context processing.
Do not modify files yet.
Constraints:
- Do not change model output behavior yet.
- Gemini/ADK must still receive the original full Prompt/context.
- The processing should only run on a copy of the assembled prompt/context.
- Log estimated savings only.
- No dashboard yet.
- No active mode yet.
- No MCP retrieval loop.
- No large architecture rewrite.
- Keep the change small and easy to review.
Shadow mode behavior:
1. Receive final assembled Prompt/context.
2. Extract or serialize a copy as text.
3. Run the context processor on the copy.
4. Log:
   - raw char count
   - processed char count
   - estimated raw tokens
   - estimated processed tokens
   - estimated saved tokens
   - estimated savings percent
   - notes
   - latency ms
5. Send original Prompt/context to Gemini unchanged.
Return:
1. Files that need to change.
2. New files/classes needed, if any.
3. Exact method where shadow mode should be inserted.
4. Configuration flag suggestion: off / shadow / active.
5. Minimal test plan.
6. Risks.
7. What not to implement yet.
Do not write code yet.
