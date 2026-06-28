# Christopher Zarraga

**C++ Systems Engineer · AI Infrastructure & HPC**

Computer Science @ UC Santa Cruz (Applied Mathematics minor) · Sabatte Family Full-Ride Scholar · Undergraduate AI Researcher

I build systems from scratch in C++ — concurrent servers, a hand-written neural-network inference engine, and a custom vector database — and I'm drawn to the layer where performance actually matters.

📍 Santa Cruz, CA · Open to SWE internships in AI/ML infrastructure, systems & performance engineering — **Summer/Fall 2027**

---

## 🔬 Research

**AIEA Lab — UC Santa Cruz** · Undergraduate AI Researcher *(Prof. Leilani Gilpin)*
*Neuron Explanations for Computer Vision* — associating logical rules to individual neurons in deep vision networks to explain which visual concepts each neuron recognizes and in what context. Search + clustering algorithms over neuron activations, in Python / PyTorch on the Nautilus Kubernetes GPU cluster.

**Tech4Good Lab — UC Santa Cruz** · Undergraduate Full-Stack Researcher
Generative-AI / ML web applications for social impact. Building standalone Angular components (Signals, OnPush change detection, Material / CDK) in the lab's TypeScript codebase.

---

## 🔧 Projects

### Multi-Threaded HTTP/1.1 Server · `C · POSIX threads`
Concurrent GET/PUT server: a fixed-size thread pool fed by a bounded producer–consumer queue with condition-variable signaling, plus per-URI reader–writer locks over a dynamic lock table. Queue and reader–writer lock primitives hand-implemented from scratch over raw POSIX syscalls.

### VeriFi — Vector Store for a RAG Pipeline · `C++` · *team project · in progress*
Conceived the project and lead a 5-person team; architected and own the core engine. An in-memory vector store with exact cosine-similarity k-NN retrieval that powers a Retrieval-Augmented Generation pipeline, grounding LLM answers in retrieved source documents.

### Neural Network Inference Engine · `C++ · PyTorch` · *in progress*
A from-scratch MNIST inference engine, no ML libraries (784→128→64→10). PyTorch training + binary weight-export pipeline **complete**; the C++ CPU forward pass — matrix multiply, ReLU, argmax — is in development. SIMD + multithreading and a CUDA port are planned.

### NVPilot — GPU Performance Agent · `TypeScript · NVML`
Autonomous GPU-tuning agent (perceive–plan–act–reflect loop, four tools) built at the NVIDIA × ASUS NemoClaw Hackathon — reads live GPU telemetry via NVML and manages OS-level process priority, freeing ~2 GB of VRAM and up to 10 FPS in Minecraft with shaders enabled. C++ / NVML rewrite in progress.
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

*Outside of code: chess, and recently took up swimming.*