<div align="center">

```
██████╗ ██████╗ ██╗ ██████╗███████╗    ██╗ ██████╗
██╔══██╗██╔══██╗██║██╔════╝██╔════╝    ██║██╔═══██╗
██████╔╝██████╔╝██║██║     █████╗      ██║██║   ██║
██╔═══╝ ██╔══██╗██║██║     ██╔══╝      ██║██║▄▄ ██║
██║     ██║  ██║██║╚██████╗███████╗    ██║╚██████╔╝
╚═╝     ╚═╝  ╚═╝╚═╝ ╚═════╝╚══════╝   ╚═╝ ╚══▀▀═╝
```

### *Intelligent Dynamic Pricing at the Speed of Demand*

<br/>

[![React](https://img.shields.io/badge/React_18-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)](https://react.dev/)
[![TypeScript](https://img.shields.io/badge/TypeScript-007ACC?style=for-the-badge&logo=typescript&logoColor=white)](https://www.typescriptlang.org/)
[![Node.js](https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=nodedotjs&logoColor=white)](https://nodejs.org/)
[![Python](https://img.shields.io/badge/Python-FFD43B?style=for-the-badge&logo=python&logoColor=blue)](https://python.org/)
[![FastAPI](https://img.shields.io/badge/FastAPI-005571?style=for-the-badge&logo=fastapi)](https://fastapi.tiangolo.com/)
[![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=for-the-badge&logo=pytorch&logoColor=white)](https://pytorch.org/)
[![MongoDB](https://img.shields.io/badge/MongoDB-4EA94B?style=for-the-badge&logo=mongodb&logoColor=white)](https://www.mongodb.com/)
[![Redis](https://img.shields.io/badge/Redis-DC382D?style=for-the-badge&logo=redis&logoColor=white)](https://redis.io/)

<br/>

> **PriceIQ** is a full-stack, AI-powered dynamic pricing platform that combines real-time clickstream analytics, deep-learning recommendations, and an intelligent chat assistant to maximize revenue through demand-aware pricing strategies.

<br/>

</div>

---

## 📐 Architecture Overview

```
┌─────────────────────────────────────────────────────────────────────┐
│                        CLIENT LAYER                                  │
│                                                                       │
│   ┌───────────────────────┐      ┌──────────────────────────────┐   │
│   │   Retail Storefront   │      │     Analytics Dashboard      │   │
│   │  React 18 + Vite      │      │   Recharts · TanStack Query  │   │
│   └───────────┬───────────┘      └──────────────┬───────────────┘   │
└───────────────┼──────────────────────────────────┼───────────────────┘
                │         REST + WebSocket          │
┌───────────────┼──────────────────────────────────┼───────────────────┐
│               │         BACKEND LAYER             │                   │
│   ┌───────────▼──────────────────────────────────▼───────────────┐   │
│   │               Express.js API  (Node.js ES Modules)           │   │
│   │         JWT Auth · Passport OAuth · Groq AI Chat             │   │
│   └──────────────┬────────────────────────┬──────────────────────┘   │
│                  │                        │                           │
│   ┌──────────────▼────────┐  ┌────────────▼──────────────────────┐   │
│   │  MongoDB (Mongoose)   │  │   Redis (ioredis)                 │   │
│   │  Products · Users     │  │   Streams · Demand Cache          │   │
│   │  Sessions · Events    │  │   Clickstream Pipeline            │   │
│   └───────────────────────┘  └───────────────────────────────────┘   │
└─────────────────────────────────┬─────────────────────────────────────┘
                                  │  Internal HTTP
┌─────────────────────────────────▼─────────────────────────────────────┐
│                          ML SERVICE LAYER                              │
│                                                                        │
│   ┌─────────────────────┐     ┌──────────────────────────────────┐    │
│   │   FastAPI Server    │     │  GRU4Rec (PyTorch)               │    │
│   │   Python Runtime    │────▶│  Session-Based Recommendations   │    │
│   └─────────────────────┘     └──────────────────────────────────┘    │
│                                                                        │
│   ┌───────────────────────────────────────────────────────────────┐   │
│   │  TF-IDF Fallback (Scikit-Learn) · Pandas · NumPy · PyMongo   │   │
│   └───────────────────────────────────────────────────────────────┘   │
└────────────────────────────────────────────────────────────────────────┘
```

---

## 🗂️ Table of Contents

- [Features](#-features)
- [Tech Stack](#-tech-stack)
  - [Frontend](#-frontend)
  - [Backend](#-backend)
  - [ML Service](#-ml-service)
- [Getting Started](#-getting-started)
- [Project Structure](#-project-structure)
- [Key Concepts](#-key-concepts)
- [Environment Variables](#-environment-variables)
- [Contributing](#-contributing)

---

## ✨ Features

| Feature | Description |
|---|---|
| 🧠 **AI-Powered Recommendations** | GRU4Rec deep learning model delivers session-aware product suggestions in real time |
| ⚡ **Real-Time Demand Sensing** | Redis Streams ingest raw clickstream events and compute live demand velocity |
| 💬 **AI Chat Assistant** | Groq-powered support chatbot embedded directly in the storefront |
| 📊 **A/B Testing Dashboard** | Live revenue and conversion visualizations via Recharts |
| 🔐 **Secure Auth** | JWT-based sessions with Google OAuth 2.0 via Passport.js |
| 🔄 **TF-IDF Fallback** | Scikit-Learn content-based filtering kicks in when deep learning signals are sparse |
| 🏎️ **High-Speed Caching** | Redis caches demand velocity scores for sub-millisecond pricing lookups |
| 📦 **Type-Safe Forms** | React Hook Form + Zod provide end-to-end validated, type-safe data flows |

---

## 🛠️ Tech Stack

### 🖥️ Frontend

> *Retail Storefront & Analytics Dashboard*

| Category | Technology | Purpose |
|---|---|---|
| **Core** | React 18 + TypeScript | Component model & type safety |
| **Build** | Vite | High-speed HMR & bundling |
| **Styling** | TailwindCSS | Utility-first CSS |
| **Components** | Shadcn UI | Accessible, composable UI library |
| **Icons** | Lucide React | Modern vector iconography |
| **Routing** | React Router DOM | Client-side navigation |
| **Server State** | TanStack Query (React Query) | Data fetching, caching & sync |
| **Visualization** | Recharts | A/B test & revenue dashboards |
| **Forms** | React Hook Form + Zod | Type-safe validation & submission |

---

### ⚙️ Backend

> *RESTful API & Real-Time Event Pipeline*

| Category | Technology | Purpose |
|---|---|---|
| **Runtime** | Node.js (ES Modules) | Server-side JavaScript environment |
| **Framework** | Express.js | RESTful API routing |
| **Primary DB** | MongoDB + Mongoose | Products, users, sessions & events |
| **Cache / Streams** | Redis + ioredis | Clickstream ingestion & demand caching |
| **Auth** | JWT + BcryptJS | Secure token-based authentication |
| **OAuth** | Passport.js | Google OAuth 2.0 integration |
| **AI Assistant** | Groq SDK | LLM-powered customer chat support |

#### 🔴 Redis — The Real-Time Engine

Redis sits at the heart of PriceIQ's real-time pipeline, serving two critical roles:

```
Clickstream Events ──▶  Redis Streams  ──▶  Demand Velocity Computation
                                                      │
Product Pricing Engine  ◀──  High-Speed Cache  ◀─────┘
```

- **Redis Streams** act as a durable, ordered log for raw clickstream events (views, add-to-carts, purchases).
- **Caching Layer** stores computed demand velocity scores so the pricing engine can respond in microseconds.

---

### 🤖 ML Service

> *Intelligence, Recommendations & Feature Engineering*

| Category | Technology | Purpose |
|---|---|---|
| **Serving** | FastAPI (Python) | High-performance async ML API |
| **Deep Learning** | PyTorch | GRU4Rec model training & inference |
| **Traditional ML** | Scikit-Learn | TF-IDF content-based fallback |
| **Feature Engineering** | Pandas + NumPy | Signal processing & feature computation |
| **DB Connection** | PyMongo | Direct access to MongoDB event store |
| **Model Ops** | Joblib | Model serialization & persistence |

#### 🧬 Recommendation Strategy

```
User Session Starts
       │
       ▼
  Enough Session Data?
  ┌────┴────┐
  │  YES    │  NO
  ▼         ▼
GRU4Rec   TF-IDF Content-Based Filtering
(PyTorch)  (Scikit-Learn)
  │         │
  └────┬────┘
       ▼
  Ranked Product List ──▶ Storefront
```

The **GRU4Rec** model (Gated Recurrent Unit for Recommendations) captures sequential patterns in a user's session to predict next likely purchases. When session data is sparse (cold-start), the system gracefully falls back to **TF-IDF cosine similarity** over product content features.

---

## 🚀 Getting Started

### Prerequisites

- **Node.js** `>= 18.x`
- **Python** `>= 3.10`
- **MongoDB** (local or Atlas)
- **Redis** `>= 7.x`

### 1. Clone the Repository

```bash
git clone https://github.com/your-org/priceiq.git
cd priceiq
```

### 2. Start the Frontend

```bash
cd frontend
npm install
npm run dev
```

### 3. Start the Backend

```bash
cd backend
npm install
npm run dev
```

### 4. Start the ML Service

```bash
cd ml-service
python -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate
pip install -r requirements.txt
uvicorn main:app --reload --port 8000
```

---

## 📁 Project Structure

```
priceiq/
│
├── frontend/                   # React 18 + Vite storefront & dashboard
│   ├── src/
│   │   ├── components/         # Shadcn UI + custom components
│   │   ├── pages/              # Route-level page components
│   │   ├── hooks/              # TanStack Query hooks & custom hooks
│   │   ├── lib/                # Zod schemas, utils, API clients
│   │   └── main.tsx            # App entry point
│   └── vite.config.ts
│
├── backend/                    # Express.js API + real-time pipeline
│   ├── src/
│   │   ├── routes/             # REST API endpoints
│   │   ├── models/             # Mongoose schemas
│   │   ├── middleware/         # JWT auth, error handling
│   │   ├── services/           # Redis stream consumers, Groq chat
│   │   └── index.js            # Server entry point
│   └── package.json
│
└── ml-service/                 # FastAPI ML inference service
    ├── models/                 # Saved PyTorch & Joblib model files
    ├── routers/                # FastAPI route handlers
    ├── training/               # GRU4Rec training scripts
    ├── utils/                  # Feature engineering (Pandas/NumPy)
    ├── main.py                 # FastAPI app entry point
    └── requirements.txt
```

---

## 💡 Key Concepts

### Dynamic Pricing Flow

```
1.  User browses storefront
        │
2.  Click events stream into Redis Streams (via backend)
        │
3.  Stream consumer computes demand velocity
        │
4.  Velocity score cached in Redis
        │
5.  Pricing engine reads velocity → adjusts price
        │
6.  Updated price served to storefront in real time
```

### A/B Testing Dashboard

The analytics dashboard (powered by **Recharts** + **TanStack Query**) provides live visibility into:
- Revenue uplift between pricing strategies
- Conversion rate comparisons across variants
- Demand velocity heatmaps by product category

---

## 🔑 Environment Variables

### Backend (`backend/.env`)

```env
# Server
PORT=5000
NODE_ENV=development

# MongoDB
MONGO_URI=mongodb://localhost:27017/priceiq

# Redis
REDIS_URL=redis://localhost:6379

# Auth
JWT_SECRET=your_jwt_secret_here
BCRYPT_SALT_ROUNDS=12

# OAuth
GOOGLE_CLIENT_ID=your_google_client_id
GOOGLE_CLIENT_SECRET=your_google_client_secret
GOOGLE_CALLBACK_URL=http://localhost:5000/auth/google/callback

# AI
GROQ_API_KEY=your_groq_api_key
```

### ML Service (`ml-service/.env`)

```env
MONGO_URI=mongodb://localhost:27017/priceiq
MODEL_PATH=./models/gru4rec.pt
TFIDF_MODEL_PATH=./models/tfidf_model.joblib
```

---

## 🤝 Contributing

Contributions are welcome! Please follow these steps:

1. **Fork** the repository
2. **Create** a feature branch: `git checkout -b feature/your-feature-name`
3. **Commit** your changes: `git commit -m 'feat: add some feature'`
4. **Push** to the branch: `git push origin feature/your-feature-name`
5. **Open** a Pull Request

Please ensure your code follows the existing TypeScript/Python style conventions and includes relevant tests.

---

## 📄 License

This project is licensed under the **MIT License** — see the [LICENSE](LICENSE) file for details.

---

<div align="center">

Built with ⚡ by the PriceIQ Team

*Demand is a signal. Price is the response.*

</div>
