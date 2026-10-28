<div align="center">

# 🤖 SigmaGPT · AI Conversational Intelligence Platform
### *Modern, Full-Stack Conversational Web Application Engineered with React.js, Node.js, Express.js & OpenAI API*

[![React](https://img.shields.io/badge/React-18-61DAFB?style=for-the-badge&logo=react&logoColor=black)](https://react.dev/)
[![Node.js](https://img.shields.io/badge/Node.js-v18%2B-339933?style=for-the-badge&logo=node.js&logoColor=white)](https://nodejs.org/)
[![Express.js](https://img.shields.io/badge/Express.js-5.x-000000?style=for-the-badge&logo=express&logoColor=white)](https://expressjs.com/)
[![OpenAI API](https://img.shields.io/badge/OpenAI_API-GPT--4o%20%2F%203.5-412991?style=for-the-badge&logo=openai&logoColor=white)](https://openai.com/)
[![Architecture](https://img.shields.io/badge/Pattern-Strict_MVC-6366F1?style=for-the-badge)](https://en.wikipedia.org/wiki/Model%E2%80%93view%E2%80%93controller)
[![License](https://img.shields.io/badge/License-MIT-blue?style=for-the-badge)](LICENSE)

</div>

---

## 📌 Overview
**SigmaGPT** is an intelligent, full-stack AI conversation application designed to deliver responsive, context-aware conversational interactions similar to ChatGPT. Engineered with a modular **React.js** frontend and an **Express.js** backend adhering to the **Model-View-Controller (MVC)** architectural pattern, SigmaGPT decouples presentation from core business logic while handling prompt execution, dynamic token management, and structured error recovery.

---

## ✨ Key Architectural Features

- **Context-Aware Conversational Intelligence:** Connects to the **OpenAI API** to generate contextually coherent, high-accuracy conversational responses across multi-turn discussions.
- **Strict MVC Separation of Concerns:**
  - **Model:** Defines prompt data structures, session state envelopes, and conversation schemas.
  - **View:** Modular, reactive UI components built in React.js featuring auto-scrolling message streams and syntax highlighting.
  - **Controller / Service Layer:** Handles HTTP request validation, prompt preprocessing, rate limiting, and OpenAI API communication.
- **Responsive & Accessible UI:** Designed with modern layout practices (Flexbox & CSS Grid) to ensure flawless usability across mobile, tablet, and desktop breakpoints without UI overflow or clipping.
- **Asynchronous Stream & State Management:** Manages asynchronous chat states (Idle, Streaming, Completed, Error) with resilient fallback prompts when external API limits are encountered.
- **Security & Environment Segregation:** API keys and sensitive runtime credentials are kept isolated on the backend server via `dotenv`, preventing client-side exposure.

---

## 🏗️ System Architecture

```
┌────────────────────────────────────────────────────────┐
│                   CLIENT (REACT.JS UI)                │
│  Chat Transcript ─── Message Composer ─── Session State│
│                           │                            │
│                           ▼ (HTTP POST / JSON)         │
├────────────────────────────────────────────────────────┤
│                 NODE.JS / EXPRESS BACKEND              │
│   ├── Routing Layer (/routes/chatRoutes.js)            │
│   ├── Middleware (CORS, JSON Parser, Rate Limiter)     │
│   ├── Chat Controller (/controllers/chatController.js) │
│   └── OpenAI Client Service (/services/openaiService)  │
│                           │                            │
│                           ▼ (Secure HTTPS Request)     │
│                   OPENAI API CLOUD                     │
│               (GPT-4o / GPT-3.5-Turbo)                 │
└────────────────────────────────────────────────────────┘
```

---

## 📁 Repository Structure

```
SigmaGPT-AI-Chat-Application-/
├── client/                      # React.js Frontend
│   ├── public/                  # Static assets & brand icons
│   ├── src/
│   │   ├── components/          # Reusable UI components (Sidebar, ChatBox, Message)
│   │   ├── App.jsx              # Application root & master layout
│   │   ├── index.css            # Global styling, dark theme, scrollbar resets
│   │   └── main.jsx             # React DOM mounting entry point
│   ├── package.json             # Frontend client dependencies
│   └── vite.config.js           # Frontend build tooling configuration
├── server/                      # Node.js + Express Backend
│   ├── controllers/             # Chat request handlers & validation logic
│   ├── routes/                  # Express route definitions (/api/chat)
│   ├── services/                # OpenAI API communication layer
│   ├── server.js                # Express app entry point & port configuration
│   └── package.json             # Backend server dependencies
└── README.md                    # Project documentation & engineering specs
```

---

## 🔌 API Endpoints Reference

| Method | Endpoint | Description | Request Payload |
| :--- | :--- | :--- | :--- |
| `POST` | `/api/chat/message` | Submit user message and receive context-aware AI response | `{ "message": "...", "conversationHistory": [...] }` |
| `GET` | `/api/chat/health` | Service health check and OpenAI API connection status | *None* |

---

## 🚀 Getting Started & Local Setup

### Prerequisites
- **Node.js** (v18.0.0 or higher)
- **npm** (v9.0.0 or higher)
- An active **OpenAI API Key** (obtainable from [platform.openai.com](https://platform.openai.com/api-keys))

---

### 1. Backend Server Setup

```bash
# Navigate to backend directory
cd server

# Install dependencies
npm install
```

Create a `.env` file in the `server` directory:
```env
PORT=5000
OPENAI_API_KEY=your_openai_api_key_here
CLIENT_URL=http://localhost:5173
```

Start the backend server:
```bash
npm start
```
*Backend service will run on `http://localhost:5000`.*

---

### 2. Frontend Client Setup

In a separate terminal window:
```bash
# Navigate to client directory
cd client

# Install frontend dependencies
npm install

# Start Vite dev server
npm run dev
```
Open **`http://localhost:5173`** in your browser.

---

## 👨‍💻 Author
**Vinayak More**  
Software Engineer & Full-Stack Developer  
- **GitHub:** [@Vinayak7986](https://github.com/Vinayak7986)  
- **LinkedIn:** [vinayak-more-b37309264](https://www.linkedin.com/in/vinayak-more-b37309264/)  
- **Portfolio:** [vinayakmore.netlify.app](https://vinayakmore.netlify.app/)  

---

## 🛡️ License
This project is open-source and licensed under the MIT License.