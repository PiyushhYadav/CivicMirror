# Civic Mirror 🏙️

[![Live Site](https://img.shields.io/badge/Live_Site-civicmirror.onrender.com-success?style=for-the-badge&logo=render)](https://civicmirror.onrender.com)
[![Backend API](https://img.shields.io/badge/API_Service-civic--mirror--backend.onrender.com-blue?style=for-the-badge&logo=render)](https://civic-mirror-backend.onrender.com)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge)](https://opensource.org/licenses/MIT)

> **Civic Mirror** is a civic intelligence platform that ingests complaints from Reddit and social media, classifies urgency and municipal department with AI, geolocates issues, and automatically escalates them to local authorities.

---

## 🌐 Live Deployments

* 🖥️ **Live Web Application:** [https://civicmirror.onrender.com](https://civicmirror.onrender.com)
* ⚙️ **Production Backend API:** [https://civic-mirror-backend.onrender.com](https://civic-mirror-backend.onrender.com)
* 🩺 **Backend Health Endpoint:** [https://civic-mirror-backend.onrender.com/health](https://civic-mirror-backend.onrender.com/health)

---

## 🛠️ Technologies Used

### Frontend (`CIVIC/`)
A responsive, modern React application providing an interactive dashboard for citizens and administrators.
* **React 19**
* **Vite** (Build tool & development server)
* **TailwindCSS** (Utility-first CSS styling)
* **React Router DOM** (Client-side routing)
* **Recharts** (Analytics and complaint metrics)
* **Leaflet & React Leaflet** (Interactive geographic mapping)
* **jsPDF** (Automated PDF incident report generation)
* **Lucide React** (Modern UI icons)

### Backend (`CIVIC_BACKEND/`)
A robust Node.js/Express service for social media ingestion, natural language classification, geocoding, and dispatch.
* **Node.js & Express.js**
* **Supabase** (PostgreSQL persistence via `@supabase/supabase-js`)
* **Axios** (Reddit API queries)
* **Nodemailer** (Automated email escalation to municipal authorities)
* **Express Rate Limit & CORS** (API protection and cross-origin security)
* **dotenv** (Configuration management)

---

## 📁 Repository Structure

```
.
├── CIVIC/              # Frontend React application (Vite + Tailwind)
│   ├── src/            # Components, pages, hooks, mock data
│   └── .env.example    # Frontend environment config (VITE_BACKEND_URL)
├── CIVIC_BACKEND/      # Backend Express application (Node.js)
│   ├── src/            # Routes, services, middleware, municipal directory
│   └── .env.example    # Backend environment config
├── .gitignore          # Repository-level ignore rules
└── README.md           # Documentation & deployment guide
```

---

## 🚀 Local Development Setup

### 1. Backend Setup
```bash
cd CIVIC_BACKEND
npm install

# Copy the sample environment file
cp .env.example .env

# Run the development server
npm run dev
```
*The backend will run on `http://localhost:3001`.*

### 2. Frontend Setup
```bash
cd CIVIC
npm install

# (Optional) specify backend URL in .env
# VITE_BACKEND_URL=http://localhost:3001

# Start the frontend dev server
npm run dev
```
*The frontend will run on `http://localhost:5173`.*

---

## ☁️ Deployment Architecture (Render)

This repository is deployed on **Render** under a monorepo structure:

| Component | Service Type | Root Directory | Build Command | Start/Publish | Environment Variables |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Frontend** | Static Site | `CIVIC` | `npm run build` | `dist` | `VITE_BACKEND_URL=https://civic-mirror-backend.onrender.com` |
| **Backend** | Web Service | `CIVIC_BACKEND` | `npm install` | `npm start` | `NODE_ENV=production`, `FRONTEND_URL=https://civicmirror.onrender.com` |

*Single Page Application rewrite rule: `/*` → `/index.html` on the static site ensures direct route access.*

---

## 💡 Key Features
* **Reddit Ingestion**: Fetches civic infrastructure complaints from Reddit feeds (authenticated or public).
* **AI Categorization**: Automatically detects urgency levels and matches incidents with respective departments (PWD, Jal Board, Sanitation, etc.).
* **Geocoding & Interactive Map**: Visualizes reported civic issues geographically.
* **Automated Escalation**: Generates incident packages and emails appropriate municipal officials with citizen notifications.
* **Graceful Fallbacks**: Fully functional in demo mode with synthetic data when credentials are not configured.

---

**Built for CODEZEN 2026 · Team IOSTREAM**
