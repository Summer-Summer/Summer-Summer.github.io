---
title: "USTC-Core: Multi-Stage Pipelined Processor Design and Microarchitecture Exploration"
excerpt: "Designed and implemented a multi-stage pipelined processor core (MIPS / RISC-V ISA) from scratch using Verilog HDL, featuring hazardous forwarding logic and comprehensive simulation verification.<br/><img src='/images/ustc_cpu/cpu_datapath.png' style='max-width:70%; height:auto;'>"
collection: portfolio
date: 2019-03-15
---

### 🚀 Project Overview
During my academic journey at the **University of Science and Technology of China (USTC)**, I served as the **Teaching Assistant (TA)** for the advanced *Computer Architecture* laboratory courses. Leading a talented team of co-TAs, I spearheaded the comprehensive redesign and construction of the entire core experimental framework from scratch, which has since served as the official open-source pedagogical baseline for hundreds of undergraduate students.

This repository documents the production-ready full-stack RTL infrastructure that we engineered for the students, charting a rigorous pedagogical milestone from single-cycle execution units to highly optimized, multi-stage pipelined processor cores running standard instruction sets (RISC-V variants).

<p align="center">
  <img src="/images/ustc_cpu/cpu_datapath.png" alt="CPU Microarchitecture Datapath" width="85%"><br>
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

### 🌌 Hardware Lineage & Ecosystem Legacy
The core Verilog framework and modular testbenches designed for this course have evolved into a vital engineering legacy within USTC. It serves not just as a grading benchmark, but as an open, highly extensible sandbox that empowers junior students to build advanced hardware-software co-designs.

Building directly upon this foundational infrastructure, subsequent undergraduate cohorts have successfully driven the platform to its limits. Notably, talented junior peers (such as [Liuly](https://liuly.moe/riscv32-ustc-codh-lab6/)) have scaled this baseline into a fully featured **RISC-V 32-bit (RV32I) ecosystem**, orchestrating cutting-edge architectural enhancements and interactive software stacks:
* **Dynamic Branch Prediction:** Integrating a hardware BHT (Branch History Table) leveraging 2-bit saturating counters directly into the instruction fetch boundary to aggressively mask control hazards.
* **Custom Memory Hierarchy:** Crafting tightly-coupled, 2-Way Set-Associative Instruction and Data Caches to effectively bypass asynchronous Block-RAM access penalties and mitigate structural memory stalls.
* **The "Greedy Snake" Bare-Metal System:** Engineering custom Memory-Mapped I/O (MMIO) peripherals to interface with on-board push buttons and a VGA display module, culminating in a full-stack deployment where an interactive "Greedy Snake" game—implemented in C and cross-compiled into bare-metal binary—runs flawlessly on the physical FPGA-synthesized pipeline.

<p align="center">
  <img src="/images/ustc_cpu/snake_vga.png" alt="Greedy Snake Game via VGA Simulation" style="width: 65%; max-width: 500px; height: auto;"><br>
  <em>Figure: Live runtime rendering of the C-driven "Greedy Snake" game executing on the custom RV32I pipelined core.</em>
</p>

---

### 🔗 Project Source
* [👉 View Complete RTL Source on GitHub](https://github.com/Summer-Summer/ComputerArchitectureLab)