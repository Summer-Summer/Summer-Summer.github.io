---
title: "USTC-Core: Multi-Stage Pipelined Processor Design and Microarchitecture Exploration"
excerpt: "Designed and implemented a multi-stage pipelined processor core (MIPS / RISC-V ISA) from scratch using Verilog HDL, featuring hazardous forwarding logic and comprehensive simulation verification.<br/><img src='/images/ustc_cpu/cpu_datapath.jpg' style='max-width:100%; height:auto;'>"
collection: portfolio
---

### 🚀 Project Overview
During my academic journey at the **University of Science and Technology of China (USTC)**, I built a series of processor microarchitectures from scratch to master the core principles of computer organization and hardware description languages (HDL). 

This repository documents my full-stack RTL development, transitioning from basic single-cycle execution units to a highly optimized, multi-stage pipelined processor core capable of executing standard instruction sets (MIPS / RISC-V variants).

<p align="center">
  <img src="/images/ustc_cpu/cpu_datapath.jpg" alt="CPU Microarchitecture Datapath" width="80%"><br>
  <em>Figure: The customized microarchitecture datapath highlighting the decoupled control unit, hazard detection logic, and pipelined register stages.</em>
</p>

---

### 🛠️ Microarchitecture & Implementation Details

* **Decoupled 5-Stage Pipeline Construction:** 
  Structured the hardware logic into classical pipeline stages: *Instruction Fetch (IF), Instruction Decode (ID), Execute (EX), Memory Access (MEM), and Write Back (WB)*.
* **Full Hazard Detection & Forwarding Logic:** 
  Developed a robust hazard management subsystem entirely in Verilog. Implemented data forwarding (bypassing) paths to resolve RAW (Read-After-Write) dependencies without introducing artificial bubbles, and engineered predictive stalling mechanisms for load-use hazards and structural conflicts.
* **Control Unit Co-Design:** 
  Designed a centralized control matrix that decodes opcodes and functional bits in the ID stage, dispatching precise synchronized control flags across execution boundaries.
* **Testbench Validation & Simulation:** 
  Authored extensive testbenches to trace register files, PC boundaries, and memory interfaces under stress-test assembly workloads, ensuring 100% functional alignment with mathematical ISA specifications.

---

### 🌌 Academic Lineage & Future Extensions
The foundational infrastructure established in this repository has served as a benchmark for subsequent academic microarchitecture exploration within USTC. 

Notably, junior researchers in our lab (such as [Liuly](https://liuly.moe/riscv32-ustc-codh-lab6/)) have successfully extended this core architecture into a full-featured **RISC-V 32-bit (RV32I) processor platform**, incorporating advanced hardware semantics including:
* **Dynamic Branch Prediction:** Integrating BHT (Branch History Table) and BTB (Branch Target Buffer) topologies into the fetch boundary to mask control hazards.
* **Memory Hierarchy Upgrades:** Designing customized, tightly-coupled 2-Way Set-Associative Instruction/Data Caches to bypass raw block-RAM access latencies.

---

### 🔗 Project Source
* [👉 View Complete RTL Source on GitHub](https://github.com/Summer-Summer/ComputerArchitectureLab)