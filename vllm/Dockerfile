FROM python:3.10-slim

# Atualiza pip e instala vllm na versão mais recente
RUN pip install --upgrade pip \
    && pip install --no-cache-dir --upgrade vllm huggingface_hub

# Exibe a versão instalada do vllm
RUN pip show vllm

EXPOSE 8000

CMD ["python", "-m", "vllm.entrypoints.openai.api_server", \
     "--model", "meta-llama/Llama-2-7b-chat-hf", \
     "--port", "8000", \
     "--host", "0.0.0.0", \
     "--device", "cpu"]
