<div align="center">

# Hi, I'm Duc Duy 👋

**Software Engineer · Lifelong Learner**  
*The landscape is vast and knowledge is infinite — driven by relentless curiosity and the joy of building.*

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=flat&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/duy-nguy%E1%BB%85n-%C4%91%E1%BB%A9c-14b785293/)
[![Email](https://img.shields.io/badge/Email-D14836?style=flat&logo=gmail&logoColor=white)](mailto:nguyenducduy25605@gmail.com)
[![GitHub](https://img.shields.io/badge/GitHub-Duckdiii-181717?style=flat&logo=github&logoColor=white)](https://github.com/Duckdiii)
[![Profile Views](https://komarev.com/ghpvc/?username=Duckdiii&label=Profile+Views&color=0e75b6&style=flat)](https://github.com/Duckdiii)

</div>

---

### 💡 About & How I Think

I'm a 3rd-year Software Engineering student at **HCMUTE**, driven by a deep curiosity for computing and the craft of engineering dependable software.

* 🏛️ **System Craftsmanship:** Focused on backend fundamentals—understanding data flow, software architecture, security, and the trade-offs that make systems resilient and maintainable.
* 🧠 **Applied Intelligence:** Passionate about connecting software with modern AI, moving beyond the surface to engineer context-aware, high-precision retrieval systems.
* 🌌 **Infinite Curiosity:** Guided by the belief that knowledge has no ceiling. I actively seek out hard problems, embrace the steep learning curves, and continuously explore emerging concepts.

---

## 🚀 Featured Projects

### 🛍️ [TechStore — Tech Gadget E-commerce Platform](https://github.com/Duckdiii/Tech-Gadget-Store)
Full-stack retail platform (phones, laptops, monitors...) with three separate roles (customer / staff / manager) and a standalone ML microservice for product recommendations.
- **3-layer recommendation system** — content-based, co-occurrence, and Matrix Factorization (ALS) — with a **live A/B test** (MF vs. rule-based) tracked via CTR, so the model's real-world lift is measured, not assumed
- **AI chatbot + natural-language search** via Gemini function calling, streamed to the client over WebSocket
- Async order processing through **RabbitMQ** (with dead-letter queues), **Redis** for rate-limiting/caching, and a Correlation-ID tracing filter propagated across services and queue consumers
- **550+ automated tests** — JUnit 5/Mockito/Testcontainers (backend) + Vitest/RTL (frontend) — plus Playwright E2E and k6 load tests, running through a full CI/CD pipeline to isolated Staging/Production environments (Railway + Vercel)

`Java 21` `Spring Boot 4` `PostgreSQL` `Redis` `RabbitMQ` `React 19` `Python (ML)`

---

### ⚖️ [LawVN Education Assistant](https://github.com/Duckdiii/lawvn-education-assistant)
Vietnamese-language RAG chatbot for looking up education-sector legal documents, built to minimize hallucination and always cite the source article.
- **Hybrid retrieval** (BAAI/bge-m3 dense search + BM25) fused with **RRF**, then re-ranked with a cross-encoder
- **CRAG grader** scores retrieved context (0–3); low-quality context automatically falls back to Tavily web search instead of answering from a weak context
- Answers streamed in real time to the client via **Server-Sent Events**
- Indexes **8,948 chunks** from 100+ official MOET (Ministry of Education and Training) legal documents

`Python` `FastAPI` `Qdrant` `Gemini 2.0 Flash` `RAGAS` `React + Vite`

---

### 🧬 [Missing Person Search via FADING](https://github.com/Duckdiii/NCKH-Searching-for-Missing-Persons-Using-Generative-Image-Models) *(NCKH — scientific research project)*
Generates age-progressed versions of a single old photo and searches for identity matches, so a person who went missing years ago can still be recognized despite major appearance change.
- 5-stage pipeline: FFHQ face alignment → Stable Diffusion specialization (double-prompt fine-tuning) → Null-text Inversion → cross-attention age editing (FADING, BMVC 2023) → InsightFace embedding + FAISS similarity search
- Add-on layers for production-style robustness: multi-age-checkpoint ensembling, confidence-based rejection threshold, and image-quality warnings (pose/yaw checks)
- Quantitatively evaluated on the **FG-NET** benchmark (ID Score / Age MAE across 230 pairs, 82 identities)

`Python` `PyTorch` `Diffusers (Stable Diffusion)` `InsightFace` `FAISS` `Streamlit`

---

### 🧠 [Brain Tumor Classification](https://github.com/Duckdiii/NCKH-brain-tumor-classifier) *(NCKH — scientific research project)*
Benchmarks 4 deep learning architectures on classifying brain MRI scans into 4 tumor classes (glioma, meningioma, pituitary, no tumor).
- Compared **CNN, ViT, YOLOv8-cls, YOLOv11-cls** on 7,023 MRI images — **YOLOv8 best at 99.57% accuracy**, with full precision/recall/F1/inference-speed/model-size trade-off analysis
- Refactored the original one-file research script into a config-driven, testable `src`-layout Python package (config separated from code, training logic decoupled from the Streamlit UI)
- End-to-end tooling: dataset splitting/validation scripts, CLI training/evaluation, Streamlit comparison demo, pretrained weights published on Hugging Face Hub

`Python` `PyTorch` `timm (ViT)` `Ultralytics YOLO` `Streamlit`

---

## 🛠️ Tech Stack & Tooling

<div align="center">

| Domain | Technologies & Frameworks | Highlights / Applied Scope |
| :--- | :--- | :--- |
| **Backend & Architecture** | Java 17+, Spring Boot 3.x/4 (MVC, Security, Data JPA/Hibernate, WebSocket + STOMP), Python, FastAPI, C# / ASP.NET Core *(learning)* | Layered/OOP architecture, JWT/RBAC auth, RESTful APIs, real-time features, RabbitMQ, Redis |
| **AI / RAG Engineering** | LangChain / LangChain4j, Qdrant, pgvector, RAGAS, Gemini API (function calling & structured output) | Hybrid retrieval (dense BGE-M3 + BM25 via RRF), CRAG & Adaptive RAG, cross-encoder reranking, RAG evaluation |
| **Computer Vision** | CLIP, FAISS, InsightFace/ArcFace, Stable Diffusion (Diffusers), YOLO, OpenCV, ViT/CNN | Multimodal video retrieval, face-aging identity search, medical image classification |
| **Databases & Storage** | PostgreSQL (Supabase), MySQL, Qdrant, pgvector | Relational schema design, JPA inheritance strategies (`JOINED` / `SINGLE_TABLE`), vector search |
| **Frontend & Mobile** | React, TypeScript, JavaScript, Android (Java, Jetpack Compose/XML) | Role-based UI workflows, REST API consumption, human-in-the-loop interfaces, native mobile apps |
| **DevOps & Engineering Tools** | Docker, Git/GitHub, Postman, JUnit5/Mockito/Testcontainers, Vitest, Render/Vercel | Containerization, automated testing, API design & documentation, deployment |

<br/>

<!-- Stack Icons Grid -->
<p align="center">
  <img src="https://skillicons.dev/icons?i=java,spring,cs,dotnet,python,fastapi,react,ts,postgres,mysql,androidstudio,docker,git" alt="Tech Stack Icons" />
</p>

</div>

---

## 📊 GitHub Insights

<div align="center">

<img height="165" src="https://github-readme-stats.vercel.app/api?username=Duckdiii&show_icons=true&theme=tokyonight&hide_border=true&count_private=true" />
<img height="165" src="https://github-readme-stats.vercel.app/api/top-langs/?username=Duckdiii&layout=compact&theme=tokyonight&hide_border=true" />

<br/>

[![GitHub Streak](https://streak-stats.demolab.com?user=Duckdiii&theme=tokyonight&hide_border=true)](https://git.io/streak-stats)

</div>

---

<div align="center">
  <sub>"Học đi đôi với hành — Building systems that solve real problems."</sub>
</div>
