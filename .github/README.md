# 🐳 Vibe-Trading - Docker Deployment Fork

> [!NOTE]
> This is a deployment-focused fork of the official [HKUDS/Vibe-Trading](https://github.com/HKUDS/Vibe-Trading) repository.
> It provides a pre-built Docker image via GHCR, allowing you to run the bot instantly in Docker / Portainer without needing a local compiler or a full git clone.

---

## 🚀 Quick Start (Docker Compose / Portainer)

The image is entirely public and can be pulled without any GitHub login or credentials:

```yaml
services:
  vibe-trading:
    image: ghcr.io/kailuettmann/vibe-trading:latest
    container_name: vibe-trading
    ports:
      - 8899:8899
    environment:
      - VIBE_TRADING_TRUST_DOCKER_LOOPBACK=1
      - LANGCHAIN_PROVIDER=openrouter
      - LANGCHAIN_MODEL_NAME=deepseek/deepseek-v4-pro
      - OPENROUTER_API_KEY=your_api_key_here
      - LANGCHAIN_TEMPERATURE=0.0
    volumes:
      # Adjust these host paths to your local server / NAS directory structure if needed
      - /volume1/docker/vibe-trading/runs:/app/agent/runs:rw
      - /volume1/docker/vibe-trading/sessions:/app/agent/sessions:rw
    restart: unless-stopped
```
## 🔄 Updates & Maintenance

Best Effort: This is a personal project. I provide this pre-built image as-is and will update it occasionally whenever new official releases come out.

## ⚖️ Disclaimer & Support

Bot Logic: All credits and copyrights for the trading logic belong to the original creators of the main project. For bugs regarding strategies or LLM integration, please open an issue in the official upstream repository.

Docker Image: If the Docker image itself fails to boot or is missing specific Linux libraries, feel free to open an issue here in this fork.
