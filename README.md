# Kujo Together Provider

[![Version](https://img.shields.io/badge/version-0.1.1-black)](https://github.com/kujolang/together/releases/tag/v0.1.1)
[![License](https://img.shields.io/badge/license-MIT-lightgrey)](LICENSE)
[![built with Kujo](https://img.shields.io/badge/built%20with-Kujo-white.svg)](https://github.com/kujolang/kujo)

Together AI chat and native model services for Kujo.

## Install

```bash
kujo run /path/to/kennel/kennel.kujo --interpreter -- add github:kujolang/together@v0.1.1 --alias together
kujo run /path/to/kennel/kennel.kujo --interpreter -- install
export TOGETHER_API_KEY=your-key
```

## 30-second quick start

```kujo
from together import create_client, client_chat

client := create_client({})
request := {
    "model": "meta-llama/Llama-3.3-70B-Instruct-Turbo",
    "messages": [
        {
            "role": "user",
            "content": "Hello from Kujo!"
        }
    ]
}

result := client_chat(client, request)

print(result["data"]["choices"][0]["message"]["content"])
```

## Native API

The native layer preserves Together chat responses, tools, reasoning, vision, model metadata, and native embeddings. Images, audio, video, fine-tuning, files, and batch workflows remain provider-owned.

## AI SDK integration

`together_provider({"model": "meta-llama/Llama-3.3-70B-Instruct-Turbo"})` supplies normalized chat and streaming semantics through the compatible driver.

## Authentication and security

Set `TOGETHER_API_KEY`. Remote endpoints require HTTPS; credentials are redacted and never committed to fixtures.

## Testing and documentation

```bash
bash scripts/release_quality_gate.sh
bash scripts/verify_installed_package.sh
```

The default gate is deterministic and offline. See [docs/](docs/) for implementation and Contract v1 evidence.
