# 🏄‍♂️ [Vicio](https://www.linkedin.com/in/viciodicara/) <img src="https://media.giphy.com/media/hvRJCLFzcasrR4ia7z/giphy.gif" width="28px" height="28px">

# Remember This: Try.

<p>
  <a href="#"><img src="https://github-readme-stats.vercel.app/api?username=VicDc&show_icons=true&count_private=true&theme=aura" width="350"></a>
</p>

<img src="https://raw.githubusercontent.com/VicDc/VicDc/main/img/sea-sunset.gif" alt="Sea Sunset GIF" align='right' width="350px"/>

[![Linkedin Badge](https://img.shields.io/badge/-viciodicara-blue?style=flat-square&logo=Linkedin&logoColor=white&link=https://www.linkedin.com/in/viciodicara/)](https://www.linkedin.com/in/viciodicara/)
<p align="left"> <img src="https://komarev.com/ghpvc/?username=VicDc" alt="VicDc" /> </p>

<div style="text-align: right">There are 10 types of people in the world: those who understand binary and those who don't...</div>

---

## 🏆 Featured Projects

### 🥇 Malaria AI Scope — *1st Place, AWS University Engagement Program*
> Automated malaria parasite detection & classification using **YOLOv11 segmentation** across 17 distinct classes (4 species × 4 life stages). Processes microscopic blood smear images through advanced OpenCV preprocessing, achieving **62% mAP50** on multi-class segmentation. Full pipeline: dataset conversion → augmentation → training with checkpoint management → real-time clinical inference.

`Python` `PyTorch` `YOLOv11` `OpenCV` `AWS` `Ultralytics`

---

### 🥈 Sherpa Alzheimer — *2nd Place, OPIT AI Competition*
> Multi-agent **RAG chatbot** for Alzheimer's care, built with **FastAPI + Milvus + Redis**. Adapts tone and terminology for three user roles (patient, caregiver, doctor) across 4 languages. Full-stack: Next.js frontend, multi-agent pipeline (RAGAgent → SupervisorAgent), Telegram & WhatsApp integration, and optional fully offline deployment via Ollama.

`Python` `FastAPI` `Next.js` `Milvus` `Redis` `RAG` `LLM` `Docker`

---

### 🎓 LisAI Interpreter — *OPIT Master's Capstone Project*
> Real-time **Italian Sign Language (LIS)** recognition system bridging the accessibility gap. Engineered end-to-end ML pipeline: FFmpeg-based video augmentation, MediaPipe Holistic for 543-keypoint extraction, dual-model architecture (MLP/CNN for letters at **87.3% accuracy** + Bi-LSTM/Transformer for words), and LLM-powered gloss-to-Italian translation (Gemma, Llama-3). Processes at 30+ FPS for letters, 15–20 FPS for words.

`Python` `PyTorch` `TensorFlow` `MediaPipe` `OpenCV` `LSTM` `Transformer` `FFmpeg`

---

## 🧠 AI Architectures I've Built With

A map of the deep learning architectures and ML systems I've applied across real projects — not tutorials, but production pipelines.

---

### 🔷 Computer Vision

| Architecture | Project | Details |
|---|---|---|
| **YOLOv11 Instance Segmentation** | 🥇 Malaria AI Scope | 17-class parasite segmentation on microscopic blood smear images. Custom dataset pipeline with multi-format conversion (Masks/JSON/TXT → YOLO). Incremental learning support. **62% mAP50** |
| **MediaPipe Holistic** | 🎓 LisAI | Full-body landmark extraction: 468 face mesh + 33 pose + 42 hand points = **543 keypoints/frame**. Spatial normalization relative to shoulder midpoint for scale/distance invariance |
| **MLP / 1D-CNN (Static)** | 🎓 LisAI | 63-dim input (21 hand landmarks × 3 coords). 3 Dense layers (256→128→64) + ReLU + Dropout(0.3). **87.3% accuracy** on 26-class fingerspelling |
| **OpenCV Preprocessing** | 🥇 Malaria AI Scope | Advanced preprocessing pipeline for heterogeneous medical image datasets. Gaussian blur, brightness normalization, contour analysis |

---

### 🔶 Sequence Models & Temporal Learning

| Architecture | Project | Details |
|---|---|---|
| **Bidirectional LSTM (Bi-LSTM)** | 🎓 LisAI | Sequence input: `(T, 1662)` feature matrix. Bidirectional layers let the model see future frames when classifying current state — critical for signs where the ending disambiguates the beginning |
| **Transformer (Multi-Head Self-Attention)** | 🎓 LisAI | Long-range dependency capture across full gesture sequences. Parallel frame attention vs. LSTM's sequential processing. Adam optimizer with decaying LR schedule |
| **GRU** | 🎓 LisAI | Evaluated alongside LSTM/Transformer as lighter alternative for temporal gesture modeling |
| **Forward Padding + Masking** | 🎓 LisAI | Variable-length sign sequences (20–180 frames) unified via Keras masking layer — ensures backpropagation ignores padded frames |

---

### 🔵 NLP & Large Language Models

| Architecture | Project | Details |
|---|---|---|
| **Multi-Agent RAG Pipeline** | 🥈 Sherpa | Sequential: `RAGAgent → SupervisorAgent`. Score-threshold filtering (cosine sim ≥ 0.55) prevents hallucinated citations. Conversational fallback when no chunks pass threshold |
| **LLM Fine-tuning (QLoRA)** | ✅ Mental D0C | Fine-tuned **Qwen3** with **Unsloth** on 12,000+ synthetic mental health conversations. Instruction-tuning for clinical assessment dialogue |
| **Gloss-to-Natural Language (LLM post-processing)** | 🎓 LisAI | Local LLM integration (Gemma, Llama-3 via Ollama/LM Studio) for: ① LIS gloss → Italian grammar ("IO MANGIARE MELA" → "Sto mangiando una mela") ② Ambiguity resolution via sliding context window |
| **Beam Search Context Engine** | 🎓 LisAI | Rule-based module combining model confidence scores + language frequency dictionary for most-likely word sequence decoding |
| **Vector Similarity Search (Milvus)** | 🥈 Sherpa | FLAT index, COSINE metric. 1024-dim embeddings. Top-k=5 retrieval with score-threshold gate. Snapshot system for portable pre-computed vector DB |

---

### 🟢 Classical ML & Ensemble Methods

| Architecture | Project | Details |
|---|---|---|
| **Random Forest Classifier** | ✅ Drug Repositioning | **92% accuracy / precision / recall / F1** on 84,400-sample biomedical dataset for novel drug-disease association prediction |
| **K-Means Clustering** | ✅ Drug Repositioning | Identified **10 optimal semantic clusters** in biomedical embedding space to surface hidden drug-disease patterns |

---

### ⚙️ Data Engineering & MLOps Patterns

| Pattern | Project | Details |
|---|---|---|
| **FFmpeg Video Augmentation Pipeline** | 🎓 LisAI | Custom engine: geometric (H-flip for handedness swap, ±15° rotation, scale jitter) + temporal (0.8×–1.2× speed) + photometric (Gaussian blur, brightness) augmentation |
| **Mixed Precision Training** | 🎓 LisAI | FP16 training with checkpoint management for memory-efficient long-sequence model training |
| **Incremental / Continual Learning** | 🥇 Malaria AI Scope | YOLOv11 training pipeline supporting incremental dataset expansion without full retraining |
| **Multi-format Dataset Conversion** | 🥇 Malaria AI Scope | Unified ingestion from heterogeneous annotation formats (binary masks, COCO JSON, plain TXT) → YOLO segmentation format |
| **Docker Multi-stage Build** | 🥈 Sherpa | Separate builder/production stages for Python backend + Node.js frontend. Non-root users, health checks, depends_on ordering |
| **RAG Snapshot System** | 🥈 Sherpa | Export/import pre-computed Milvus vectors as portable JSON (with SHA-256 manifest). Eliminates re-embedding on fresh deployments |

---

## :computer: My Tech Stack

### Languages & Databases
<p>
  <a href="https://skillicons.dev">
    <img src="https://skillicons.dev/icons?i=python,mysql" />
  </a>
</p>

### AI & Data Science
<p>
  <a href="https://skillicons.dev">
    <img src="https://skillicons.dev/icons?i=tensorflow,pytorch,sklearn,opencv,selenium,pandas,numpy,matplotlib,anaconda,jupyter,huggingface" />
  </a>
</p>

### Cloud & DevOps
<p>
  <a href="https://skillicons.dev">
    <img src="https://skillicons.dev/icons?i=aws,gcp,firebase,docker,linux,git,github" />
  </a>
</p>

### Design & Development Tools
<p>
  <a href="https://skillicons.dev">
    <img src="https://skillicons.dev/icons?i=figma,canva,ps,ai,pr,ae,xd,latex,vscode,raspberrypi" />
  </a>
  <img src="https://img.shields.io/badge/AutoCAD-F29B0C?style=for-the-badge&logo=autocad&logoColor=white" alt="AutoCAD"/>
</p>

---

## :man_technologist: Who am I?

```python
class WhoAmI:
    user = 'Vicio Di Cara'
    birth_fact = 'The first internet ping in Italy coincides with my birth'

    currently_working_on = [
        "🎓 LisAI Interpreter — OPIT Master's Capstone (CNN-LSTM + Transformer)",
        "🥇 Malaria AI Scope — 1st Place AWS University Engagement Program",
        "🥈 Sherpa Alzheimer — 2nd Place OPIT AI Competition (Multi-Agent RAG)",
        "✅ Drug Repositioning Research (Random Forest + K-means, 92% accuracy)",
        "✅ Mental D0C — LLM fine-tuned for mental health assessment (Qwen3)",
        "🚀 Building AI Agents to help others"
    ]

    hobbies = [
        "Surfing",
        "Bouldering",
        "Coding for Good"
    ]

    def get_city():
        return "Palermo, Italy"

    def future_ambitions():
        return "To travel the world, programming to help others."
```
