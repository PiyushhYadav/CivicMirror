# Civic Mirror 🏙️

Civic Mirror is a platform designed to ingest civic complaints from Reddit, analyze them, and automatically escalate them to the appropriate municipal authorities. It bridges the gap between citizens reporting issues on social media and the actual problem resolution by local government bodies.

---

## 🛠️ Technologies Used

### Frontend (`CIVIC/`)
The frontend is a modern, responsive React application built to provide an intuitive dashboard for users and authorities.
- **React 19**
- **Vite** (Build tool & development server)
- **TailwindCSS** (Utility-first CSS framework for styling)
- **React Router DOM** (Navigation)
- **Recharts** (Data visualization & charts)
- **Leaflet & React Leaflet** (Interactive map visualizations)
- **jsPDF** (Generating complaint reports)
- **Lucide React** (Iconography)

### Backend (`CIVIC_BACKEND/`)
The backend is a robust Node.js service responsible for fetching data, classifying urgency, geocoding, and managing complaints.
- **Node.js & Express.js**
- **Supabase** (Database & Authentication via `@supabase/supabase-js`)
- **Axios** (HTTP client for fetching Reddit API)
- **Nodemailer** (Automated email notifications to municipal authorities)
- **dotenv** (Environment variables management)
- **CORS & Express Rate Limit** (Security and rate limiting)

---

## 📁 Repository Structure

```
.
├── CIVIC/              # Frontend React application (Vite + Tailwind)
├── CIVIC_BACKEND/      # Backend Express application (Node.js)
└── README.md           # This file
```

---

## 🚀 How to Run Locally

### 1. Backend Setup
```bash
cd CIVIC_BACKEND
npm install

# Copy the environment file and configure your credentials
cp .env.example .env

# Run the development server
npm run dev
```
*The backend will run at `http://localhost:3001`.*

### 2. Frontend Setup
```bash
cd CIVIC
npm install

# Start the frontend application
npm run dev
```
*The frontend will be accessible at `http://localhost:5173`.*

---

## 💡 Features
- **Reddit API Integration**: Fetches complaints related to infrastructure (potholes, water leaks, etc.) directly from Reddit.
- **AI Classification**: Automatically classifies the complaint's urgency and targets the correct department (e.g., PWD).
- **Geocoding**: Extracts location details from text and plots them on interactive maps.
- **Automated Notifications**: Sends emails to respective municipal zones and notifies citizens.
- **Mock Mode**: Works seamlessly without credentials for demo purposes, logging outputs to the console.

---

**Built for CODEZEN 2026 · Team IOSTREAM**
