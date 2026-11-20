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


### Ollama Configuration (Don't need, because `ollama pull qwen3.8:27b` takes it)
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
