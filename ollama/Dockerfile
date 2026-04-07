FROM alpine/ollama:latest

# Bundel model qwen2.5:0.5b (~350MB) untuk PoC
RUN ollama serve > /dev/null 2>&1 & \
    sleep 5 && \
    ollama pull qwen2.5:0.5b && \
    kill $(pgrep ollama) || true
