---
title: "PhD Thesis: Compression-Driven Memory-Efficient and High-Throughput GPU Systems for LLM Inference"
collection: publications
category: thesis
permalink: /publication/2026-06-21-phd-thesis
excerpt: 'My doctoral dissertation focuses on alleviating the memory wall in Large Language Model (LLM) inference through algorithm-system co-design, including low-bit weight/KV quantization and unstructured weight sparsity acceleration.'
date: 2026-06-21
venue: 'The University of Sydney (USYD)'
---

This doctoral dissertation addresses the severe memory and bandwidth bottlenecks challenges in serving Large Language Models (LLMs) on modern GPU architectures. By driving systematic innovations across the algorithm and runtime system boundaries, this work proposes compression-driven methodologies to achieve high-throughput and memory-efficient LLM inference. 

The dissertation was successfully defended on 4th March 2026 and officially submitted USYD library in June 2026.

**Key Contributions:**
* **Low-Bit Weight/KV Cache Quantization:** Co-designed highly efficient GPU compilation and custom Tensor Core layout support for diverse sub-byte formats (e.g., FP6, 2-bit quantization with dynamic channel-wise boosting), substantially lowering the GPU memory wall.
* **Unstructured Sparsity Exploitation:** Created runtime optimization spaces and high-performance kernel execution paradigms to exploit model weight sparsity, significantly improving generation throughput and saving HBM bandwidth for large generative models.
