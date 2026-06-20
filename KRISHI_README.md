# 🌾 KRISHI — AI-Powered Agriculture Assistant

> An offline-first, multilingual AI platform helping Indian smallholder farmers diagnose crop diseases, get expert advice, and access a peer-to-peer marketplace — all in one app.

**Final Year Project (BIS786)** · Dept. of Information Science & Engineering, JSS Academy of Technical Education, Bengaluru · 2026–27

## 👥 Team
- Ananya Singh
- Harsh Kumar Anand
- **Dhriti RR**
- Harshdeep Jadhav

*Under the guidance of Dr. Sahana V, Associate Professor*

## 📖 Overview
Indian agriculture supports over 120 million farming households, yet crop diseases alone cause 20–40% in annual yield losses — largely due to delayed diagnosis, language barriers, and poor rural connectivity. Most existing tools are English-only, cloud-dependent, and solve only one piece of the problem.

**KRISHI** (Sanskrit: कृषि, "Agriculture") bridges this gap as a single, offline-capable web app combining:
- 🩺 AI crop disease detection
- 🗣️ Multilingual support (English, Hindi, Kannada)
- 🛒 Peer-to-peer marketplace
- 👨‍🌾 Expert consultation booking
- 💬 Community forum
- 🤖 24/7 AI chatbot

## ✨ Key Features
| Feature | Details |
|---|---|
| **Disease Detection** | TensorFlow.js model running fully in-browser, ~92% accuracy across 15+ disease categories, no internet required |
| **Offline-First** | Progressive Web App (PWA) with service-worker caching; local knowledge base (`plantDiseases.js`, `agriKnowledge.js`) |
| **Voice & Language** | Web Speech API for voice synthesis in English, Hindi, Kannada; runtime language switching |
| **Marketplace** | List, search, and inquire about agricultural produce/inputs |
| **Expert Consultation** | Book sessions with certified agricultural experts |
| **Community Forum** | Threaded posts and farmer-to-farmer knowledge sharing |
| **AI Chatbot** | Agriculture-specific Q&A, works offline via local knowledge base |

## 🛠️ Tech Stack
**Frontend:** React 18, Tailwind CSS (glassmorphism UI), Web Speech API, Service Workers
**Backend:** Node.js, Express.js, REST API (`/api/chat`, `/api/community`, `/api/market`, `/api/consult`)
**AI/ML:** TensorFlow.js (in-browser inference), local rule-based fallback
**Database:** MongoDB Atlas (experts, products, posts collections)
**Hosting:** Vercel
**Other:** Multer (image uploads), Mongoose (ODM), Axios, React Router

## 🏗️ Architecture
```
Farmer captures/uploads leaf image
        ↓
Image preprocessing (resize 224×224, normalize)
        ↓
TensorFlow.js model → Disease + confidence score (offline, in-browser)
        ↓
Treatment recommendations from local knowledge base
        ↓
Multilingual rendering + voice output (Web Speech API)
        ↓
Optional: Chatbot / Expert booking / Marketplace / Community (synced via REST API + MongoDB Atlas when online)
```

## 📊 Target Outcomes
- ~92% disease detection accuracy across 15+ categories
- Scan-to-result flow in under 3 seconds
- API response time under 500ms
- Lighthouse performance score target: 98/100
- 100% offline availability for core disease detection

## 🚧 Current Limitations
- Uses pre-trained TensorFlow.js weights (training a custom CNN is out of scope)
- JWT-based authentication is a planned future enhancement
- PWA service workers are partially implemented
- Marketplace payment gateway not yet integrated

## 🔮 Future Enhancements
- Full authentication with role management (farmer/expert)
- LLM-based advisory for richer chatbot responses
- WhatsApp API integration for alerts
- Weather API integration for location-specific advisory
- Voice **input** in addition to voice output

## 📄 Documentation
Full project synopsis (architecture, literature review, methodology, 30-reference literature survey) available in `/docs`.

---
*This was a collaborative final-year team project. My contributions focused on [add your specific contribution here, e.g. frontend modules / disease detection integration / multilingual UI].*
