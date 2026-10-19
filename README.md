# 🔍 Python Under the Hood

![Python](https://img.shields.io/badge/Python-3776AB?logo=python&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?logo=fastapi&logoColor=white)
![React](https://img.shields.io/badge/React_18-20232A?logo=react&logoColor=61DAFB)
![Vite](https://img.shields.io/badge/Vite-646CFF?logo=vite&logoColor=white)

Write Python in the browser, run it, and step through execution line by line while watching local variables change. The idea is similar to Python Tutor.

## Features
- CodeMirror editor with Python syntax highlighting
- Backend traces execution with `sys.settrace`, recording line, locals snapshot and stdout per step
- Step-by-step playback with a plain-English explanation of what changed
- Captures exceptions and tracebacks

> ⚠️ The backend `exec`s arbitrary code. Run it locally only. Don't deploy it publicly without sandboxing.

## Screenshot
<!-- Add a GIF stepping through a loop: docs/demo.gif -->
![Demo](docs/demo.gif)

## Tech stack
FastAPI · Uvicorn · React 18 · @uiw/react-codemirror · Vite 5

## Project structure
```
.
├── main.py            # FastAPI app: GET /api/health, POST /api/trace
├── requirements.txt
└── frontend/
    ├── src/App.jsx    # editor + step viewer
    ├── src/main.jsx, src/styles.css
    └── vite.config.js
```

## Getting started
```bash
git clone https://github.com/Preethambhavirisetty/python-under-the-hood.git
cd python-under-the-hood

# Backend
python3 -m venv .venv && source .venv/bin/activate
pip install -r requirements.txt
python main.py                 # http://127.0.0.1:8000

# Frontend (new terminal)
cd frontend
npm install
npm run dev
```

## Environment variables
None. The API URL is hard-coded as `http://127.0.0.1:8000` in `frontend/src/App.jsx`. Consider `VITE_API_BASE`.

## Contributing
1. Fork the repo and create a branch: `git checkout -b feature/your-change`
2. Commit using [Conventional Commits](https://www.conventionalcommits.org/) (`feat: …`, `fix: …`)
3. Push and open a pull request against `main`

## License
No license file yet. Add one (MIT is a common choice) via **Add file → Create new file → `LICENSE` → Choose a license template**, then update this section.
