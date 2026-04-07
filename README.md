# Docker Builds

Docker images untuk layanan BintangTimur.ID.

## Repository Structure
```
docker-builds/
├── README.md          # Dokumentasi ini
├── ollama/            # Ollama server image (bundled model)
│   ├── Dockerfile
│   └── Makefile
└── python/            # Python base image (FastAPI dependencies)
    ├── Dockerfile
    ├── Makefile
    └── requirements.txt
```

## Services

### 1. Python (Base Image)
- **Lokasi**: `python/`
- **Image**: `bintangtimurid/python:latest`
- **Base**: `python:3.11-slim`
- **Dependencies**: FastAPI, Uvicorn, Pydantic, httpx
- **Build**: `cd python && make all`

### 2. Ollama (LLM Server)
- **Lokasi**: `ollama/`
- **Image**: `bintangtimurid/ollama:latest`
- **Base**: `alpine/ollama:latest`
- **Bundled Model**: `qwen2.5:0.5b` (~350MB, untuk PoC)
- **CPU-only**: Ya (tanpa GPU support)
- **Build**: `cd ollama && make all`

## Build Commands

Jalankan dari folder masing-masing image:

```bash
# Build, push semua (clean + pull base + build + push)
cd python && make all
cd ollama && make all

# Atau individual step
cd ollama && make build
cd ollama && make push
```
