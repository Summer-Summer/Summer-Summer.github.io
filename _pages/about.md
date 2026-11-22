---
permalink: /
title: "About me"
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---

I am a Research Software Engineer at **Google Research, Australia**, based in Sydney. I am currently focusing on ML efficiency, especially LLM inference optimizations. I obtained my Ph.D. from the School of Computer Science, Faculty of Engineering at **The University of Sydney (USYD)**. Prior to that, I received my Master's and Bachelor's degree from the **University of Science and Technology of China (USTC)**.

My research lies at the intersection of **Computer Systems, Machine Learning (MLSys), and Hardware Architecture**. I am passionate about breaking the memory wall and communication bottlenecks in generative AI. Through full-stack innovations across the algorithm, runtime, and hardware boundaries, my work primarily focuses on algorithm-system-architecture co-design for Large Language Models (LLMs), including:

* **High-Performance Kernel Optimization:** Designing efficient system acceleration and custom GPU/TPU kernels for Generative AI, including the kernel design of efficient MLP, Attention, and MoE layers.
* **Extreme Model Compression:** Developing low-bit weight/KV cache quantization (e.g., FP6, sub-byte formats) and unstructured sparsity exploitation to maximize inference throughput.
* **Hardware Acceleration & Custom Microarchitecture:** Leveraging domain-specific architectures (DSA) and custom hardware accelerators (e.g., FPGA/SoC prototypes) to co-design and execute hardware-native execution primitives for modern ML and pattern-matching workloads.

With systematic optimizations spanning from gate-level hardware logic up to distributed software systems, my ultimate goal is to build memory-efficient, high-throughput, and scalable infrastructure to democratize next-generation AI foundation models.

News
======
* **[Jul 2026]** My PhD was conferred by The University of Sydney. My thesis is [open access](https://hdl.handle.net/2123/35623).
* **[May 2026]** Our paper Kitty was selected for an **oral presentation** at [MLSys 2026](https://mlsys.org/virtual/2026/oral/3746).
* **[Nov 2025]** I joined **Google Research, Australia** as a Research Software Engineer, working on LLM serving efficiency on TPUs.
* **[Aug 2024]** Oral presentation of Flash-LLM at VLDB 2024, Guangzhou.
* **[Jul 2024]** Oral presentation of Quant-LLM (FP6-LLM) at [USENIX ATC 2024](https://www.usenix.org/conference/atc24/presentation/xia), Santa Clara.
* **[2024]** FP6-LLM was integrated into [Microsoft DeepSpeed](https://github.com/deepspeedai/DeepSpeed/blob/master/blogs/deepspeed-fp6/03-05-2024/README.md) and [PyTorch/AO](https://docs.pytorch.org/ao/0.13/generated/torchao.quantization.FPXWeightOnlyConfig.html).
