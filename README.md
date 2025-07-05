# 🚀 Actomatic - GitHub Actions Workflow Templates

A production-ready GitHub Actions template repo to streamline CI/CD across AI, frontend, backend, and DevOps deployments.

This repo includes YAML-based workflows for:

- 🧠 AI/ML & Jupyter Notebooks (Python)
- ⚛️ Frontend (React/Next.js with Vercel/Netlify)
- 🐍 Backend (FastAPI/Node.js with Railway/Render/Heroku)
- 🐳 Dockerized Microservices
- 🌍 GitHub Pages static hosting
- 🔐 VPS via SSH + Rsync
- 🔁 Scheduled Cron jobs
- 🧹 Auto lint, format, and deploy

## 📁 Folder Structure
```
.
├── .github/workflows     # All GitHub Actions YAML files
├── client/               # Frontend (React/Next.js)
├── server/               # Backend (Node.js / FastAPI)
├── notebooks/            # AI/ML Jupyter notebooks
├── public/               # GitHub Pages static files
├── netlify.toml          # Netlify frontend deployment config
├── railway.json          # Railway backend deploy config
├── render.yaml           # Render deploy config
├── fly.toml              # Fly.io app config
├── Procfile              # Heroku deployment file
├── SUPABASE.md           # Supabase integration guide
├── .env.example          # Template for environment variables
├── docker-compose.yml    # Full Docker app setup
└── README.md             # This file
```

---

## 🔐 GitHub Secrets Needed
| Secret Name              | Purpose                          |
|--------------------------|----------------------------------|
| `VERCEL_TOKEN`           | Vercel deploy                    |
| `VERCEL_PROJECT_ID`      | Vercel project                   |
| `VERCEL_ORG_ID`          | Vercel organization              |
| `RAILWAY_DEPLOY_HOOK`    | Railway auto deploy              |
| `RENDER_DEPLOY_KEY`      | Render deploy trigger            |
| `HEROKU_API_KEY`         | Heroku deploy                    |
| `VPS_KEY`                | SSH deploy to private VPS        |
| `DOCKER_USERNAME`        | Docker Hub login                 |
| `DOCKER_PASSWORD`        | Docker Hub login                 |
| `GITHUB_TOKEN`           | Default token for Actions        |

---

## ✅ Included Workflows

| File                        | Description                            |
|-----------------------------|----------------------------------------|
| `ci-ai.yml`                | Convert/test AI notebooks              |
| `ci-frontend.yml`          | Build + deploy frontend (Vercel)       |
| `ci-backend.yml`           | Test + deploy backend (Railway)        |
| `gh-pages-deploy.yml`      | Static site GitHub Pages deploy        |
| `docker-build-push.yml`    | Build/push Docker images               |
| `lint-autoformat.yml`      | Prettier, ESLint, Black auto format    |
| `weekly-update.yml`        | Weekly scheduled cron task             |
| `vps-deploy.yml`           | SSH + rsync deploy to VPS              |
| `heroku-deploy.yml`        | CI deploy to Heroku                   |
| `render-deploy.yml`        | CI deploy to Render                   |

---

## 🗺️ Workflow Overview
```
                 ┌─────────────┐
                 │   GitHub    │
                 │   Push PR   │
                 └────┬────────┘
                      │
         ┌────────────┼────────────┐
         │            │            │
         ▼            ▼            ▼
    Frontend      Backend        AI/DS
    (React)     (Node/FastAPI) (Notebooks)
       │            │              │
       ▼            ▼              ▼
  Vercel /      Railway /      GitHub Pages
  Netlify       Render /       nbconvert
                Heroku
       │            │
       ▼            ▼
     Docker Build & Push (Optional)
       │
       ▼
     VPS Deploy (via SSH + Rsync)
```

---

## 🧠 AI Notebook Deployment
- Converts Jupyter notebooks → HTML using `nbconvert`
- Deploys the converted HTML as GitHub Pages docs

---

## ⚛️ Frontend Deployment
- Vercel: Uses `amondnet/vercel-action`
- Netlify: Uses `netlify.toml`
- GitHub Pages: Static folder auto-publish

---

## 🐍 Backend Deployment
- Railway: Trigger via deploy hook
- Heroku: GitHub Actions deploy via `Procfile`
- Render: Deploy via API webhook
- VPS: SSH key + Rsync push

---

## 📦 Docker Support
- Build and push images for client/server
- Works with Docker Hub or self-hosted registry

---

## 🔁 Scheduled Cron Jobs
Run weekly tasks like sync scripts, dataset updates, backups:
```yaml
schedule:
  - cron: "0 3 * * 0" # Every Sunday 3AM UTC
```

---

## 🧪 Lint + Format
Run Prettier/ESLint (Node) and Black (Python) on every PR or push

---

## 🧱 How to Use
1. Clone or fork this repo
2. Customize your `client/`, `server/`, `notebooks/`
3. Set required secrets in GitHub → Settings → Secrets → Actions
4. Push to `main`, and workflows will run automatically ✅

---

## 📫 Author
Maintained by [@MuhammadTahaNasir](https://github.com/MuhammadTahaNasir) – feel free to fork, star ⭐, and contribute.

> 💬 Need Render/Netlify/Heroku setup in your real project? Ping me anytime!
