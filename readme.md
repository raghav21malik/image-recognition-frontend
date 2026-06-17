<div align="center">

<img src="https://img.shields.io/badge/VisionCloud-AI%20Vision%20Platform-4F46E5?style=for-the-badge&logoColor=white" height="40"/>

# VisionCloud

**Cloud-Native Multi-Model AI Vision Platform**

*Upload an image. Benchmark 5 AI architectures. Explore your scan history — all in one platform.*

[![Live Demo](https://img.shields.io/badge/🌐%20Live%20Demo-Visit%20App-4F46E5?style=for-the-badge)](https://raghav21malik.github.io/image-recognition-frontend/)
[![Architecture](https://img.shields.io/badge/🏗️%20Architecture-View%20Diagram-0EA5E9?style=for-the-badge)](https://raghav21malik.github.io/image-recognition-frontend/architecture.html)
[![Backend Repo](https://img.shields.io/badge/⚙️%20Backend-Flask%20API-000000?style=for-the-badge&logo=github)](https://github.com/raghav21malik/image-recognition-backend)

<br/>

![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![Flask](https://img.shields.io/badge/Flask-000000?style=flat&logo=flask&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat&logo=javascript&logoColor=black)
![PostgreSQL](https://img.shields.io/badge/Supabase-3ECF8E?style=flat&logo=supabase&logoColor=white)
![Cloudinary](https://img.shields.io/badge/Cloudinary-3448C5?style=flat&logo=cloudinary&logoColor=white)
![HuggingFace](https://img.shields.io/badge/🤗%20Hugging%20Face-FFD21E?style=flat&logoColor=black)
![GitHub Pages](https://img.shields.io/badge/GitHub%20Pages-181717?style=flat&logo=github&logoColor=white)
![Render](https://img.shields.io/badge/Render-46E3B7?style=flat&logo=render&logoColor=black)

</div>

---

## 📸 What Is VisionCloud?

VisionCloud is a **production-deployed, full-stack AI platform** that lets users upload images and instantly benchmark them across **5 state-of-the-art computer vision models** — seeing real confidence scores and inference times side by side.

It's not a tutorial project. It integrates **real cloud infrastructure**: Supabase for auth + database, Cloudinary CDN for image storage, Hugging Face Inference API for ML inference, and a Flask REST API deployed on Render — all wired together into a seamless user experience.

> **Built to demonstrate:** Full-stack engineering · REST API design · Cloud service integration · Auth systems · AI model benchmarking

---

## 🌟 Core Features

### 🤖 Multi-Model AI Benchmarking *(the main event)*
Compare 5 production-grade vision architectures **simultaneously** on any image you upload:

| Model | Architecture | Strength |
|-------|-------------|----------|
| **ViT-Base/16** | Vision Transformer | Global attention, strong on complex scenes |
| **ResNet-50** | Residual Network | Battle-tested baseline, fast inference |
| **MobileNet-V2** | Depthwise Separable CNN | Lightest model, optimized for mobile/edge |
| **Swin-Tiny** | Shifted Window Transformer | Efficient hierarchical attention |
| **DeiT-Base** | Knowledge Distillation Transformer | Data-efficient, distilled from CNN teacher |

Each run surfaces: **top label · confidence score · inference time · fastest model · highest confidence model**

---

### 🔐 Auth & User Accounts
- Secure registration + login via **Supabase Auth**
- JWT-based session management
- Every scan is tied to your account — private history, not shared

### 📊 Analytics Dashboard
- Scans per day trend chart
- Top detected labels across your history
- Activity timeline
- Usage statistics — all rendered client-side from your personal scan data

### 🔍 Semantic Label Search
Search your past scans by **what the AI detected** — not just filenames. Find every image where the model saw "golden retriever" or "sports car" instantly.

### ☁️ Cloud Image Storage
Images are stored and served via **Cloudinary CDN** — optimized delivery, no server disk usage, persistent across deployments.

---

## 🏗️ System Architecture

```
┌─────────────────────────────────────────────────────────────┐
│                        USER BROWSER                          │
│           HTML5 · CSS3 · Vanilla JavaScript                  │
│              Hosted on GitHub Pages (CDN)                    │
└────────────────────────┬────────────────────────────────────┘
                         │ HTTPS REST API calls
                         ▼
┌─────────────────────────────────────────────────────────────┐
│                   FLASK REST API                             │
│                  Python · Render.com                         │
│                                                              │
│  /auth       → Supabase Auth (JWT issue + validation)        │
│  /upload     → Cloudinary (image store) + DB record          │
│  /classify   → Hugging Face Inference API (5 models)         │
│  /history    → Supabase PostgreSQL (user scan records)       │
│  /analytics  → Supabase PostgreSQL (aggregated stats)        │
└──────┬────────────────┬──────────────────┬──────────────────┘
       │                │                  │
       ▼                ▼                  ▼
┌────────────┐  ┌──────────────┐  ┌──────────────────────┐
│  Supabase  │  │  Cloudinary  │  │   Hugging Face API   │
│ Auth + DB  │  │  CDN Storage │  │  5 Vision Models     │
│ PostgreSQL │  │ Optimized    │  │  ViT · ResNet ·      │
│            │  │ Image Serve  │  │  MobileNet-V2 ·      │
└────────────┘  └──────────────┘  │  Swin-Tiny · DeiT    │
                                   └──────────────────────┘
```

**Why this architecture?**
- **Stateless API** — Flask holds no session state; JWT tokens handle auth. Horizontally scalable.
- **CDN-first storage** — Images never sit on the API server. Cloudinary handles delivery globally.
- **Inference via API** — No GPU required on the server. Hugging Face manages model serving.
- **Managed database** — Supabase PostgreSQL with Row Level Security; no DB server to maintain.

---

## 🛠️ Full Tech Stack

| Layer | Technology | Why This Choice |
|-------|-----------|----------------|
| **Frontend** | HTML5, CSS3, Vanilla JS | Zero framework overhead; fast load on GitHub Pages |
| **Backend** | Python Flask | Lightweight REST API; easy Hugging Face SDK integration |
| **Authentication** | Supabase Auth | Production-grade JWT auth without building it from scratch |
| **Database** | Supabase PostgreSQL | Managed Postgres with built-in Row Level Security |
| **AI Inference** | Hugging Face Inference API | Access to 5 SOTA models without GPU infrastructure |
| **Image Storage** | Cloudinary CDN | Automatic optimization, global CDN, no disk usage |
| **Frontend Host** | GitHub Pages | Free static hosting, instant deploys on push |
| **Backend Host** | Render | Auto-deploy from GitHub, free tier, HTTPS out of the box |

---

## 🚀 Getting Started (Local Development)

### Prerequisites
- Python 3.9+
- A free [Supabase](https://supabase.com) account
- A free [Cloudinary](https://cloudinary.com) account
- A free [Hugging Face](https://huggingface.co) account (for the Inference API token)

### 1. Clone the repositories

```bash
# Backend
git clone https://github.com/raghav21malik/image-recognition-backend.git
cd image-recognition-backend

# Frontend (separate repo)
git clone https://github.com/raghav21malik/image-recognition-frontend.git
```

### 2. Set up the backend

```bash
cd image-recognition-backend
python -m venv venv
source venv/bin/activate        # Windows: venv\Scripts\activate
pip install -r requirements.txt
```

### 3. Configure environment variables

Create a `.env` file in the backend root:

```env
# Supabase
SUPABASE_URL=your_supabase_project_url
SUPABASE_KEY=your_supabase_anon_key

# Cloudinary
CLOUDINARY_CLOUD_NAME=your_cloud_name
CLOUDINARY_API_KEY=your_api_key
CLOUDINARY_API_SECRET=your_api_secret

# Hugging Face
HF_API_TOKEN=your_huggingface_token

# Flask
SECRET_KEY=your_flask_secret_key
FLASK_ENV=development
```

### 4. Run the backend

```bash
flask run
# API will be live at http://localhost:5000
```

### 5. Open the frontend

```bash
cd image-recognition-frontend
# Open index.html in your browser, or use Live Server in VS Code
```

---

## 📡 API Endpoints

| Method | Endpoint | Description | Auth Required |
|--------|----------|-------------|:---:|
| `GET` | `/` | Health check — API status | ❌ |
| `POST` | `/api/upload` | Upload image → Cloudinary + AI classify + save to DB | Optional |
| `GET` | `/api/history` | Fetch scan history (filtered by user if authenticated) | Optional |
| `POST` | `/api/benchmark` | Run all 5 models in parallel on an image URL | ❌ |
| `GET` | `/api/models` | Get all model info for frontend display | ❌ |

---

## 🎯 Engineering Decisions Worth Noting

**Benchmarking 5 models in parallel** — API calls to Hugging Face are made concurrently (not sequentially) to minimize total inference wait time.

**JWT stateless auth** — No server-side sessions. The Flask API is fully stateless; any instance can serve any request, making it deploy-friendly.

**Vanilla JS on the frontend** — No React, no build step, no `node_modules`. The frontend deploys as static files to GitHub Pages with zero CI configuration.

**Row Level Security on Supabase** — Each user can only query their own scan records, enforced at the database layer — not just the API layer.

---

## 📁 Repository Structure

```
image-recognition-backend/
├── app.py                  # Flask app entry + blueprint registration
├── upload.py               # /api/upload — Cloudinary + HuggingFace + Supabase
├── benchmark.py            # /api/benchmark — 5-model parallel inference
├── history.py              # /api/history — user scan records from Supabase
├── requirements.txt        # Python dependencies
├── render.yaml             # Render deployment config
└── .env.example            # Environment variables template

image-recognition-frontend/
├── index.html              # Main app (Analyze, History, Analytics, Benchmark)
├── auth.html               # Authentication page (login/register)
├── architecture.html       # Architecture & project details page
├── readme.html             # README documentation page
├── readme.md               # GitHub README
├── style.css               # All styles (~100KB)
└── script.js               # All JavaScript logic (~85KB)
```

---

## 🔮 Roadmap

- [ ] Export scan history as CSV
- [ ] Compare any two scans side-by-side
- [ ] Add object detection models (YOLO, DETR)
- [ ] Containerize backend with Docker for self-hosting
- [ ] Add image segmentation support

---

## 📚 Research Background

These five models were chosen to represent the **full architectural spectrum** of modern computer vision — from pioneering CNNs to cutting-edge Transformers.

### Paper Citations

| Model | Paper | Venue | Year | Top-1 Acc | Params |
|-------|-------|-------|:----:|:---------:|:------:|
| **ViT-Base/16** | *An Image is Worth 16×16 Words* | ICLR 2021 | 2020 | 85.8% | 86M |
| **ResNet-50** | *Deep Residual Learning for Image Recognition* | CVPR 2016 | 2015 | 80.8% | 25M |
| **MobileNet-V2** | *MobileNetV2: Inverted Residuals and Linear Bottlenecks* | CVPR 2018 | 2018 | 71.8% | 3.4M |
| **Swin-Tiny** | *Swin Transformer: Hierarchical Vision Transformer using Shifted Windows* | ICCV 2021 | 2021 | 81.3% | 28M |
| **DeiT-Base** | *Training Data-Efficient Image Transformers & Distillation through Attention* | ICML 2021 | 2020 | 83.4% | 86M |

### Why These 5 Architectures?

The selection spans the full evolution of visual AI:

- **ResNet-50** (2015) — The CNN that proved depth matters. Skip connections solved vanishing gradients, enabling 100+ layer networks.
- **MobileNet-V2** (2018) — Proved that competitive accuracy is possible with 8× fewer parameters using depthwise separable convolutions. Critical for edge/mobile deployment.
- **ViT-Base** (2020) — The paradigm shift. First pure Transformer applied to vision, treating image patches as tokens with global self-attention.
- **DeiT-Base** (2020) — Solved ViT's data hunger through knowledge distillation from a CNN teacher, making Transformers practical without massive pretraining datasets.
- **Swin-Tiny** (2021) — Made Transformers efficient with shifted window attention (linear complexity), producing hierarchical features like CNNs.

By benchmarking across all five, VisionCloud reveals how each architectural paradigm handles different visual inputs — demonstrating that no single architecture dominates across all image types.

---

## 👨‍💻 Author

**Raghav Malik**
B.Tech Computer Science Engineering · UPES Dehradun (2023–2027)

[![Email](https://img.shields.io/badge/Email-D14836?style=flat&logo=gmail&logoColor=white)](mailto:Malikraghav873@gmail.com)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=flat&logo=linkedin&logoColor=white)](https://linkedin.com/in/raghav21malik)
[![GitHub](https://img.shields.io/badge/GitHub-181717?style=flat&logo=github&logoColor=white)](https://github.com/raghav21malik)

---

<div align="center">

*VisionCloud — built to learn, designed to impress.*

⭐ If you found this useful, a star on the repo goes a long way!

</div>
