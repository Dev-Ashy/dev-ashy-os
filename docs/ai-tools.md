# Dev-Ashy OS AI Tools

Dev-Ashy OS comes with support for multiple AI tools and services.

## Ollama

### Installation

Ollama is pre-installed on Dev-Ashy OS.

### Start Ollama

```bash
ollama serve
```

### Pull a Model

```bash
# Small model (2 GB)
ollama pull llama3.2:3b

# Medium model (4.7 GB)
ollama pull qwen2.5-coder:7b

# Large model (6.6 GB)
ollama pull gemma4:e4b
```

### Run a Model

```bash
ollama run llama3.2:3b
```

### API Access

Ollama provides an OpenAI-compatible API:

```bash
curl http://127.0.0.1:11434/api/generate -d '{
  "model": "llama3.2:3b",
  "prompt": "Hello"
}'
```

## OpenCode

### Installation

```bash
npm install -g opencode-ai
```

### Start OpenCode

```bash
opencode
```

### Configuration

OpenCode uses Ollama by default on Dev-Ashy OS.

## Gemini CLI

### Installation

```bash
npm install -g @google/gemini-cli
```

### Authentication

```bash
gemini
```

Follow the prompts to authenticate with your Google account.

### Usage

```bash
gemini "Your prompt here"
```

## Hermes Agent

### Installation

Hermes Agent is pre-installed on Dev-Ashy OS.

### Start Hermes

```bash
hermes chat
```

### Configuration

Hermes uses Ollama by default:

```yaml
provider: "custom"
base_url: "http://127.0.0.1:11434/v1"
api_key: "ollama"
model:
  default: "gemma4:e4b"
```

## AI Model Recommendations

For 8 GB RAM:
- **llama3.2:3b** — Fast, lightweight
- **qwen2.5-coder:7b** — Best for code
- **gemma4:e4b** — Good balance

For 16 GB RAM:
- **llama3.1:8b** — Better quality
- **deepseek-coder:6.7b** — Code specialist
- **mistral:7b** — General purpose

For 32 GB RAM:
- **llama3.1:70b** — Best quality
- **codellama:34b** — Code specialist

## API Keys

Dev-Ashy OS does NOT include API keys. You must authenticate each service:

- **Gemini CLI** — Google account
- **OpenCode** — Anthropic API key
- **Hermes** — Uses Ollama (no key needed)

## Next Steps

- [Installation](installation.md) — Install Dev-Ashy OS
- [Security](security.md) — Security tools guide
- [Building](building.md) — Build from source
