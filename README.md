# Christopher Zarraga

**C++ Systems Engineer · AI Infrastructure & HPC**

Computer Science @ UC Santa Cruz (Applied Mathematics minor) · Sabatte Family Full-Ride Scholar · Undergraduate AI Researcher

I build systems from scratch in C++ — concurrent servers, a hand-written neural-network inference engine, a custom vector database, and a limit order book — and I'm drawn to the layer where performance actually matters.

📍 Santa Cruz, CA · Open to SWE internships in AI/ML infrastructure, systems & performance engineering — **Summer/Fall 2027**

---

## 🔬 Research

**AIEA Lab — UC Santa Cruz** · Undergraduate AI Researcher *(Prof. Leilani Gilpin)*
*Robustifying Autonomous Vehicles* — deploying the CARLA driving simulator headless on the Nautilus Kubernetes GPU cluster (PVC-backed storage, GPU-scheduled jobs, custom YAML specs) as the foundation for benchmarking reinforcement-learning algorithms for autonomous-driving safety. Builds on prior neuron-activation analysis work in the lab (Python / PyTorch).

**Tech4Good Lab — UC Santa Cruz** · Undergraduate Full-Stack Researcher
Generative-AI / ML web applications for social impact. Building standalone Angular components (Signals, OnPush change detection, Material / CDK) in the lab's TypeScript codebase.

---

## 🔧 Projects

### Multi-Threaded HTTP/1.1 Server · `C · POSIX threads`
Sustained ~8,400 req/s at ~13 ms p99 under 64 concurrent connections — 2.2× a single-threaded baseline, measured with wrk (connection-per-request, 6-core aarch64 VM) — by engineering a C HTTP/1.1 server around a fixed-size thread pool, bounded producer-consumer queue, and hand-rolled per-URI reader–writer locks.

### VeriFi — Vector Store for a RAG Pipeline · `C++` · *team project · in progress*
Founded the project and lead a 5-person team; architected and own the core engine. An in-memory vector store with exact cosine-similarity k-NN retrieval that powers a Retrieval-Augmented Generation pipeline, grounding LLM answers in retrieved source documents. Defined the Day-1 interface contracts (chunk format, search API, response schema) the team builds against.

### Limit Order Book Matching Engine · `C++`
A price-time-priority limit order book matching engine, extended with two original order types I designed for tighter execution control:
- **Banded Execution Order** — a tolerance band around the limit price; the order rests rather than filling when the market gaps beyond an acceptable floor/ceiling, protecting against flash-crash slippage.
- **VWAP Pre-Execution Gate** — computes the volume-weighted average across available liquidity *before* matching, executing only if the blended fill clears the limit price — so a large order in a thin book can't silently average above the intended ceiling.

Engine and both order types implemented; validation suite in progress.

### Neural Network Inference Engine · `C++ · PyTorch` · *in progress*
A from-scratch MNIST inference engine, no ML libraries (784→128→64→10). PyTorch training + binary weight-export pipeline **complete**; the C++ CPU forward pass — matrix multiply, ReLU, argmax — is in development. SIMD + multithreading and a CUDA port are planned.

### NVPilot — GPU / System Performance Agent · `TypeScript · Node · NVML`
Autonomous performance agent (perceive–plan–act–reflect loop) that reads live GPU telemetry via NVML, classifies hardware tier, and applies surgical, fully reversible game/system/power optimizations in real time. Built at the NVIDIA × ASUS NemoClaw Hackathon.
- Full system perception in **~550 ms**; rule-based plan generation **<1 ms** (measured on RTX 3060 Laptop).
- **Journal-based reversibility** — every mutation records a mechanical inverse; verified byte-identical config restoration with **~3 s** full rollback.
- Scans **400+ processes** per cycle, identifying ~2 GB of reclaimable background memory.
- Local LLM planner (Ollama / Nemotron) with schema validation and a deterministic rule-engine fallback — remains functional with the LLM offline.
- **~2,800 lines** of strict-mode TypeScript across 4 subsystems (drivers, planners, core engine, tool interface). C++ / NVML rewrite planned.

🔗 github.com/Kurisuo/NVPilot

### Redis Clone — In-Memory Key-Value Store · `C++` · *in progress*
Building a Redis-style in-memory key-value store in C++ — TCP server, core commands, and RESP protocol parsing — as a from-scratch systems exercise.

*Exploring next: a lock-free concurrent queue (C++ atomics).*

---

## 🛠 Tech

**Systems:** C · C++17/20 · POSIX threads · Linux · CMake · gdb · Valgrind · Git
**GPU & Infra:** NVML · GPU telemetry · Kubernetes (Nautilus) · Docker · Bash · CUDA *(learning)*
**ML & Web:** Python · PyTorch · NumPy · Pandas · TypeScript · Angular

---

## 📚 Selected Coursework

Computer Systems Design · Data Structures & Algorithms · Computer Systems & C · Machine Learning Basics · AI for Health · Linear Algebra · Discrete Mathematics
*In progress:* Software Engineering (Agile / Scrum)

---

## 📫 Contact

📧 christopherzarraga31@gmail.com  ·  💼 [LinkedIn](https://linkedin.com/in/christopher-zarraga)

*Outside of code: chess (2000 Elo), and recently took up swimming.*
