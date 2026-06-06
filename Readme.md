# 🏄‍♂️ [Vicio Di Cara](https://www.linkedin.com/in/viciodicara/) <img src="https://media.giphy.com/media/hvRJCLFzcasrR4ia7z/giphy.gif" width="28px" height="28px">

### AI / ML Engineer · Shipping deployed AI, grounded in 3+ years of B2B technical consulting

> Remember this: Try.

I build end-to-end AI systems (multi-agent RAG, computer vision, LLM fine-tuning) and currently complete an **MSc in Applied Data Science & AI @ OPIT**. Background in industrial B2B consulting, so I care about systems that ship and stakeholders who are not engineers.

<img src="https://raw.githubusercontent.com/VicDc/VicDc/main/img/sea-sunset.gif" alt="Sea Sunset GIF" align='right' width="350px"/>

[![Linkedin Badge](https://img.shields.io/badge/-viciodicara-blue?style=flat-square&logo=Linkedin&logoColor=white&link=https://www.linkedin.com/in/viciodicara/)](https://www.linkedin.com/in/viciodicara/)
<a href="https://bento.me/viciodc"><img src="https://img.shields.io/badge/Portfolio-bento.me-6C5CE7?style=flat-square&logo=googlechrome&logoColor=white" alt="Portfolio"/></a>
<img src="https://komarev.com/ghpvc/?username=VicDc" alt="VicDc" />

<sub>There are 10 types of people in the world: those who understand binary and those who don't.</sub>

<br clear="right"/>

<p>
  <a href="#"><img src="https://github-readme-stats.vercel.app/api?username=VicDc&show_icons=true&count_private=true&theme=aura" height="170"></a>
  <a href="#"><img src="https://github-readme-stats.vercel.app/api/top-langs/?username=VicDc&layout=compact&theme=aura&langs_count=8" height="170"></a>
</p>

---

## 🏆 Featured Projects

### 🥇 Malaria AI Scope · 1st Place, AWS University Engagement Program
> Automated malaria parasite detection and classification using **YOLOv11 segmentation** across 17 classes (4 species × 4 life stages). Microscopic blood smear images pass through an OpenCV preprocessing pipeline, reaching **62% mAP50** on multi-class segmentation. Full workflow: dataset conversion, augmentation, training with checkpoint management, real-time clinical inference.

`Python` `PyTorch` `YOLOv11` `OpenCV` `AWS` `Ultralytics`
[`→ repo`](https://github.com/VicDc/MalariaAI-Scope)

---

### 🥈 Sherpa Alzheimer · 2nd Place, OPIT Hackathon 2026
> Multi-agent **RAG chatbot** for Alzheimer's care, built on **FastAPI + Milvus + Redis**. Adapts tone and terminology for three user roles (patient, caregiver, doctor) across four interface languages. Full-stack: Next.js frontend, multi-agent pipeline (RAGAgent then SupervisorAgent), Telegram and WhatsApp channels, and an optional fully offline deployment via Ollama.

`Python` `FastAPI` `Next.js` `Milvus` `Redis` `RAG` `LLM` `Docker`
[`→ repo`](https://github.com/VicDc/Alzheimer-assistant)

---

### 🤟 LisAI Interpreter · Real-time Italian Sign Language Recognition
> Computer vision and deep learning system for **Italian Sign Language (LIS)**. End-to-end ML pipeline: FFmpeg-based video augmentation, MediaPipe Holistic for **543-keypoint** extraction, and a two-tier architecture. Static fingerspelling recognition (MLP / 1D-CNN) reaches **87.3% accuracy at 30+ FPS**. Word-level recognition was explored as a research track using sequence models (Bi-LSTM, Transformer) and LLM-based gloss-to-Italian refinement (Gemma, Llama-3).

`Python` `PyTorch` `TensorFlow` `MediaPipe` `OpenCV` `Bi-LSTM` `Transformer` `FFmpeg`

---

## 🧠 AI Architectures I've Built With

A map of the deep learning architectures and ML systems I've applied across real projects, not tutorials but production pipelines.

### 🔷 Computer Vision

| Architecture | Project | Details |
|---|---|---|
| **YOLOv11 Instance Segmentation** | 🥇 Malaria AI Scope | 17-class parasite segmentation on microscopic blood smear images. Custom dataset pipeline with multi-format conversion (Masks/JSON/TXT to YOLO). Incremental learning support. **62% mAP50** |
| **MediaPipe Holistic** | 🤟 LisAI | Full-body landmark extraction: 468 face mesh + 33 pose + 42 hand points = **543 keypoints/frame**. Spatial normalization relative to shoulder midpoint for scale and distance invariance |
| **MLP / 1D-CNN (Static)** | 🤟 LisAI | 63-dim input (21 hand landmarks × 3 coords). 3 Dense layers (256, 128, 64) + ReLU + Dropout(0.3). **87.3% accuracy** on 26-class fingerspelling |
| **OpenCV Preprocessing** | 🥇 Malaria AI Scope | Preprocessing pipeline for heterogeneous medical image datasets. Gaussian blur, brightness normalization, contour analysis |

### 🔶 Sequence Models & Temporal Learning

| Architecture | Project | Details |
|---|---|---|
| **Bidirectional LSTM (Bi-LSTM)** | 🤟 LisAI | Sequence input: `(T, 1662)` feature matrix. Bidirectional layers let the model see future frames when classifying the current state, useful for signs where the ending disambiguates the beginning |
| **Transformer (Multi-Head Self-Attention)** | 🤟 LisAI | Long-range dependency capture across full gesture sequences. Parallel frame attention vs. sequential LSTM processing. Adam optimizer with decaying LR schedule |
| **GRU** | 🤟 LisAI | Evaluated alongside LSTM and Transformer as a lighter alternative for temporal gesture modeling |
| **Forward Padding + Masking** | 🤟 LisAI | Variable-length sign sequences (20 to 180 frames) unified via Keras masking layer, so backpropagation ignores padded frames |

### 🔵 NLP & Large Language Models

| Architecture | Project | Details |
|---|---|---|
| **Multi-Agent RAG Pipeline** | 🥈 Sherpa | Sequential `RAGAgent → SupervisorAgent`. Score-threshold filtering (cosine sim ≥ 0.55) prevents hallucinated citations. Conversational fallback when no chunks pass the threshold |
| **LLM Fine-tuning (QLoRA)** | ✅ Mental D0C | Fine-tuned **Qwen3** with **Unsloth** on 12,000+ synthetic mental health conversations. Instruction-tuning for clinical assessment dialogue |
| **Gloss-to-Natural Language (LLM post-processing)** | 🤟 LisAI | Local LLM integration (Gemma, Llama-3 via Ollama / LM Studio): LIS gloss to Italian grammar ("IO MANGIARE MELA" to "Sto mangiando una mela") and ambiguity resolution via sliding context window |
| **Beam Search Context Engine** | 🤟 LisAI | Rule-based module combining model confidence scores and a language frequency dictionary for most-likely word sequence decoding |
| **Vector Similarity Search (Milvus)** | 🥈 Sherpa | FLAT index, COSINE metric, 1024-dim embeddings. Top-k=5 retrieval with score-threshold gate. Snapshot system for portable pre-computed vector DB |

### 🟢 Classical ML & Ensemble Methods

| Architecture | Project | Details |
|---|---|---|
| **Random Forest Classifier** | ✅ Drug Repositioning | **92% accuracy / precision / recall / F1** on an 84,400-sample biomedical dataset for novel drug-disease association prediction |
| **K-Means Clustering** | ✅ Drug Repositioning | Identified **10 optimal semantic clusters** in biomedical embedding space to surface hidden drug-disease patterns |

### ⚙️ Data Engineering & MLOps Patterns

| Pattern | Project | Details |
|---|---|---|
| **FFmpeg Video Augmentation Pipeline** | 🤟 LisAI | Custom engine: geometric (H-flip for handedness swap, ±15° rotation, scale jitter), temporal (0.8x to 1.2x speed), photometric (Gaussian blur, brightness) |
| **Mixed Precision Training** | 🤟 LisAI | FP16 training with checkpoint management for memory-efficient long-sequence model training |
| **Incremental / Continual Learning** | 🥇 Malaria AI Scope | YOLOv11 training pipeline supporting incremental dataset expansion without full retraining |
| **Multi-format Dataset Conversion** | 🥇 Malaria AI Scope | Unified ingestion from heterogeneous annotation formats (binary masks, COCO JSON, plain TXT) to YOLO segmentation format |
| **Docker Multi-stage Build** | 🥈 Sherpa | Separate builder and production stages for Python backend and Node.js frontend. Non-root users, health checks, depends_on ordering |
| **RAG Snapshot System** | 🥈 Sherpa | Export/import pre-computed Milvus vectors as portable JSON (with SHA-256 manifest). Eliminates re-embedding on fresh deployments |

---

## :computer: My Tech Stack

### Languages & Databases
<p>
  <a href="https://skillicons.dev">
    <img src="https://skillicons.dev/icons?i=python,mysql,postgres,sqlite" />
  </a>
  <img src="https://img.shields.io/badge/SQL-4479A1?style=for-the-badge&logo=databricks&logoColor=white" alt="SQL"/>
</p>

### AI & Data Science
<p>
  <!-- Frameworks supported by skillicons -->
  <a href="https://skillicons.dev">
    <img src="https://skillicons.dev/icons?i=tensorflow,pytorch,sklearn,opencv" />
  </a>
  <!-- Libraries via shields.io -->
  <img src="https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white" alt="NumPy"/>
  <img src="https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white" alt="Pandas"/>
  <img src="https://img.shields.io/badge/Matplotlib-11557c?style=for-the-badge&logo=plotly&logoColor=white" alt="Matplotlib"/>
  <img src="https://img.shields.io/badge/Plotly-3F4F75?style=for-the-badge&logo=plotly&logoColor=white" alt="Plotly"/>
  <img src="https://img.shields.io/badge/Jupyter-F37626?style=for-the-badge&logo=jupyter&logoColor=white" alt="Jupyter"/>
  <img src="https://img.shields.io/badge/Anaconda-44A833?style=for-the-badge&logo=anaconda&logoColor=white" alt="Anaconda"/>
  <img src="https://img.shields.io/badge/HuggingFace-FFD21E?style=for-the-badge&logo=huggingface&logoColor=black" alt="HuggingFace"/>
  <img src="https://img.shields.io/badge/MediaPipe-0097A7?style=for-the-badge&logo=google&logoColor=white" alt="MediaPipe"/>
  <img src="https://img.shields.io/badge/Ultralytics-111F68?style=for-the-badge&logo=yolo&logoColor=white" alt="Ultralytics YOLO"/>
  <img src="https://img.shields.io/badge/Unsloth-8A2BE2?style=for-the-badge&logo=lightning&logoColor=white" alt="Unsloth"/>
  <img src="https://img.shields.io/badge/FFmpeg-007808?style=for-the-badge&logo=ffmpeg&logoColor=white" alt="FFmpeg"/>
</p>

### LLMs & Generative AI
<p>
  <img src="https://img.shields.io/badge/Claude_(Anthropic)-D97757?style=for-the-badge&logo=anthropic&logoColor=white" alt="Claude"/>
  <img src="https://img.shields.io/badge/Gemini-4285F4?style=for-the-badge&logo=google&logoColor=white" alt="Gemini"/>
  <img src="https://img.shields.io/badge/OpenAI_GPT--4-412991?style=for-the-badge&logo=openai&logoColor=white" alt="GPT-4"/>
  <img src="https://img.shields.io/badge/Llama_3-0467DF?style=for-the-badge&logo=meta&logoColor=white" alt="Llama 3"/>
  <img src="https://img.shields.io/badge/Qwen3-FF6A00?style=for-the-badge&logo=alibabadotcom&logoColor=white" alt="Qwen3"/>
  <img src="https://img.shields.io/badge/Mistral-FF7000?style=for-the-badge&logo=mistral&logoColor=white" alt="Mistral"/>
  <img src="https://img.shields.io/badge/Gemma-34A853?style=for-the-badge&logo=google&logoColor=white" alt="Gemma"/>
  <img src="https://img.shields.io/badge/Ollama-000000?style=for-the-badge&logo=ollama&logoColor=white" alt="Ollama"/>
  <img src="https://img.shields.io/badge/LM_Studio-6C5CE7?style=for-the-badge&logo=lmstudio&logoColor=white" alt="LM Studio"/>
  <img src="https://img.shields.io/badge/vLLM-FF4B4B?style=for-the-badge&logo=lightning&logoColor=white" alt="vLLM"/>
</p>

### Backend & Databases
<p>
  <a href="https://skillicons.dev">
    <img src="https://skillicons.dev/icons?i=fastapi,nodejs,redis" />
  </a>
  <img src="https://img.shields.io/badge/Milvus-00A1EA?style=for-the-badge&logo=milvus&logoColor=white" alt="Milvus"/>
  <img src="https://img.shields.io/badge/Next.js-000000?style=for-the-badge&logo=nextdotjs&logoColor=white" alt="Next.js"/>
</p>

### Cloud & DevOps
<p>
  <a href="https://skillicons.dev">
    <img src="https://skillicons.dev/icons?i=aws,gcp,docker,linux,git,github" />
  </a>
  <img src="https://img.shields.io/badge/AWS_SageMaker-FF9900?style=for-the-badge&logo=amazonaws&logoColor=white" alt="SageMaker"/>
  <img src="https://img.shields.io/badge/Google_Colab-F9AB00?style=for-the-badge&logo=googlecolab&logoColor=white" alt="Colab"/>
  <img src="https://img.shields.io/badge/TensorBoard-FF6F00?style=for-the-badge&logo=tensorflow&logoColor=white" alt="TensorBoard"/>
  <img src="https://img.shields.io/badge/CVAT-0D6EFD?style=for-the-badge&logo=opencv&logoColor=white" alt="CVAT"/>
</p>

### Design & Development Tools
<p>
  <a href="https://skillicons.dev">
    <img src="https://skillicons.dev/icons?i=figma,ps,ai,pr,ae,xd,latex,vscode,raspberrypi" />
  </a>
  <img src="https://img.shields.io/badge/Canva-00C4CC?style=for-the-badge&logo=canva&logoColor=white" alt="Canva"/>
  <img src="https://img.shields.io/badge/AutoCAD-F29B0C?style=for-the-badge&logo=autodesk&logoColor=white" alt="AutoCAD"/>
</p>

---

## :man_technologist: Who am I?

```python
class WhoAmI:
    user = 'Vicio Di Cara'
    role = 'AI / ML Engineer'
    based_in = 'Palermo, Italy'
    birth_fact = 'The first internet ping in Italy coincides with my birth'

    studying = 'MSc in Applied Data Science & AI @ OPIT'

    ai_portfolio = [
        "🥇 Malaria AI Scope: YOLOv11 segmentation, 1st Place AWS University Engagement Program",
        "🥈 Sherpa Alzheimer: multi-agent RAG chatbot, 2nd Place OPIT Hackathon 2026",
        "🤟 LisAI Interpreter: real-time LIS recognition (MLP/CNN letters 87.3%, Bi-LSTM/Transformer words)",
        "✅ Mental D0C: Qwen3 fine-tuned for mental health assessment (Unsloth)",
        "✅ Drug Repositioning: Random Forest + K-means, 92% accuracy",
        "🚀 Building AI agents to help others",
    ]

    hobbies = [
        "Surfing",
        "Bouldering",
        "Coding for Good",
    ]

    def get_city():
        return "Palermo, Italy"

    def future_ambitions():
        return "To travel the world, programming to help others."
```

---

<p align="center">
  <a href="https://www.linkedin.com/in/viciodicara/"><img src="https://img.shields.io/badge/Let's_connect-LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn"/></a>
  <a href="mailto:vicio.dicara@gmail.com"><img src="https://img.shields.io/badge/Email-vicio.dicara@gmail.com-D14836?style=for-the-badge&logo=gmail&logoColor=white" alt="Email"/></a>
</p>
