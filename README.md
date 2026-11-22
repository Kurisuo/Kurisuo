## Christopher Zarraga
**OS Internals · Linux · CUDA · Systems C/C++**

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/christopher-zarraga)
[![Email](https://img.shields.io/badge/Email-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:christopherzarraga31@gmail.com)
[![Portfolio](https://img.shields.io/badge/Portfolio-27272A?style=for-the-badge&logo=firefox&logoColor=white)](https://kurisuo.github.io/Christopher-Zarraga-Portfolio-Website/)

<img align="left" width="145" alt="Christopher Zarraga" src="https://github.com/user-attachments/assets/1eedef93-8d35-4af1-9c3d-bf6fff2286f0" />

Hi, I'm Chris — a CS student at UC Santa Cruz (Applied Math minor) focused on low-level systems, OS internals, Linux, CUDA, and practical AI that improves everyday tech.

**Building:** **SlugOS** — a from-scratch x86_64 OS in C++ with Limine<br>
**Research:** Autonomous Vehicle frame-monitoring @ UCSC AIEA Lab<br>
**Seeking:** Spring & Summer 2027 SWE Internships<br>
**Off-clock:** Lap swimming *(learned earlier this year)*, chess, and calisthenics

<br clear="left"/>

---

### Featured Projects

#### SlugOS *(In Progress)*
*C++ · Limine · QEMU · x86_64* — [GitHub](https://github.com/Kurisuo)
* Building a bare-metal operating system from scratch with custom memory management, preemptive multithreading, Ring 3 user isolation, and a minimalist serial/framebuffer shell.

#### Multi-Threaded HTTP Server
*C · POSIX* — [GitHub](https://github.com/Kurisuo/multithreaded-http-server) · [Live Site](https://your-http-server-site-url)
* Sustains **8,400 req/s** at 64 concurrent connections (**~13 ms p99** on a 6-core VM).
* Achieved a **2.2x speedup** via a fixed thread pool, bounded producer-consumer queue, per-URI reader-writer locks, and audit logging.

#### Neural Network Inference Engine
*C++17 · Python · PyTorch* — [GitHub](https://github.com/Kurisuo/neural-inference-engine) · [Live Site](https://your-inference-engine-site-url)
* Zero-dependency C++17 MLP inference engine matching PyTorch's predicted labels across all **10,000 MNIST test images** at **24,000 images/sec** on a single CPU thread.
* Caught and fixed a flawed validation baseline off by 39 images, replacing it with runtime baseline calculation and injected-bug verification.

#### VeriFi
*C++17 · nlohmann/JSON* — [GitHub](https://github.com/Kurisuo/VeriFi) · [Live Site](https://your-verifi-site-url)
* Founded and led a 5-person team building a policy-grounded RAG system with shared chunk, search API, and response schemas.
* Built a custom C++ top-*k* cosine-similarity search engine hitting **0.36 ms/search** over 1k passages and scaling linearly to **96 ms** at 250k passages (**33k chunks/sec** ingestion).

#### NVPilot *(NVIDIA × ASUS Hackathon)*
*TypeScript · NVML · NVIDIA NeMo* — [GitHub](https://github.com/Kurisuo/NVPilot) · [Live Site](https://your-nvpilot-site-url)
* AI agent using NVML telemetry to tune system settings with **550 ms** perception and **sub-1 ms** rule-based planning, freeing **2 GB of RAM** across 400+ background processes on an RTX 3060 laptop.
* Engineered safe reversibility with range validation, reversal logging, deterministic rule fallback, and byte-for-byte rollback in **~3 s**.

---

### Tools & Skillsets

**Languages**  
![C](https://img.shields.io/badge/C-00599C?style=for-the-badge&logo=c&logoColor=white)
![C++](https://img.shields.io/badge/C%2B%2B-00599C?style=for-the-badge&logo=cplusplus&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-4479A1?style=for-the-badge&logoColor=white)

**Systems & Infra**  
![Linux](https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black)
![Bash](https://img.shields.io/badge/Bash-4EAA25?style=for-the-badge&logo=gnubash&logoColor=white)
![CMake](https://img.shields.io/badge/CMake-064F8C?style=for-the-badge&logo=cmake&logoColor=white)
![Git](https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![Kubernetes](https://img.shields.io/badge/Kubernetes-326CE5?style=for-the-badge&logo=kubernetes&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=for-the-badge&logo=postgresql&logoColor=white)

**ML & Simulation**  
![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=for-the-badge&logo=pytorch&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white)
![Gymnasium](https://img.shields.io/badge/Gymnasium-0081A5?style=for-the-badge&logoColor=white)
![Stable-Baselines3](https://img.shields.io/badge/Stable--Baselines3-1E3A8A?style=for-the-badge&logoColor=white)

**AI Tooling**  
![NVIDIA NeMo Agents](https://img.shields.io/badge/NVIDIA_NeMo_Agents-76B900?style=for-the-badge&logo=nvidia&logoColor=white)
![Ollama](https://img.shields.io/badge/Ollama-18181B?style=for-the-badge&logo=ollama&logoColor=white)
![OpenAI API](https://img.shields.io/badge/OpenAI_API-412991?style=for-the-badge&logo=openai&logoColor=white)
![Claude Code](https://img.shields.io/badge/Claude_Code-D97757?style=for-the-badge&logo=anthropic&logoColor=white)
![Cursor](https://img.shields.io/badge/Cursor-000000?style=for-the-badge&logo=cursor&logoColor=white)
![Codex](https://img.shields.io/badge/Codex-10A37F?style=for-the-badge&logo=openai&logoColor=white)
![ElevenLabs](https://img.shields.io/badge/ElevenLabs-111111?style=for-the-badge&logo=elevenlabs&logoColor=white)
![Google Antigravity](https://img.shields.io/badge/Google_Antigravity-4285F4?style=for-the-badge&logo=google&logoColor=white)
