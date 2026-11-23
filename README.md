<img width="100%" src="https://capsule-render.vercel.app/api?type=waving&color=0:0f0c29,50:302b63,100:24243e&height=200&section=header&text=Sudhan%20Shankar&fontSize=52&fontColor=ffffff&animation=fadeIn&fontAlignY=36&desc=ML%20%7C%20LiDAR%20%7C%20LLMs%20%7C%20Systems&descAlignY=58&descSize=18" />

<div align="center">

<a href="https://github.com/ThESLOwWoLF">
  <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&size=20&pause=1200&color=58A6FF&center=true&vCenter=true&width=640&lines=Final-year+CSE+%40+Amrita+Bengaluru+(2027);I+train+models+and+then+try+to+prove+them+wrong;Leakage+hunter.+Baseline+enjoyer.;Currently%3A+arguing+with+LiDAR+point+clouds" alt="Typing SVG" />
</a>

<a href="https://www.linkedin.com/in/sudhan-shankar-1710a529b/"><img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" /></a>
<a href="mailto:sudhan1345@gmail.com"><img src="https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white" /></a>
<img src="https://komarev.com/ghpvc/?username=ThESLOwWoLF&style=for-the-badge&color=blueviolet&label=visitors" />
<img src="https://img.shields.io/badge/fuel-red%20bull-DB0A40?style=for-the-badge" />
<img src="https://img.shields.io/badge/sleep-deprecated-555555?style=for-the-badge" />

<!-- ANIME GIF: paste a GIF link you like below and uncomment the line -->
<!-- <img src="PASTE_GIF_URL_HERE" width="320" /> -->

</div>

---

```bash
sudhan@slowwolf:~$ whoami
final-year CSE student, Amrita Vishwa Vidyapeetham, Bengaluru (2027)

sudhan@slowwolf:~$ cat interests.txt
ml        -> models I can actually evaluate, not just train
3d vision -> LiDAR point clouds, range images, geometry
llms      -> local models, orchestration, grounding
systems   -> anything that makes me read a spec at 2 am

sudhan@slowwolf:~$ ls achievements/
ieee_paper_rl.pdf   p2p_net_lidar/   wavlm_leakage_fix/   bi0s_ctf_forensics/

sudhan@slowwolf:~$ echo $STATUS
looking for internships: ML / Applied AI / Research Engineering

sudhan@slowwolf:~$ cat fuel.log
red bull   ████████████████████  100%
sleep      ██░░░░░░░░░░░░░░░░░░   10%
```

---

## Things I've built

### P2P-Net: Zero-Shot LiDAR Super-Resolution
![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white) ![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=flat-square&logo=pytorch&logoColor=white) ![NumPy](https://img.shields.io/badge/NumPy-013243?style=flat-square&logo=numpy&logoColor=white) ![Ouster](https://img.shields.io/badge/Ouster_SDK-222222?style=flat-square)

Doubles the vertical resolution of a LiDAR scan (64 to 128 beams) with **no external training data**.
Each missing beam's ray is intersected with tangent planes of its neighbours, and a tiny MLP, trained on the scan itself, picks which surface the ray actually hits.

> On 11 held-out real frames: **45% lower Chamfer distance** and **29% fewer flying points** than linear interpolation.
> Median error got slightly worse (2.20 vs 2.05 cm), and yes, I report that too.

<details>
<summary><b>The trick I'm proudest of</b></summary>

The OS1-64's beams turn out to be exactly the odd beams of the OS1-128 (checked in the sensor metadata).
So deleting the even beams from a real 128-beam scan gives a real 64-beam input, with measured ground truth on the exact same rays.
No simulation, no ICP, no guessing which point matches which.

</details>

[→ Repo](https://github.com/ThESLOwWoLF/LiDAR-Upscaling) · *v2 code landing soon*

---

### Speech Clarity Classifier on WavLM
![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white) ![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=flat-square&logo=pytorch&logoColor=white) ![HuggingFace](https://img.shields.io/badge/HF_Transformers-FFD21E?style=flat-square&logo=huggingface&logoColor=black) ![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white) ![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)

Classifies viva answer recordings as low / medium / high clarity using frozen WavLM embeddings and an SVM.

> **Plot twist:** my original 0.69 macro F1 was data leakage. After grouping by recording and moving every transform inside the pipeline, the honest number is **0.46** (MFCC baseline 0.42, chance 0.33).
> Lower number, much better project.

Served with FastAPI + a Gradio demo, 32 tests, 39 ms per clip on GPU.

[→ Repo](https://github.com/ThESLOwWoLF/Clarity-Assessment-in-Viva-Answers-in-speech-signals)

---

### Multi-LLM Research Orchestrator
![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white) ![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white) ![NVIDIA](https://img.shields.io/badge/NVIDIA_NIM-76B900?style=flat-square&logo=nvidia&logoColor=white) ![Ollama](https://img.shields.io/badge/Ollama-000000?style=flat-square&logo=ollama&logoColor=white)

Four LLMs (Gemma 4 31B, Llama 3.3 70B, DeepSeek, local Qwen) answer the same question, critique each other, then one writes the final answer.
Runs live as background asyncio tasks, so closing the tab doesn't kill the run: reconnect and it replays everything you missed.

---

### Omni-Exec: ELF64 / PE32+ Loader
![C](https://img.shields.io/badge/C-A8B9CC?style=flat-square&logo=c&logoColor=black) ![Assembly](https://img.shields.io/badge/x86--64_ASM-654FF0?style=flat-square) ![Linux](https://img.shields.io/badge/Linux-FCC624?style=flat-square&logo=linux&logoColor=black) ![Windows](https://img.shields.io/badge/Windows-0078D6?style=flat-square&logo=windows&logoColor=white)

Loads code from a Linux ELF on Windows (and a Windows PE on Linux) and calls it through a **24-byte trampoline I hand-encoded in machine code**, swapping Microsoft x64 argument registers into System V order.
Runs small position-independent functions for now. Relocations and imports are next.

```asm
48 89 CF    mov rdi, rcx   ; arg1: Windows -> Linux
48 89 D6    mov rsi, rdx   ; arg2
4C 89 C2    mov rdx, r8    ; arg3
4C 89 C9    mov rcx, r9    ; arg4
48 B8 ...   movabs rax, <target>
FF E0       jmp rax        ; and pray
```

[→ Repo](https://github.com/ThESLOwWoLF/ABI-Translator-for-Linux-Windows)

---

## Toolbox

**Languages**
![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white) ![C](https://img.shields.io/badge/C-A8B9CC?style=flat-square&logo=c&logoColor=black) ![C++](https://img.shields.io/badge/C++-00599C?style=flat-square&logo=cplusplus&logoColor=white) ![Bash](https://img.shields.io/badge/Bash-4EAA25?style=flat-square&logo=gnubash&logoColor=white)

**ML**
![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=flat-square&logo=pytorch&logoColor=white) ![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=flat-square&logo=scikitlearn&logoColor=white) ![HuggingFace](https://img.shields.io/badge/HF_Transformers-FFD21E?style=flat-square&logo=huggingface&logoColor=black) ![NumPy](https://img.shields.io/badge/NumPy-013243?style=flat-square&logo=numpy&logoColor=white) ![pandas](https://img.shields.io/badge/pandas-150458?style=flat-square&logo=pandas&logoColor=white) ![SciPy](https://img.shields.io/badge/SciPy-8CAAE6?style=flat-square&logo=scipy&logoColor=white) ![CUDA](https://img.shields.io/badge/CUDA-76B900?style=flat-square&logo=nvidia&logoColor=white) ![ONNX](https://img.shields.io/badge/ONNX_Runtime-005CED?style=flat-square&logo=onnx&logoColor=white)

**LLMs**
![NVIDIA NIM](https://img.shields.io/badge/NVIDIA_NIM-76B900?style=flat-square&logo=nvidia&logoColor=white) ![Ollama](https://img.shields.io/badge/Ollama-000000?style=flat-square&logo=ollama&logoColor=white)

**Backend & tools**
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white) ![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white) ![Linux](https://img.shields.io/badge/Linux-FCC624?style=flat-square&logo=linux&logoColor=black) ![Git](https://img.shields.io/badge/Git-F05032?style=flat-square&logo=git&logoColor=white) ![SQLite](https://img.shields.io/badge/SQLite-003B57?style=flat-square&logo=sqlite&logoColor=white)

---

## git log --oneline (lessons learned)

```text
f3a91c2  fix(wavlm): 0.69 F1 was leakage. honest score is 0.46. growth.
b7e04d1  feat(lidar): read the sensor metadata. found a free benchmark in it.
9c2d6aa  feat(omni-exec): learned what 48 89 CF means. cannot unlearn it.
4e18f07  chore: stopped trusting any number I can't reproduce
1a0b3e9  init: "it's just one quick project"
```

---

## Currently

- Rebuilding my English-to-KQL project around a local LLM, with a real KQL parser in the loop
- Testing whether four LLMs arguing actually beats the best single one
- Pushing P2P-Net v2 to GitHub
- Deep Learning Specialisation (DeepLearning.AI)

---

<div align="center">

<img src="https://raw.githubusercontent.com/ThESLOwWoLF/ThESLOwWoLF/output/github-contribution-grid-snake-dark.svg" width="100%" />

<img height="165" src="https://github-readme-stats.vercel.app/api?username=ThESLOwWoLF&show_icons=true&theme=tokyonight&hide_border=true" />
<img height="165" src="https://github-readme-stats.vercel.app/api/top-langs/?username=ThESLOwWoLF&layout=compact&theme=tokyonight&hide_border=true" />

*If you read this far, we should probably talk.*

<img width="100%" src="https://capsule-render.vercel.app/api?type=waving&color=0:24243e,50:302b63,100:0f0c29&height=120&section=footer" /> 
</div>
