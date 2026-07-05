# Prompt 01 - Verify Integration Point
I need to verify the exact integration point for a shadow-mode pre-LLM context processing layer in this Java / Spring Boot / Google ADK project.
Please inspect the actual repository and dependencies. Do not modify any files.
Goal:
Find the safest place to intercept the final assembled Prompt before it is sent to Gemini, run metrics on a copy, and still send the original Prompt to Gemini.
Please verify these things from real code, not assumptions:
## 1. LanguageModel / Gemini model interface
- Does the project use a LanguageModel interface?
- Does the project use a GeminiLanguageModel implementation?
- What exact method sends the prompt to Gemini?
- Show the exact method signature.
- Show the exact import/package names.
- Show whether the method is sync, async, streaming, or returns a reactive type.
## 2. Prompt object structure
- What Prompt class/type is used?
- What fields/methods does Prompt expose?
- How is message/content text stored?
- Is there a safe way to extract the full assembled prompt/context as text?
- Is prompt.toString() useful or unsafe/incomplete?
- If Prompt contains messages/parts/content objects, show the exact APIs to read them.
## 3. Bean configuration
- Where is the Gemini/LanguageModel bean configured?
- Show the exact file path.
- Show the exact class name and method name.
- Is the Gemini model created directly in config or somewhere else?
- Is it injected into the ADK Agent?
- Can we wrap the LanguageModel bean without changing the rest of the application?
## 4. Request flow confirmation
Confirm or correct this flow:
API/controller
→ support/orchestration service
→ ADK Agent
→ Prompt assembled internally
→ LanguageModel / Gemini model call
→ Gemini API
Show exact files/classes/methods for each step.
## 5. Best shadow-mode integration point
Based on the verified types and signatures, tell me the best place to add a wrapper/interceptor.
Shadow mode must:
- receive the final Prompt
- extract or serialize a copy of the prompt/context as text
- run metrics on that copy
- log raw chars, processed chars, estimated saved tokens, savings percent, notes, and latency
- still call the original Gemini model with the original Prompt
- not change model output behavior
## 6. Risks
List risks:
- Prompt extraction may miss hidden/system/tool context
- wrapper may break streaming/async behavior
- logging may expose sensitive prompt content
- latency overhead
- token estimation accuracy
- bean injection issues
Return:
- exact verified class names
- exact verified method signatures
- exact file paths
- recommended wrapper location
- whether this should be a package inside the main agent for first spike or a Maven module
- what I should not change yet
Do not write code yet. Only analysis and verification.
