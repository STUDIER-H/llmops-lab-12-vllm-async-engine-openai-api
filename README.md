# 🧪 LAB 12: High-Throughput LLM Serving com vLLM, PagedAttention e OpenAI SDK

## 🎯 Objetivo do Lab
Implementar o motor de inferência **vLLM** como servidor primário de alta vazão, eliminando frameworks de chatbot e mantendo controle nativo da API.

---

## 📋 Pré-requisitos
- Ter lido o paper do vLLM (*PagedAttention* - Kwon et al.) e concluído a especialização *LLMOps* (Duke Univ).
- vLLM 0.4+, GPU NVIDIA com CUDA 12+, Python OpenAI SDK.

---

## 🛠️ O que você deve construir neste Lab:

### Etapa 1: Setup do Servidor vLLM
1. Suba o vLLM servidor via CLI ou script Python com suporte a Continuous Batching e PagedAttention:
   ```bash
   python -m vllm.entrypoints.openai.api_server --model meta-llama/Meta-Llama-3-8B-Instruct --gpu-memory-utilization 0.90
   ```

### Etapa 2: Cliente Native OpenAI SDK (Python Async)
1. Escreva um script em Python `client_async.py` que se conecte ao vLLM local via `AsyncOpenAI` client e consuma o endpoint `/v1/chat/completions` com streaming ativo.

---

## ✅ Critérios de Aceitação & Entrega
- [ ] Servidor vLLM rodando e respondendo na porta `8000`.
- [ ] Streaming de tokens token-a-token funcionando com a SDK da OpenAI em CPython.
