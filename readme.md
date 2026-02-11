

# 🧠 Local Llama 3.1 ChatGPT Clone (React + FastAPI + Ollama)

A full-stack AI chatbot built using:

- ⚛ React (Frontend)
- 🚀 FastAPI (Backend)
- 🦙 Ollama (Llama 3.1 local LLM)
- 🔄 Streaming responses
- 🛑 Stop generation feature
- ✨ Markdown rendering (bold, code, formatting supported)

This project replicates a ChatGPT-style interface running entirely on your local machine.

---

# 📸 Features

- ChatGPT-style UI
- Real-time streaming responses
- Stop generation button
- Markdown rendering (bold, lists, code blocks)
- Auto-scroll to latest message
- Enter to send / Shift + Enter for new line
- Clean full-screen professional layout
- Fully local (no external API usage)

---

# ⚙️ Requirements

Before starting, make sure you have:

- Node.js (LTS version)
- Python 3.9+
- Git
- Ollama installed

---

# 🦙 Step 1 — Install Ollama

Download from:

https://ollama.com

After installation, verify:

```bash
ollama --version
````

Pull Llama 3.1 model:

```bash
ollama pull llama3.1
```

Test it:

```bash
ollama run llama3.1
```

Type `/bye` to exit.

---

# 📥 Step 2 — Clone Repository

```bash
git clone https://github.com/YOUR_USERNAME/ai-chatbot.git
cd ai-chatbot
```

---

# 🚀 Step 3 — Backend Setup (FastAPI)

### 1️⃣ Navigate to backend

```bash
cd backend
```

### 2️⃣ Create virtual environment

```bash
python -m venv venv
```

### 3️⃣ Activate virtual environment

**Windows:**

```bash
venv\Scripts\activate
```

**Mac/Linux:**

```bash
source venv/bin/activate
```

### 4️⃣ Install dependencies

```bash
pip install fastapi uvicorn requests python-dotenv
```

### 5️⃣ Run backend server

```bash
uvicorn main:app --reload
```

Backend will run at:

```
http://127.0.0.1:8000
```

Keep this terminal running.

---

# 🎨 Step 4 — Frontend Setup (React)

Open a new terminal.

Navigate to frontend:

```bash
cd frontend
```

### 1️⃣ Install dependencies

```bash
npm install
```

### 2️⃣ Install Markdown renderer

```bash
npm install react-markdown
```

### 3️⃣ Start frontend

```bash
npm run dev
```

Frontend will run at:

```
http://localhost:5173
```

Open it in your browser.

---

# 🛑 Stop Generation Feature

The Stop button works using:

* `AbortController` in frontend
* Cancels streaming fetch request
* Immediately stops model output

---

# 🧠 How It Works

1. User sends message from React UI
2. React sends conversation history to FastAPI
3. FastAPI forwards request to Ollama `/api/chat`
4. Ollama streams response
5. FastAPI relays stream to frontend
6. React updates UI live

---

# 🧪 Development Commands Cheatsheet

## Backend

Start server:

```bash
uvicorn main:app --reload
```

Deactivate venv:

```bash
deactivate
```

---

## Frontend

Install packages:

```bash
npm install
```

Start dev server:

```bash
npm run dev
```

Build production:

```bash
npm run build
```

---

## Ollama

List models:

```bash
ollama list
```

Remove model:

```bash
ollama rm llama3.1
```

Serve manually:

```bash
ollama serve
```

---

# 🛠 Common Errors & Fixes

### CORS Error

Make sure backend has:

```python
allow_origins=["http://localhost:5173"]
```

---

### Backend not connecting

Ensure Ollama is running:

```bash
ollama list
```

---

### Port already in use

Kill process or change port:

```bash
uvicorn main:app --reload --port 8001
```

---

# 🌟 Future Improvements

* Chat history persistence
* Model selector dropdown
* Sidebar for conversation list
* Code syntax highlighting
* Dark/light mode toggle
* Authentication system
* Docker support
* WebSocket streaming

---

# 🤝 Contributing

Contributions are welcome.

## 🔁 How to Contribute

### 1️⃣ Fork the repository

Click **Fork** button on GitHub.

### 2️⃣ Clone your fork

```bash
git clone https://github.com/YOUR_USERNAME/ai-chatbot.git
cd ai-chatbot
```

### 3️⃣ Create a new branch

```bash
git checkout -b feature/your-feature-name
```

### 4️⃣ Make changes

Edit files and test locally.

### 5️⃣ Commit changes

```bash
git add .
git commit -m "Added feature: description"
```

### 6️⃣ Push to your fork

```bash
git push origin feature/your-feature-name
```

### 7️⃣ Create Pull Request

Go to your fork on GitHub
Click **Compare & Pull Request**

---

# 📜 License

This project is open-source and available under the MIT License.

---
