# Exercise 05: Web UI (Optional)

>**Duration:** 20 min  
>**Objective:** Add web chat interface <br>
>**Tech Showcase:** FastAPI + React UI

---

## Part 1: Create FastAPI and React App (5 min)

Use this prompt to generate backend and frontend:

```
Build a simple UI for my deployed Microsoft Foundry AI Release Readiness Assistant using React + Vite and Python FastAPI.

My agent uses the OpenAI Responses protocol. First inspect main.py, requirements.txt/pyproject.toml, and existing configuration to verify authentication and SDK compatibility.

Store the agent endpoint in backend .env as FOUNDRY_AGENT_ENDPOINT.
Create FastAPI /health and /chat endpoints that securely invoke the deployed agent.
Build a responsive React chat UI with message history, input, loading state, error handling, and sample release-readiness prompts.
Keep credentials on the backend; reuse the existing agent without recreating it.
Test the real end-to-end flow and provide Windows PowerShell run commands.
Inspect first, preserve existing code, and never guess configuration or use mock responses.
```

---

## Part 2: Start Server (5 min)

```bash
.\ui\backend\.venv\Scripts\python.exe -m pip install -r .\ui\backend\requirements.txt

# Start server
.\ui\backend\.venv\Scripts\python.exe -m uvicorn app.main:app --app-dir .\ui\backend --reload --host 127.0.0.1 --port 8000

```
Open browser: http://127.0.0.1:8000/health

---

## Part 3: Start Web UI (5 min)

```bash
# Start web UI
Set-Location .\ui\frontend
npm install
npm run dev
```

Open browser: http://127.0.0.1:5173/

---

## Checklist

- [ ] Web chat interface loads successfully and communicates with the backend agent
- [ ] Backend FastAPI server responds correctly to /health and /chat endpoints
- [ ] End-to-end chat flow works with real agent responses

---

## Next Steps

Congratulations! You have successfully added a web chat interface for your AI Release Readiness Assistant. Workshop complete. 
