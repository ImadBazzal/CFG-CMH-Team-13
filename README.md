# Team-13

CLEP Finder Portal is a web platform designed to help students explore courses, track progress, and give institutions an easy way to manage learning data.

Project Structure
backend/ – Node.js + Express server with Supabase and PostgreSQL
studentview/ – Learner-facing front end built with React, Vite, and CSS
admin/ – Admin and institution dashboard built with React, Vite, and CSS

Tech Stack
Frontend: React, Vite, CSS
Backend: Node.js, Express, Supabase, PostgreSQL

Features
Secure authentication and user management
Course tracking and progress visualization
Admin dashboard for institutions to manage learners and courses
Responsive, minimal UI for both learner and admin views

---

Docker: Run the entire stack locally

Prerequisites
- Docker Desktop 4.x+
- (Optional) Node.js 20+ if you also plan to run outside Docker

1) Configure environment variables
- Copy `backend/.env.example` to `backend/.env` and paste your Supabase credentials:
```
SUPABASE_URL=...your supabase project url...
SUPABASE_ANON_KEY=...your anon key...
```
- (Optional) Copy `.env.example` to `.env` at repo root to override default ports.

2) Build and start all services
```
docker compose up --build
```
This will start:
- Backend (Express + Supabase) → http://localhost:8000
- Frontend (Learner CRA demo) → http://localhost:3000
- Admin (Admin CRA app) → http://localhost:3001
- Studentview (Vite app) → http://localhost:5173

Notes
- Containers mount your local folders for live-reload. First run may be slower while dependencies are installed.
- If your frontend(s) call the API, set an env var like `REACT_APP_API_URL=http://localhost:8000/api` (CRA) or `VITE_API_URL=http://localhost:8000/api` (Vite) in the respective app and read it in code.
- Stop everything with `Ctrl+C`, then `docker compose down` to remove containers.

Troubleshooting
- If ports are busy, change host ports in `docker-compose.yml` (or via root `.env`).
- On Apple Silicon/ARM: images target `node:20-alpine` which supports arm64.
- Supabase vars are required; the backend will exit if they are missing.

---

 <br /> <br /> The code ("Code") in this repository was created solely by the student teams during a coding competition hosted by JPMorgan Chase Bank, N.A. ("JPMC"). JPMC did not create or contribute to the development of the Code. This Code is provided AS IS and JPMC makes no warranty of any kind, express or implied, as to the Code, including but not limited to, merchantability, satisfactory quality, non-infringement, title or fitness for a particular purpose or use.
