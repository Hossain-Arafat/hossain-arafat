<p align="center">
  <img src="./assets/header-1.svg" alt="Arafat Hossain, AI/ML engineer" width="100%" />
</p>

<p align="center">
  <a href="https://www.linkedin.com/in/arafathossain-cs/"><img src="https://img.shields.io/badge/LinkedIn-1B2533?style=flat-square&logo=linkedin&logoColor=E8A33D" alt="LinkedIn" /></a>
  <a href="mailto:ar.hossain1303@gmail.com"><img src="https://img.shields.io/badge/Email-1B2533?style=flat-square&logo=maildotru&logoColor=E8A33D" alt="Email" /></a>
  <a href="https://github.com/Hossain-Arafat?tab=repositories"><img src="https://img.shields.io/badge/Repositories-1B2533?style=flat-square&logo=github&logoColor=E8A33D" alt="Repositories" /></a>
  <!-- Portfolio: uncomment and drop your URL in when the site is live
  <a href="YOUR_PORTFOLIO_URL"><img src="https://img.shields.io/badge/Portfolio-1B2533?style=flat-square&logo=googlechrome&logoColor=E8A33D" alt="Portfolio" /></a>
  -->
</p>

## Selected work

### LegalEase BD

<p>
  <img src="https://img.shields.io/badge/LLM-LLaMA--3.3--70B-E8A33D?style=flat-square&labelColor=131A24" />
  <img src="https://img.shields.io/badge/Retrieval-Hybrid%20RAG-E8A33D?style=flat-square&labelColor=131A24" />
  <img src="https://img.shields.io/badge/Corpus-35%2C472%20chunks-4FB3A5?style=flat-square&labelColor=131A24" />
  <img src="https://img.shields.io/badge/Deploy-Modal%20serverless-4FB3A5?style=flat-square&labelColor=131A24" />
</p>

- Bilingual legal assistant answering questions on Bangladeshi law in Bangla or English, cited to Act and Section
- Hybrid retrieval over 35,472 statute chunks: BM25 and ChromaDB run in parallel, merged by Reciprocal Rank Fusion, so casual Bangla still reaches formal legal wording
- Seven stage pipeline: language detection, intent classification, anti hallucination prompting, citation extraction
- FastAPI on Modal serverless GPU with a React frontend, 1 to 2s warm latency at near zero idle cost

<details>
<summary><b>Pipeline</b></summary>
  
```mermaid
flowchart LR
  Q["Question<br/>বাংলা / English"] --> N["Normalize<br/>+ detect language"]
  N --> D["Dense retrieval<br/>ChromaDB"]
  N --> S["Sparse retrieval<br/>BM25"]
  D --> F["Reciprocal<br/>Rank Fusion"]
  S --> F
  F --> C["Top-k chunks<br/>from 35,472"]
  C --> L["LLaMA-3.3-70B<br/>on Groq"]
  L --> A["Answer<br/>+ citations<br/>+ confidence"]
```
</details>

**Stack:** `Python` · `FastAPI` · `Modal` · `Groq` · `ChromaDB` · `Sentence-Transformers` · `BM25` · `LangChain` · `React` · `Vite`

**Repo:** [LegalEase-BD](https://github.com/Hossain-Arafat/LegalEase-BD)

### DeepAttend

<p>
  <img src="https://img.shields.io/badge/Model-MobileNetV2-E8A33D?style=flat-square&labelColor=131A24" />
  <img src="https://img.shields.io/badge/Task-Face%20Recognition-E8A33D?style=flat-square&labelColor=131A24" />
  <img src="https://img.shields.io/badge/Enrolled-50%2B%20people-4FB3A5?style=flat-square&labelColor=131A24" />
  <img src="https://img.shields.io/badge/Runs%20on-CPU-4FB3A5?style=flat-square&labelColor=131A24" />
</p>

- Real time webcam attendance built for ordinary classroom hardware, no GPU
- MobileNetV2 fine tuned by transfer learning to recognise 50+ enrolled people
- Confidence threshold plus a stability window across frames, so no single frame can trigger a match
- Session safe CSV logging, one record per person however often they pass the camera

<details>
<summary><b>Pipeline</b></summary>

```mermaid
flowchart LR
  V["Camera frame"] --> DT["Face detection<br/>OpenCV"]
  DT --> AL["Crop + align"]
  AL --> EM["MobileNetV2<br/>embedding"]
  EM --> MT["Match against<br/>enrolled set"]
  MT --> TH{"Confident<br/>+ stable?"}
  TH -->|yes| LG["Log once<br/>per session"]
  TH -->|no| RJ["Hold as unknown"]
```
</details>

**Stack:** `Python` · `TensorFlow` · `Keras` · `OpenCV` · `MobileNetV2` · `Tkinter`

**Repo:** [deepattend-face-recognition](https://github.com/Hossain-Arafat/deepattend-face-recognition)

### PizzaGo

<p>
  <img src="https://img.shields.io/badge/Architecture-MVC-E8A33D?style=flat-square&labelColor=131A24" />
  <img src="https://img.shields.io/badge/Backend-PHP-E8A33D?style=flat-square&labelColor=131A24" />
  <img src="https://img.shields.io/badge/Database-MySQL-4FB3A5?style=flat-square&labelColor=131A24" />
  <img src="https://img.shields.io/badge/Roles-Customer%20%7C%20Staff%20%7C%20Admin-4FB3A5?style=flat-square&labelColor=131A24" />
</p>

- Full stack PHP ordering platform on MVC, with separate controllers for auth, cart, orders, and inventory
- Three roles with their own dashboards, including live order status
- Normalised MySQL schema with cascading foreign keys, so deletes leave no orphaned rows

**Stack:** `PHP` · `MySQL` · `JavaScript` · `HTML` · `CSS` · `Apache`

**Repo:** [PizzaGo](https://github.com/Hossain-Arafat/PizzaGo)

## Tools

<p>
  <img src="https://img.shields.io/badge/Python-1B2533?style=flat-square&logo=python&logoColor=4FB3A5" />
  <img src="https://img.shields.io/badge/PyTorch-1B2533?style=flat-square&logo=pytorch&logoColor=4FB3A5" />
  <img src="https://img.shields.io/badge/TensorFlow-1B2533?style=flat-square&logo=tensorflow&logoColor=4FB3A5" />
  <img src="https://img.shields.io/badge/Keras-1B2533?style=flat-square&logo=keras&logoColor=4FB3A5" />
  <img src="https://img.shields.io/badge/scikit--learn-1B2533?style=flat-square&logo=scikitlearn&logoColor=4FB3A5" />
  <img src="https://img.shields.io/badge/OpenCV-1B2533?style=flat-square&logo=opencv&logoColor=4FB3A5" />
  <img src="https://img.shields.io/badge/Hugging%20Face-1B2533?style=flat-square&logo=huggingface&logoColor=4FB3A5" />
  <br>
  <img src="https://img.shields.io/badge/LangChain-1B2533?style=flat-square&logo=langchain&logoColor=4FB3A5" />
  <img src="https://img.shields.io/badge/ChromaDB-1B2533?style=flat-square&logo=chromatic&logoColor=4FB3A5" />
  <img src="https://img.shields.io/badge/FastAPI-1B2533?style=flat-square&logo=fastapi&logoColor=4FB3A5" />
  <img src="https://img.shields.io/badge/Docker-1B2533?style=flat-square&logo=docker&logoColor=4FB3A5" />
  <img src="https://img.shields.io/badge/Modal-1B2533?style=flat-square&logo=modal&logoColor=4FB3A5" />
  <img src="https://img.shields.io/badge/Git-1B2533?style=flat-square&logo=git&logoColor=4FB3A5" />
  <img src="https://img.shields.io/badge/Linux-1B2533?style=flat-square&logo=linux&logoColor=4FB3A5" />
</p>

<details>
<summary><b>Everything else</b></summary>

<br>

| | |
|---|---|
| **Languages** | Python, C++, C#, SQL, JavaScript, PHP |
| **NLP and retrieval** | Sentence-Transformers, BM25, Groq API, Reciprocal Rank Fusion |
| **Data** | NumPy, Pandas, Matplotlib, Seaborn, Jupyter |
| **Web** | React, Vite, Tailwind, REST APIs, HTML, CSS, Apache |
| **Demos and serving** | Gradio, Streamlit, Modal, Docker |
| **Databases** | MySQL, SQL Server, ADO.NET |

</details>

<br>

---

<p align="center">
  <sub>Open to AI/ML engineering roles and research collaboration. <a href="mailto:ar.hossain1303@gmail.com">get in touch</a></sub>
</p>
