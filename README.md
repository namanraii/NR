# 📖 NeuroRead | Reading, Reimagined

NeuroRead is an accessibility-first, AI-powered reading platform designed to reduce cognitive load and provide a highly personalized reading experience. It features tools for individuals with dyslexia, ADHD, and anyone who benefits from clearer, more structured reading materials.

## 🚀 Live Deployments

- **Frontend Application (Vercel):** [https://nr-three-puce.vercel.app](https://nr-three-puce.vercel.app)
- **Backend API (Render):** [https://neuroread-5icn.onrender.com](https://neuroread-5icn.onrender.com)

---

## ✨ Core Features

- **🧠 Smart Simplifier (Focus Mode):** Uses AI (Groq + LLaMA) to rewrite dense text into easily digestible content, tracking cognitive load reduction.
- **🗣️ Text-to-Speech (TTS):** Integrated audio playback for simplified text.
- **👁️ Dyslexia Support:** Includes the OpenDyslexic font, line highlighting, reading rulers, and color overlays (B/D/P/Q distinction).
- **📊 Session Analytics:** Tracks your "Cognitive Score" and reading history to visualize improvement over time.
- **🎨 Beautiful & Accessible UI:** A warm, calm, constraint-based design (defaulting to Warm Beige) that avoids harsh contrasts and is fully customizable.

---

## 📂 Folder Structure

The repository is structured as a monorepo containing both the FastAPI backend and the Vite/React frontend.

```text
neuroread/
├── backend/                 # Python FastAPI Backend
│   ├── app/                 # Core application code
│   │   ├── main.py          # Application entry point
│   │   ├── routes/          # API endpoints (e.g., assistive/simplify)
│   │   └── services/        # Business logic & AI integration (Groq client)
│   └── requirements.txt     # Python dependencies
│
├── frontend/                
│   └── frontend/            # React + Vite Frontend
│       ├── public/          # Static assets (fonts, logo)
│       ├── src/             
│       │   ├── components/  # React UI components (Navbar, Modal, etc.)
│       │   ├── pages/       # High-level route views (Dashboard, Simplifier)
│       │   ├── services/    # API calls (api.js connecting to backend)
│       │   ├── stores/      # Zustand state management
│       │   ├── index.css    # Tailwind CSS & custom design tokens
│       │   └── main.tsx     # React DOM entry
│       ├── package.json     # Node dependencies and scripts
│       ├── tailwind.config.js
│       └── vite.config.ts
│
└── README.md                # You are here
```

---

## 🛠️ Technology Stack

### Frontend
- **Framework:** React / Vite (TypeScript/JavaScript)
- **Styling:** Tailwind CSS & Custom CSS Variables (for real-time accessibility theming)
- **Animations:** Framer Motion & GSAP
- **State Management:** Zustand
- **Deployment:** Vercel

### Backend
- **Framework:** FastAPI (Python)
- **AI Integration:** Groq API (LLaMA models)
- **Machine Learning / NLP:** spaCy, textstat, NLTK
- **Deployment:** Render

---

## 💻 Local Machine Setup & Usage

To run the full application on your own machine, you need to run both the Backend and Frontend servers simultaneously in separate terminal windows.

### 1. Start the Backend

1. Open a terminal and navigate to the `backend` folder:
   ```bash
   cd backend
   ```
2. Create and activate a Python virtual environment:
   ```bash
   # On macOS/Linux:
   python3 -m venv venv
   source venv/bin/activate
   
   # On Windows:
   python -m venv venv
   venv\Scripts\activate
   ```
3. Install the required dependencies:
   ```bash
   pip install -r requirements.txt
   ```
4. Create a `.env` file in the `backend` folder and add your Groq API Key:
   ```env
   GROQ_API_KEY=gsk_your_groq_api_key_here
   ```
5. Start the backend server:
   ```bash
   python -m uvicorn app.main:app --host 0.0.0.0 --port 8000 --reload
   ```

### 2. Start the Frontend

1. Open a **new** terminal window and navigate to the `frontend/frontend` folder:
   ```bash
   cd frontend/frontend
   ```
2. Install the necessary Node packages:
   ```bash
   npm install
   ```
3. Create a `.env` file in the `frontend/frontend` folder and point it to your local backend:
   ```env
   VITE_API_URL=http://localhost:8000
   ```
4. Start the frontend development server:
   ```bash
   npm run dev
   ```
5. Open your browser and go to the link shown in the terminal (usually `http://localhost:5173`).

---

## 🌍 How to Deploy

If you want to host NeuroRead live on the internet, follow this pipeline:

### 1. Deploy the Backend to Render
1. Create a free account on [Render.com](https://render.com).
2. Connect your GitHub account and create a new **Web Service**.
3. Select your NeuroRead repository.
4. **Configuration Details:**
   - **Root Directory:** `backend`
   - **Environment:** `Python 3`
   - **Build Command:** `pip install -r requirements.txt`
   - **Start Command:** `uvicorn app.main:app --host 0.0.0.0 --port $PORT`
5. Click **Advanced** (or Environment Variables) and confidently add:
   - `GROQ_API_KEY` : `Your Groq key`
6. Click **Create Web Service**. Once it is Live, copy the generated URL (e.g., `https://neuroread-xyz.onrender.com`).

### 2. Deploy the Frontend to Vercel
1. Create an account on [Vercel.com](https://vercel.com) and import your GitHub repository.
2. In the project settings configuration:
   - **Root Directory:** `frontend/frontend`
   - **Framework Preset:** `Vite`
   - **Build Command:** `npm run build`
   - **Output Directory:** `dist`
3. Expand **Environment Variables** and add:
   - **Name:** `VITE_API_URL`
   - **Value:** `https://neuroread-xyz.onrender.com` *(The URL you copied from Render)*
4. Click **Deploy**. Vercel will build and host your frontend globally.

---

## 🤝 Contributing

Contributions to improve accessibility or AI features are always welcome! Please create an issue or pull request.
