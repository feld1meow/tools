## Configuration for Ryzen 7 9700X + RTX 4070TI Super + 64GB RAM


### Windows
```powershell
[Environment]::SetEnvironmentVariable("OLLAMA_FLASH_ATTENTION", "1", "User")
[Environment]::SetEnvironmentVariable("OLLAMA_KV_CACHE_TYPE", "q8_0", "User")
[Environment]::SetEnvironmentVariable("OLLAMA_NUM_PARALLEL", "1", "User")
[Environment]::SetEnvironmentVariable("OLLAMA_CONTEXT_LENGTH", "65536", "User")
[Environment]::SetEnvironmentVariable("OLLAMA_KEEP_ALIVE", "6h", "User")
```


### MacOS
```bash
launchctl setenv OLLAMA_FLASH_ATTENTION 1
launchctl setenv OLLAMA_KV_CACHE_TYPE q8_0
launchctl setenv OLLAMA_NUM_PARALLEL 1
launchctl setenv OLLAMA_CONTEXT_LENGTH 65536
launchctl setenv OLLAMA_KEEP_ALIVE 6h
```


### Ollama Configuration
```bash
ollama run qwen3.8:27b
```
