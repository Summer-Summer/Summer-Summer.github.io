---
title: "LAP_SoC: A Domain-Specific Heterogeneous System-on-Chip with Lightweight Automata Processor"
excerpt: "Designed and implemented a domain-specific core optimized for ADFA algorithms and integrated it into an ARM-based heterogeneous SoC via high-throughput AXI channels, evaluated on a physical Zedboard FPGA platform.<br/><img src='/images/LAP_SoC/LAP_SoC.jpg' style='max-width:100%; height:auto;'>"
collection: portfolio
---

### 🚀 Project Overview
Multi-pattern matching is a fundamental but computationally expensive operation widely used in deep packet inspection (DPI), log parsing, and bioinformatics[cite: 1]. Traditional general-purpose CPUs and GPUs suffer from severe branch mispredictions and intensive random memory accesses when simulating finite automata (FAs). 

To tackle this bottleneck, I designed and implemented **LAP (Lightweight Automata Processor)**, a domain-specific core optimized for **ADFA (Amortized time/bandwidth overhead DFA)** models. I further integrated this dedicated accelerator into an ARM-based heterogeneous Computing System-on-Chip (**LAP_SoC**) implemented on the Xilinx ZYNQ platform.

<p align="center">
  <img src="/images/LAP_SoC/LAP_SoC.jpg" alt="LAP_SoC Architecture" width="90%">
</p>

---

### 🛠️ Key Technical Contributions

#### 1. Hardware-Software Co-Design & Parallel Rollback Architecture
To compress transition tables without ruining streaming performance, the framework compiles standard regular expressions into layered ADFA structures. By introducing a split storage topology, the core decouples regular labeled edges from fallback pipelines, executing state optimization with custom hardware primitives.

<p align="center">
  <img src="/images/LAP_SoC/ADFA.jpg" alt="ADFA Layered Optimization" width="85%"><br>
  <em>Figure: Layered compilation mechanism mapping standard patterns into compressed ADFA representations with tight bound limits.</em>
</p>

#### 2. Fine-Grained Multi-Threading Pipeline
Designed a highly balanced 4-stage hardware pipeline (*State Fetch, State Decoding, Instruction Fetch, Instruction Decoding*). To resolve data and control hazards without introducing complex bypass logic or pipeline bubbles, I implemented **Fine-Grained Multi-Threading (FGMT)**, allowing 4 independent hardware contexts to share the core seamlessly with zero pipeline stalls.

#### 3. Standard AXI Industrial Integration & Driver Stack
Wrapped the standalone LAP core into a production-ready Xilinx IP block featuring customized standard buses. Configured and booted an embedded Linux OS environment (built via PetaLinux) on the host dual-core ARM Cortex-A9 processing system. Authored the user-space low-level Linux drivers in C via `mmap` physical address binding, abstracting complex DMA descriptors into clean API primitives for seamless host-device scheduling.

<p align="center">
  <img src="/images/LAP_SoC/outputs.jpg" alt="Linux Terminal Evaluation" width="85%"><br>
  <em>Figure: Live execution of user-space driver scheduling stream DMA copies and retrieving hardware match payloads.</em>
</p>

---

### 📊 Hard Evaluation Results

* **Silicon Efficiency:** Fully synthesized and mapped onto the Xilinx fabric, achieving a layout clock of **263 MHz** for the standalone core. The architecture provides up to **8x higher storage density** compared to IBM RegX or Micron AP accelerators.
* **Heterogeneous Speedup Dominance:** In physical experiments, driving the hardware logic over unified streaming DMA buses provides massive latency drops. Compared to industrial-grade standard regex software engines (e.g., GNU `grep`), LAP provides **over 40x speedup** against bare ARM processors and outperforms x86 server-grade Intel chips.

<p align="center">
  <img src="/images/LAP_SoC/results.jpg" alt="Hardware Acceleration Speedup" width="85%"><br>
  <em>Figure: Speedup statistics across multiple dataset scales, illustrating constant performance scaling once OS overhead limits fade out.</em>
</p>

---

### 🌌 Physical FPGA System Implementation
The entire heterogeneous compute platform is fully realized and validated on a standard Avnet Zedboard evaluation platform. The ARM processing subsystem hooks directly into the PL logic via memory-mapped interconnects to drive automated packet capture and deep evaluation pipelines.

<p align="center">
  <img src="/images/LAP_SoC/zedboard.jpg" alt="Physical Zedboard Setup" width="70%"><br>
  <em>Figure: Physical experimental setup of LAP_SoC running embedded Linux environment and real-time streaming validation.</em>
</p>

---

### 📝 Related Publication
This full-stack project led to my master's thesis at **USTC** and a peer-reviewed publication:
* **Haojun Xia**, Lei Gong, Chao Wang, et al. *"LAP: A Lightweight Automata Processor for Pattern Matching Tasks."* In **Proceedings of the 2021 Design, Automation & Test in Europe (DATE)**. *(CCF-B)*