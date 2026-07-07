---
layout: archive
title: "CV"
permalink: /cv/
author_profile: true
redirect_from:
  - /resume
---

<div class="wordwrap">This is my <a href="/files/cv_haojun_xia.pdf" target="_blank">downloadable CV</a>.</div>

{% include base_path %}

Education
======
* **Ph.D. in Computer Science**, The University of Sydney (USYD), 2022 – 2026
  * *Thesis:* Compression-Driven Memory-Efficient and High-Throughput GPU Systems for LLM Inference.
* **M.S. in Computer Architecture**, University of Science and Technology of China (USTC), 2018 – 2021
  * *Thesis:* The design and implementation of a lightweight Automata Processor.
  * *Honors:* First Class Scholarship
* **B.S. in Computer Science and Technology**, University of Science and Technology of China (USTC), 2014 – 2018
  * *Thesis:* FPGA Based CNN Accelerator Design.
  * *Honors:* Talent Program

Work Experience
======
* **Research Software Engineer** | Google Research
  * *Nov 2025 – Present* (Full-time, On-site)
  * Duties: Optimizing production-level TPU-based LLM inference systems.
* **Research Consultant** | Together AI
  * *Mar 2024 – Sept 2024* (Part-time, Remote)
  * Duties: Optimizing the LLM inference system, identifying and mitigating performance issues in LoRA inference, and developing the FP8 MHA Decoding GPU kernel using OpenAI Triton.
* **Research Intern** | Alibaba Cloud
  * *Feb 2022 – Aug 2023* (Remote, Un-paid)
  * Duties: Extension of the former research project on large-scale ML model acceleration frameworks.
* **Research Intern** | Alibaba Cloud
  * *Aug 2021 – Jan 2022* (On-site)
  * Duties: Part of the Alibaba Innovative Research (AIR) program. Investigated SOTA system support for LLMs, and R&D a novel large-scale ML model acceleration framework.

Skills
======
* **Research Interests:** Performance Optimization, Machine Learning System, Runtime Systems, Computer Architecture, Domain Specific Architectures, GPU/TPU Kernel Design
* **Programming Languages:** JAX, Pallas (TPU), C/C++, Python, CUDA (GPU), Triton (GPU), Verilog HDL (FPGA)
* **Software & Frameworks:** Machine Learning Frameworks (e.g., PyTorch, Huggingface Transformers, Faster Transformer), Embedded System Design and Implementation (e.g., Xilinx FPGA + ARM CPUs)

Selected Publications
======
<!-- Automatically load all items from collections -->
<ul>{% for post in site.publications reversed %}
  {% if post.category != 'thesis' %}
    {% include archive-single-cv.html %}
  {% endif %}
{% endfor %}</ul>
  
Talks
======
<ul>{% for post in site.talks reversed %}
  {% include archive-single-talk-cv.html  %}
{% endfor %}</ul>
  
Teaching
======
<ul>{% for post in site.teaching reversed %}
  {% include archive-single-cv.html %}
{% endfor %}</ul>
  
Honors and Achievements
======
* **2022 – 2026:** Faculty of Engineering Research Scholarship, PhD study, USYD
* **2021:** Outstanding Graduates (Top 15%), Master's study, USTC
* **2020:** Suzhou Park Scholarship, Master's study, USTC
* **2018 – 2021:** First Class Academic Scholarship, Master's study, USTC
* **2018:** Yang Yuanqing Education Fund - Top Research Scholarship, Bachelor's study, USTC
* **2018:** Outstanding Graduates (Top 15%), Bachelor's study, USTC
* **2014 – 2018:** Talent program in computer science and technology, USTC