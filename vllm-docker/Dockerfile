FROM python:3.10-slim

# System deps
RUN apt-get update && apt-get install -y \
    git \
    wget \
    gcc \
    g++ \
    && rm -rf /var/lib/apt/lists/*

# Upgrade pip
RUN pip install --upgrade pip

# Install vLLM (CPU version)
RUN pip install vllm

# Expose vLLM port
EXPOSE 8000

# Start vLLM server with LLaVA
CMD ["vllm", "serve", "llava-hf/llava-1.5-7b-hf"]
