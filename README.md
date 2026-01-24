# ft_transcendence

A full-stack **real-time web application** built for the 42 curriculum’s **ft_transcendence** project: a modern platform centered around **online Pong**, authentication, social features, and real-time communication.

> Repo includes a frontend + a Python backend/auth service, Dockerized infrastructure, and extra modules/configs (ELK, certificates, optional blockchain experiments).  
> See `en.subject.pdf` for the official subject.

---

## ✨ Key Features (project goal)

- 🔐 Authentication (42 OAuth / sessions, profile)
- 🎮 Real-time Pong gameplay (multiplayer)
- 💬 Social features (friends, chat, presence)
- 📊 Stats & leaderboard
- 🐳 Dockerized dev environment

---

## 🧱 Tech Stack (as in this repo)

- **Backend / Auth:** Python service in `user_auth/` (see `requirements.txt`)  
- **Frontend:** JavaScript/HTML app in `frontend/`
- **Infra:** Docker / docker compose, plus custom configs under `docker/`
- **Monitoring (optional):** `elk-config/`
- **Certificates:** `certs/` and `postgres-certs/`

Languages detected in the repository include Python, JavaScript, and HTML. :contentReference[oaicite:1]{index=1}

---

## 📁 Repository Structure

```code
.
├── frontend/ # frontend (SPA / UI)
├── user_auth/ # backend/auth service (Python)
├── docker/ # docker-related scripts/config
├── certs/ # TLS certs (dev)
├── postgres-certs/ # postgres TLS certs (dev)
├── elk-config/ # ELK stack configuration (optional)
├── blockchain/ # experimental module
├── docker-compose.yml
├── Makefile
├── requirements.txt
└── en.subject.pdf
```

(If your structure evolves, update this section.)

---

## 🚀 Quick Start (Docker)

### 1) Clone
```bash
git clone https://github.com/ARAMELOYAN/ft_transcendence.git
cd ft_transcendence
```
2) Environment variables

This repo contains an .env file at the root. Make sure it has correct values for:

database credentials

OAuth client keys (if used)

secrets (JWT/session)

service URLs/ports

Tip: avoid committing real secrets in .env for public repos.

3) Build & run
```bash
docker compose up --build
```

Stop:
```bash
docker compose down
```
🛠️ Makefile helpers

If you prefer Make targets:

make


Open Makefile to see available commands (up/down/build/logs/migrate, etc.).

🧩 Backend (user_auth)

Typical local workflow (if you run it outside Docker):

python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
# then run the service (check user_auth/ for the entrypoint)


There are helper scripts in the repo root:

makemigrations.sh

migrate.sh

runserver.sh

manage.sh

Use them if they match your Django setup.

🌐 Frontend (frontend)

Install & run commands depend on your frontend tooling (React/Vue/Vanilla/etc.).
Check frontend/ for package.json and scripts, then run something like:

cd frontend
npm install
npm run dev

🔍 Observability (optional)

This repo includes elk-config/ which suggests an ELK stack setup for logs/metrics.
If enabled in docker-compose.yml, you can use it to inspect application logs.

✅ Notes & Constraints (42)

The project is expected to be secure (input validation, auth, permissions).

Real-time features should be handled via WebSockets or an equivalent real-time layer.

The final product should be usable through a browser and containerized for evaluation.

Refer to en.subject.pdf for exact mandatory/bonus requirements.

📄 License

Educational project (42 curriculum).
(Optionally add a license file if you want: MIT/Apache-2.0/GPL-3.0.)

👤 Authors

Aram Eloyan — https://github.com/ARAMELOYAN
