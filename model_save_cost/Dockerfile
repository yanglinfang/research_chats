# Dockerfile

# Use NVIDIA CUDA base image with PyTorch support
FROM nvidia/cuda:11.8.0-cudnn8-runtime-ubuntu22.04

# Set environment variables for Python and CUDA
ENV DEBIAN_FRONTEND=noninteractive
ENV PYTHONDONTWRITEBYTECODE=1
ENV PYTHONUNBUFFERED=1
ENV PATH="/opt/conda/bin:$PATH"

# --- APT 缓存加速，装 Python 3.10 ---
RUN apt-get update && apt-get install -y --no-install-recommends \
    python3.10 python3-pip python3-dev \
    wget git curl \
    libgl1-mesa-glx libglib2.0-0 && \
    rm -rf /var/lib/apt/lists/*

# --- 一次性装 cu118 轮子 + vLLM ---
RUN pip install --no-cache-dir \
        torch==2.1.0+cu118 torchvision==0.16.0+cu118 \
        --extra-index-url https://download.pytorch.org/whl/cu118 && \
    pip install --no-cache-dir vllm[cu118]

# Set working directory
WORKDIR /research_chats

# Clone repository
COPY . /research_chats

# Install dependencies
RUN pip install --no-cache-dir -r requirements.txt
RUN pip install jupyter ipython


# ---------- Entrypoint ----------
ENTRYPOINT ["python", "-m", "vllm.entrypoints.openai.api_server"]

# 多行 CMD 写完别漏右括号
CMD ["--model", "deepseek-10b-awq", "--tokenizer", "deepseek-10b-awq", "--port", "8000", "--concurrency", "16", "--max-batch-tokens", "8192", "--log-dir", "vllm_logs"]


# Expose default ports for training logs (if needed)
EXPOSE 8192
