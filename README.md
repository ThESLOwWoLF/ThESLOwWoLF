# Hi, I'm Sudhan Shankar

Final-year CSE student at Amrita Vishwa Vidyapeetham, Bengaluru (2027).
I work at the intersection of computer networks, network security, and machine learning.

---

## About me

- Genuinely interested in how networks are built, how they break, and how to secure them
- Competed in CTFs under Team bi0s — file forensics and network forensics
- Completed Arista Networks' 12-week bootcamp (Layer 2/3, EOS CLI, switching and routing)
- Published first-author IEEE research on reinforcement learning
- Preparing for CCNA
- Looking for internships in Network Engineering, Network Software Dev, and ML/AI — Bangalore

---

## Projects

### Omni-Exec — Bi-Directional ABI Translator (Linux ↔ Windows)
`C` `x86-64 Assembly` `ELF64` `PE32+` `Linux` `Windows`

Executes Linux ELF64 binaries natively on Windows and Windows PE32+ binaries natively on Linux — no VM, no emulator.
Built a 4-stage pipeline: ELF/PE header parser → OS-native memory allocator (mmap / VirtualAlloc with PROT_EXEC) → ABI register trampoline (Microsoft x64 ↔ System V calling conventions) → direct execution via function pointer.

[→ View on GitHub](https://github.com/ThESLOwWoLF/ABI-Translator-for-Linux-Windows)

---

### MCP Orchestrator 3 — Multi-Agent AI Research Platform
`Python` `FastAPI` `WebSockets` `asyncio` `SQLite` `JWT` `NVIDIA NIM` `Ollama`

Runs Gemini, GPT-OSS 120B, Meta Llama (via NVIDIA NIM), and local Ollama in parallel using asyncio.gather().
Real-time WebSocket streaming with per-user state isolation, reconnect support, and incremental DB persistence.
JWT auth, referral-driven access control, DuckDuckGo RAG at full depth. All 7 integration tests passed.

---

### Speech Clarity Classifier — WavLM + LDA-SVM
`Python` `PyTorch` `CUDA` `librosa` `scikit-learn` `pandas`

GPU-accelerated binary audio classifier fine-tuned on Microsoft WavLM.
Achieved macro F1 0.68 across 713 samples (Low: 0.75 / Medium: 0.67 / High: 0.62).
LDA outperformed PCA by +0.44 F1 on the hardest class.

[→ View on GitHub](https://github.com/ThESLOwWoLF/Clarity-Assessment-in-Viva-Answers-in-speech-signals)

---

### MQTT Smart Proxy Firewall — IoT Network Security
`Python` `MQTT` `paho-mqtt` `JSON Schema` `Rate Limiting` `Access Control`

Proxy firewall that intercepts IoT traffic before it reaches the broker.
Time-window rate limiting against flooding attacks, role-based topic authorization,
deep packet inspection with JSON schema validation to catch malformed payloads and injection attempts.

---

### SDN Network Slicing & QoS Platform
`Python` `Ryu` `Mininet` `OpenFlow` `Open vSwitch` `Linux HTB` `REST API` `JavaScript`

SDN slicing solution with three tiered QoS classes: Premium, Standard (capped at 2 Mbps), and Best Effort.
OpenFlow flow rules classify traffic by L4 ports and route into dedicated HTB queues.
Real-time bandwidth dashboard — Python REST API + JavaScript frontend polling live stats.

---

### LiDAR Point Cloud Super-Resolution
`Python` `OpenCV` `NumPy` `Potts Model` `ICP Alignment`

Upscales 32/64-beam LiDAR scans to 128-beam (4x point density) for autonomous driving.
Potts model energy minimisation with edge preservation and ICP alignment.
~3x speedup via vectorised NumPy over naive iterative processing.

[→ View on GitHub](https://github.com/ThESLOwWoLF/LiDAR-Upscaling)

---

## Skills

**Networking:** TCP/IP · MQTT · OpenFlow · SDN · VLANs · STP · OSPF · QoS · Linux HTB  
**ML / DL:** PyTorch · scikit-learn · NumPy · pandas · librosa · OpenCV · CUDA  
**Languages:** Python · C · C++ · x86-64 Assembly · Bash · JavaScript  
**Tools:** FastAPI · WebSockets · Docker · Git · Linux · Ryu · Mininet · Wireshark  

---

## Find me

- LinkedIn: [Sudhan Shankar](https://www.linkedin.com/in/sudhan-shankar-1710a529b/)
- Email: sudhan1345@gmail.com
