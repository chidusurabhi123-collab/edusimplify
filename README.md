# EduSimplify AI — Powered by IBM Bob

Adaptive educational content simplification using **IBM watsonx.ai** and the **IBM Granite** foundation model.

---

## How to Run

```bash
cd edusimplify
npm install
npm start
```

Then open **http://localhost:3000**

---

## Configuration

Copy `env.example` to `.env` and fill in your values:

```
IBM_WATSONX_API_KEY=your_ibm_cloud_api_key
IBM_WATSONX_PROJECT_ID=your_watsonx_project_id
IBM_WATSONX_REGION=us-south
PORT=3000
```

### Getting your credentials

| Value | Where to get it |
|---|---|
| `IBM_WATSONX_API_KEY` | IBM Cloud → Manage → Access → API Keys |
| `IBM_WATSONX_PROJECT_ID` | watsonx.ai → Your project → Manage → General → Project ID |
| `IBM_WATSONX_REGION` | `us-south` (default), `eu-de`, or `jp-tok` |

---

## Architecture

```
Browser (index.html)
    │  POST /api/simplify  { api_key, student_level, … }
    ▼
Express server (server.js)
    │  POST iam.cloud.ibm.com  → Bearer token
    │  POST us-south.ml.cloud.ibm.com/ml/v1/text/generation
    │  model: ibm/granite-3-8b-instruct
    ▼
JSON response → rendered in browser
```

---

## Features

| | |
|---|---|
| 💡 | Simplified Explanation |
| 🔑 | Key Concepts |
| 📖 | Important Terms glossary |
| 🌍 | Real-World Analogy |
| 📋 | Step-by-Step breakdown |
| 💻 | Worked Example |
| ⚠️ | Common Mistakes |
| 🎯 | Exam-Ready Summary |
| 📝 | 5 Practice Questions with difficulty ratings |

---

## Project Structure

```
edusimplify/
├── server.js        ← Express + IBM watsonx.ai integration
├── public/
│   └── index.html   ← IBM Carbon Design UI
├── .env             ← Your credentials (never commit)
├── env.example      ← Template
└── README.md
```
