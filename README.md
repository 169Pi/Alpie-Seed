<div align="center">

# Alpie Seed

### A 9B Multimodal Reasoning Model by 169Pi AI

**Reason. Code. See. Understand.**

[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](LICENSE)
[![Parameters](https://img.shields.io/badge/Parameters-~9B-green.svg)]()
[![Context](https://img.shields.io/badge/Context-256K-orange.svg)]()
[![Hugging Face](https://img.shields.io/badge/🤗%20Hugging%20Face-169Pi-yellow.svg)](https://huggingface.co/169Pi/Alpie_seed)
[![Ollama](https://img.shields.io/badge/Ollama-169pi-black.svg)](https://ollama.com/169pi)

</div>

---

Alpie Seed is a 9-billion-parameter multimodal reasoning model developed by **169Pi AI**. Designed for advanced reasoning, mathematics, coding and visual understanding, it brings together language intelligence and multimodal capabilities in an efficient model built for local and cloud deployment.

Alpie Seed supports **text, image and video** inputs, with a **256K native context window**, multilingual capabilities and multiple quantized variants.

Our goal is to make capable AI more accessible, efficient and independent of constant cloud connectivity.

## Table of Contents

- [Overview](#overview)
- [Key Capabilities](#key-capabilities)
- [Benchmark Performance](#benchmark-performance)
- [Model Downloads](#model-downloads)
- [Run with Ollama](#run-with-ollama)
- [Run with Hugging Face](#run-with-hugging-face)
- [Architecture and Development](#architecture-and-development)
- [Intended Use](#intended-use)
- [License](#license)
- [About 169Pi AI](#about-169pi-ai)
- [Coming Soon: API and SDK](#-coming-soon-api-and-sdk)

## Overview

| Property | Details |
|---|---|
| **Model** | Alpie Seed |
| **Developer** | 169Pi AI |
| **Parameters** | ~9 Billion |
| **Architecture** | Dense Vision-Language Causal LM |
| **Base Architecture** | Qwen3.5-9B |
| **Context Window** | 256K tokens |
| **Extended Context** | Up to ~1M tokens with YaRN |
| **Input Modalities** | Text, Image, Video |
| **Reasoning** | Supported |
| **Quantization** | 2-bit, 3-bit, 4-bit |
| **Model Format** | Safetensors, GGUF |
| **License** | Apache 2.0 |

## Key Capabilities

### 1. Advanced Reasoning

Alpie Seed is designed to handle complex reasoning tasks across multiple domains, including:

- Mathematics and quantitative problem-solving
- Science and technical reasoning
- Logical and analytical reasoning
- General knowledge and instruction following
- Multistep problem-solving

### 2. Coding and Software Engineering

- Code generation and completion
- Debugging and error analysis
- Code explanation and refactoring
- Algorithm design and problem-solving
- Understanding existing code

### 3. Multimodal Understanding

Alpie Seed goes beyond text-only interaction.

- **Text:** Understand instructions, analyse information, reason and generate responses.
- **Images:** Interpret screenshots, diagrams, documents and visual content.
- **Video:** Understand video content through visual frame sequences and reason about events and changes across frames.

### 4. Long-Context Processing

Alpie Seed supports a native context window of **256K tokens**, with extended context configurations reaching approximately **1 million tokens** using YaRN.

This enables longer conversations, larger document inputs and more extensive contextual reasoning, subject to runtime, memory and configuration constraints.

### 5. Multilingual Intelligence

Alpie Seed is designed to support multilingual reasoning and communication, including dedicated evaluation across Indic languages.

## Benchmark Performance

Alpie Seed has been evaluated across reasoning, mathematics, coding and multimodal benchmarks.

### Reasoning and Knowledge

| Benchmark | Score |
|---|---|
| MMLU | 87.30% |
| MMLU-Pro | 82.54% |
| GPQA Diamond | 84.32% |
| HLE | 13.24% |
| TruthfulQA MC1 | 84.20% |
| TruthfulQA MC2 | 93.56% |

### Mathematics

| Benchmark | Score |
|---|---|
| AIME 2026 | 83.33% |
| GSM8K | 98.00% |
| Math-500 | 91.00% |
| PolyMath | 57.10% |

### Coding

| Benchmark | Score |
|---|---|
| HumanEval | 91.46% |
| HumanEval+ | 88.30% |
| MBPP | 84.30% |
| LiveCodeBench v6 | 72.99% |
| CRUXEval | 85.90% |
| SWE-Bench Verified | 61.20% |

### Multimodal

| Benchmark | Score |
|---|---|
| MMMU-Pro | 68.70% |
| MathVision | 76.76% |
| DocVQA (Accuracy@0.5) | 81.23% |
| TextVQA | 78.67% |
| OCRBench | 90.30% |
| ChartQA | 72.56% |
| HallusionBench | 79.88% |
| MMStar | 78.87% |
| RealWorldQA | 80.39% |

### Indic Language Evaluation

| Evaluation | Score |
|---|---|
| Indic MMLU | 73.67% |
| MILU | 73.01% |

> **Note:** Benchmark scores are reported from our evaluations. Results can vary depending on evaluation methodology, prompting, model format, precision and runtime configuration. Scores should not be assumed to apply identically to every quantized variant.

## Model Downloads

Alpie Seed is available in multiple formats to support different deployment requirements.

| Repository | Description |
|---|---|
| [Alpie Seed](https://huggingface.co/169Pi/Alpie_seed) | Primary model repository |
| Alpie Seed GGUF | Quantized GGUF variants |
| [Ollama](https://ollama.com/169pi) | Run Alpie Seed locally with Ollama |

### Quantized Variants

Alpie Seed is available in **2-bit, 3-bit and 4-bit** quantized versions. These variants provide flexibility across different hardware configurations, balancing model size, memory requirements and inference quality.

## Run with Ollama

The easiest way to get started with Alpie Seed is through [Ollama](https://ollama.com/169pi).

```bash
# Default variant
ollama run 169pi/alpie-seed

# 2-bit variant
ollama run 169pi/alpie-seed:q2

# 3-bit variant
ollama run 169pi/alpie-seed:q3

# Vision variant
ollama run 169pi/alpie-seed:vision
```

> For multimodal workflows, use a compatible vision-enabled variant and runtime.

## Run with Hugging Face

The primary model weights and configuration are available through Hugging Face: [`169Pi/Alpie_seed`](https://huggingface.co/169Pi/Alpie_seed)

```bash
pip install transformers torch accelerate
```

Load the model and tokenizer using the appropriate model configuration and chat template from the repository.

For multimodal inference, use the model's supported image and video processing pipeline. Refer to the repository's model configuration and processor documentation for implementation details.

## Architecture and Development

Alpie Seed is built on the **Qwen3.5-9B** architecture and further developed by 169Pi AI through post-training.

The released model retains the underlying architecture, with post-training adapters merged into the base model for distribution.

The project focuses on:

- Efficient reasoning at the 9B parameter scale
- Multimodal understanding across text, images and video
- Improved performance across mathematical and coding tasks
- Multilingual and Indic-language capabilities
- Quantized deployment for local inference

## Intended Use

Alpie Seed can be used for:

- AI assistants and conversational applications
- Coding and developer tools
- Mathematical and scientific reasoning
- Document and visual analysis
- Multimodal applications
- Local AI deployment and experimentation
- Research and model development

> **Disclaimer:** The model is not intended to replace expert judgement in high-stakes domains. Outputs should be independently verified where accuracy and safety are critical.

## License

Alpie Seed is released under the **Apache License 2.0**. See the [LICENSE](LICENSE) file for the complete terms.

## About 169Pi AI

169Pi AI is an AI infrastructure company building models, agent frameworks and AI-powered products.

We are working towards making advanced AI more efficient, accessible and useful across real-world applications. Alpie Seed is part of that effort.

- 🌐 Website: [https://169pi.ai](https://169pi.ai)
- 🤗 Hugging Face: [https://huggingface.co/169Pi](https://huggingface.co/169Pi)
- 🦙 Ollama: [https://ollama.com/169pi](https://ollama.com/169pi)

---

## 🚀 Coming Soon: API and SDK

> [!IMPORTANT]
> ### **Alpie Seed API and SDK are coming soon!**
> We are working on a hosted **API** and an official **SDK** so you can integrate Alpie Seed into your applications even more easily. Stay tuned, and follow [169Pi on Hugging Face](https://huggingface.co/169Pi) and [169pi.ai](https://169pi.ai) for updates.

---

<div align="center">

**Alpie Seed. Intelligence beyond the cloud.**

Built by 169Pi AI.

</div>
