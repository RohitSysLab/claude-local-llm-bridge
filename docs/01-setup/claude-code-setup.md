## Environment Configuration

Set these variables to redirect Claude Code from Anthropic's API to local Ollama:
```bash
export ANTHROPIC_AUTH_TOKEN="ollama"
export ANTHROPIC_API_KEY=""
export ANTHROPIC_BASE_URL="http://localhost:11434"
```

Add to ~/.bashrc for persistence:
```bash
echo 'export ANTHROPIC_AUTH_TOKEN="ollama"' >> ~/.bashrc
echo 'export ANTHROPIC_API_KEY=""' >> ~/.bashrc
echo 'export ANTHROPIC_BASE_URL="http://localhost:11434"' >> ~/.bashrc
source ~/.bashrc
```

## Launching Claude Code with Local Model

First, make sure Ollama is running:
```bash
ollama serve
```

Then in a new terminal, launch with your model:
```bash
claude --model qwen2.5-coder:latest
```

## Known Issue
some models such as qwen2.5-coder returns raw JSON tool calls instead of text responses.
This indicates the model may lack proper tool-calling support for Claude Code.
Solution: switch to other models which has native tool-calling support.