# Christopher Zarraga

**C++ Systems Engineer · AI Infrastructure & HPC**

Computer Science @ UC Santa Cruz (Applied Mathematics minor) · Sabatte Family Full-Ride Scholar · Undergraduate AI Researcher

I build systems from scratch in C and C++ — concurrent servers, a hand-written neural-network inference engine, a custom vector store, and a limit order book — and I'm drawn to the layer where performance actually matters.

📍 Santa Cruz, CA · Open to SWE internships in AI/ML infrastructure, systems & performance engineering — **Summer 2027**

🌐 [Portfolio](https://kurisuo.github.io/Christopher-Zarraga-Portfolio-Website)

---

## 🔬 Research

**AIEA Lab — UC Santa Cruz** · Undergraduate AI Researcher *(Prof. Leilani Gilpin)*
*Robustifying Autonomous Vehicles* — I learned Kubernetes and the Nautilus GPU cluster from scratch to get access to CARLA and run the lab's experiments: GPU-scheduled jobs, PVC-backed storage, and pod specs written by hand. Now I'm evaluating SAC agents in Gymnasium's CarRacing environment with Stable-Baselines3, studying SAC and DDPG, and building a one-click benchmarking framework so multiple RL algorithms can be compared under a single pipeline with auto-generated reward, loss, and policy visualizations.

**Tech4Good Lab — UC Santa Cruz** · Undergraduate Full-Stack Researcher
I helped build and complete four goal-tracking components for Compass, the lab's goal-setting and reflection app — owning the data and event layer, which meant keeping state consistent from a user's action through NgRx Signal Store to Firestore. I also architected the bulk write pipeline that queues and reorders multi-record transactions. The lab is separately studying how to use AI agents properly in development, working inside Google Antigravity with a shared set of in-house agent skills where every stage of the Angular feature pipeline splits into a plan skill and an implement skill — and implement won't run until a plan is finalized.

---

## 🔧 Projects

### Neural Network Inference Engine · `C++17 · PyTorch`
A from-scratch MNIST inference engine with **no ML libraries at runtime** (784→128→64→10). The C++ CPU forward pass — dense matrix multiply, bias, ReLU, and argmax over flat row-major `float` storage — is complete and validated against the reference PyTorch model.
- **100% argmax agreement** with PyTorch across all 10,000 MNIST test images, reproducing an identical **9,694/10,000** accuracy.
- **~24,000 images/sec** (~0.041 ms/image) single-threaded on Apple M5, `-O2`.
- Designed the **binary weight-export format** and matching C++ loader, pinning one transpose convention across both sides so layer shapes stay consistent.
- Caught a **false positive in my own validation gate** — a hardcoded accuracy constant from a separate training run, sitting 39 images off the model under test and clearing tolerance by 0.0011. Fixed by deriving the PyTorch baseline at runtime, tightening the assertion to exact count equality, and mutation-testing the assert to prove it could still fail.
- Also surfaced a **20× `-O0` vs `-O2` gap** the default build had been silently shipping, by splitting release and test build configurations.
- SIMD, multithreading, and a CUDA port are planned.

🔗 [github.com/Kurisuo/neural-inference-engine](https://github.com/Kurisuo/neural-inference-engine)

### Multi-Threaded HTTP/1.1 Server · `C · POSIX threads`
Sustained **~8,400 req/s** with **99% of requests under ~13 ms** across 64 concurrent connections — **2.2× a single-threaded baseline**, measured with wrk (connection-per-request, 6-core aarch64 VM) — by pairing a fixed-size thread pool with a bounded producer-consumer queue. The queue and per-URI reader–writer locks were hand-implemented over raw POSIX syscalls with no library concurrency. My first benchmark silently linked the reference library instead of my own primitives, so I verified symbol provenance with `nm`, fixed the link order, and re-ran the full matrix.

🔗 [github.com/Kurisuo/multithreaded-http-server](https://github.com/Kurisuo/multithreaded-http-server)

### VeriFi — Vector Store for a RAG Pipeline · `C++17` · *5-person team*
I founded this and led a five-person team building an in-memory vector store that grounds LLM answers in sourced company policy documents. Most of my time went to defining the Day-1 interface contracts — chunk format, search API, response schema — so five people could build in parallel instead of blocking on each other. I own the retrieval engine itself: exact cosine-similarity k-NN, written as a correctness baseline before any optimization. Benchmarked single-threaded (Apple M5, `-O2`, synthetic 384-dim vectors, correctness-gated by a self-retrieval property test): **0.36 ms p50 at 1K vectors, scaling linearly to 96 ms at 250K, with ~33K chunks/sec ingestion.** Full-sort top-k dominates after the O(N·d) scan — partial-sort/heap selection, indexing, and SIMD are the next targets.

🔗 [github.com/Kurisuo/VeriFi](https://github.com/Kurisuo/VeriFi)

### NVPilot — GPU / System Performance Agent · `TypeScript · Node · NVML`
An autonomous performance agent (perceive–plan–act–reflect loop) that reads live GPU telemetry via NVML, classifies hardware tier, and applies surgical, fully reversible system and power optimizations in real time. Built at the NVIDIA × ASUS NemoClaw Hackathon and finished solo after the team moved on.
- Full system perception in **~550 ms**; rule-based plan generation **<1 ms** (measured on an RTX 3060 Laptop).
- **Journal-based reversibility** — every mutation records a mechanical inverse; verified byte-identical config restoration with **~3 s** full rollback.
- **Constrained LLM autonomy** — a validation layer rejects unknown settings, clamps values to legal per-setting ranges, and overwrites state fields from live telemetry, so the model can't misreport what it's changing. A deterministic rule engine takes over if the LLM is offline or its output fails schema checks.
- Scans **400+ processes** per cycle, identifying ~2 GB of reclaimable background memory.
- **~2,800 lines** of strict-mode TypeScript across 4 subsystems (drivers, planners, core engine, tool interface).

🔗 [github.com/Kurisuo/NVPilot](https://github.com/Kurisuo/NVPilot) · Live demo: [kurisuo.github.io/NVPilot](https://kurisuo.github.io/NVPilot/)

### Limit Order Book Matching Engine · `C++`
A price-time-priority limit order book matching engine, extended with two original order types I designed for tighter execution control:
- **Banded Execution Order** — a tolerance band around the limit price; the order rests rather than filling when the market gaps beyond an acceptable floor/ceiling, protecting against flash-crash slippage.
- **VWAP Pre-Execution Gate** — computes the volume-weighted average across available liquidity *before* matching, executing only if the blended fill clears the limit price, so a large order in a thin book can't silently average above the intended ceiling.

Engine and both order types implemented; validation suite in progress.

---

*Building next: an NES emulator in C++ (6502 CPU and PPU from scratch), AVScope — a C++ tool for benchmarking autonomous-vehicle experiments — and a lock-free concurrent queue using C++ atomics.*

---

## 🛠 Tech

**Systems:** C · C++17/20 · POSIX threads · Linux · CMake · gdb · Valgrind · wrk · Git
**GPU & Infra:** NVML · GPU telemetry · Kubernetes (Nautilus) · Docker · Bash · CUDA *(learning)*
**ML & Research:** Python · PyTorch · NumPy · Pandas · Stable-Baselines3 · Gymnasium · CARLA
**Web:** TypeScript · Angular · Firebase · NgRx Signal Store
**Workflow:** Cursor · Claude Code · Google Antigravity

---

## 📚 Selected Coursework

Parallel Programming · Computer Systems Design · Software Engineering · Artificial Intelligence · Databases · Data Structures & Algorithms · Computer Systems & C · Linear Algebra · Discrete Mathematics

---

## 🏅 Honors

Sabatte Family Full-Ride Scholarship (first cohort in university history) · Co-Founder, Sabatte & Regents Scholars Association · SHPE · NVIDIA × ASUS Hackathon · Y Combinator Startup Internship Expo 2027 (accepted)

---

## 📫 Contact

📧 christopherzarraga31@gmail.com · 💼 [LinkedIn](https://linkedin.com/in/christopher-zarraga) · 🌐 [Portfolio](https://kurisuo.github.io/Christopher-Zarraga-Portfolio-Website)

*Outside of code: chess (1900 bullet, 2000 peak), active trading, lap swimming, calisthenics, and 18–55mm photography.*
