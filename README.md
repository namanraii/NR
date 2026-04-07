# 📖 NeuroRead | Reading, Reimagined

NeuroRead is an accessibility-first, AI-powered reading platform designed to reduce cognitive load and provide a highly personalized reading experience. It features tools for individuals with dyslexia, ADHD, and anyone who benefits from clearer, more structured reading materials.

## 🚀 Live Deployments

- **Frontend Application (Vercel):** [https://nr-three-puce.vercel.app](https://nr-three-puce.vercel.app)
- **Backend API (Render):** [https://neuroread-5icn.onrender.com](https://neuroread-5icn.onrender.com)

## ✨ Core Features

- **🧠 Smart Simplifier (Focus Mode):** Uses AI (Groq + LLaMA) to rewrite dense text into easily digestible content, tracking cognitive load reduction.
- **🗣️ Text-to-Speech (TTS):** Integrated audio playback for simplified text.
- **👁️ Dyslexia Support:** Includes the OpenDyslexic font, line highlighting, reading rulers, and color overlays (B/D/P/Q distinction).
- **📊 Session Analytics:** Tracks your "Cognitive Score" and reading history to visualize improvement over time.
- **🎨 Beautiful & Accessible UI:** A warm, calm, constraint-based design (defaulting to Warm Beige) that avoids harsh contrasts and is fully customizable.

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

## 💻 Running Locally

### 1. Backend Setup
```bash
cd backend
python -m venv venv
source venv/bin/activate
pip install -r requirements.txt

# Create a .env file and add your GROQ_API_KEY
uvicorn app.main:app --reload
```

### 2. Frontend Setup
```bash
cd frontend/frontend
npm install

# Create a .env file and add: VITE_API_URL=http://localhost:8000
npm run dev
```

## 🤝 Contributing

Contributions to improve accessibility or AI features are always welcome! Please create an issue or pull request.
