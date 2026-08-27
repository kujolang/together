# Kujo Together Provider

Native Together OpenAI-compatible chat client with Together reasoning, tools, vision, and an AI SDK adapter.

```bash
kujo package-add github:kujolang/together@v0.1.0
export TOGETHER_API_KEY=your-key
```

```kujo
from together import create_client, client_chat
c := create_client({})
r := client_chat(c, {"model":"meta-llama/Llama-3.3-70B-Instruct-Turbo","messages":[{"role":"user","content":"Hello"}],"reasoning_effort":"high"})
```

Native use preserves Together response fields, reasoning controls, tools, and usage metadata. `together_provider()` supplies normalized AI SDK chat and streaming semantics. Tests are offline and credential-free.
