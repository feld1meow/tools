## Configuration for Ryzen 7 9700X + RTX 4070TI Super + 64GB RAM


### Windows
```powershell
[Environment]::SetEnvironmentVariable("OLLAMA_FLASH_ATTENTION", "1", "User")
[Environment]::SetEnvironmentVariable("OLLAMA_KV_CACHE_TYPE", "q8_0", "User")
[Environment]::SetEnvironmentVariable("OLLAMA_NUM_PARALLEL", "1", "User")
[Environment]::SetEnvironmentVariable("OLLAMA_KEEP_ALIVE", "24h", "User")
[Environment]::SetEnvironmentVariable("OLLAMA_CONTEXT_LENGTH", "65536", "User")
```


### MacOS
```bash
launchctl setenv OLLAMA_FLASH_ATTENTION 1
launchctl setenv OLLAMA_KV_CACHE_TYPE q8_0
launchctl setenv OLLAMA_NUM_PARALLEL 1
launchctl setenv OLLAMA_KEEP_ALIVE 24h
launchctl setenv OLLAMA_CONTEXT_LENGTH 65536
```


### Ollama Configuration
```bash
ollama run qwen3.8:27b-q8_0
/set parameter num_ctx 65536
/set parameter num_predict 24576
/set parameter num_thread 8
/set parameter temperature 0.6
/set parameter top_p 0.95
/set parameter top_k 20
/set parameter min_p 0.0
/save qwen3.8:27b-q8_0
/bye
```

```bash
ollama run qwen3.8:27b
/set parameter num_ctx 65536
/set parameter num_predict 16384
/set parameter num_thread 8
/set parameter temperature 0.6
/set parameter top_p 0.95
/set parameter top_k 20
/set parameter min_p 0.0
/save qwen3.8:27b
/bye
```

### opencode.json
```json
{
  "$schema": "https://opencode.ai/config.json",
  "model": "ollama/qwen3.8:27b-q8_0",
  "provider": {
    "ollama": {
      "npm": "@ai-sdk/openai-compatible",
      "name": "Ollama Local",
      "options": {
        "baseURL": "http://127.0.0.1:11434/v1",
        "timeout": 1200000
      },
      "models": {
        "qwen3.8:27b-q8_0": {
          "name": "Qwen 3.8 27B (Q8_0 — Max Quality)",
          "tool_call": true,
          "reasoning": true,
          "attachment": true,
          "temperature": true,
          "limit": {
            "context": 65536,
            "output": 24576
          },
          "options": {
            "temperature": 0.6,
            "top_p": 0.95,
            "reasoningEffort": "high"
          },
          "variants": {
            "high": {
              "options": { "reasoningEffort": "high" }
            },
            "medium": {
              "options": { "reasoningEffort": "medium" }
            },
            "low": {
              "options": { "reasoningEffort": "low" }
            }
          }
        },
        "qwen3.8:27b": {
          "name": "Qwen 3.8 27B (Q4_K_M — Fast Mode)",
          "tool_call": true,
          "reasoning": true,
          "attachment": true,
          "temperature": true,
          "limit": {
            "context": 65536,
            "output": 16384
          },
          "options": {
            "temperature": 0.6,
            "top_p": 0.95,
            "reasoningEffort": "medium"
          }
        }
      }
    }
  },
  "mcp": {
    "chrome-devtools": {
      "type": "local",
      "command": [
        "cmd",
        "/c",
        "npx",
        "-y",
        "chrome-devtools-mcp@latest",
        "--slim"
      ],
      "enabled": true
    }
  }
}
```
