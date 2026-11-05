# Hi, I'm Amogh Koushik 👋

2nd-year B.Tech CSE student at **IIIT Nagpur** (class of 2029). I work on backend systems in Python and practise DSA in C++. Right now I'm learning backend engineering properly, building my own projects, and starting out in open source.

- Building **ContestPulse**, a Codeforces tracker for my college coding club
- Learning FastAPI, PostgreSQL, Redis and how real systems are designed
- Exploring AI/ML, deep learning, data science and visualisation
- AI/ML Co-Lead at GDG On Campus IIIT Nagpur

## Tech stack

**Languages**

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![C++](https://img.shields.io/badge/C%2B%2B-00599C?style=for-the-badge&logo=cplusplus&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)

**Backend**

![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=for-the-badge&logo=fastapi&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=for-the-badge&logo=postgresql&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-DC382D?style=for-the-badge&logo=redis&logoColor=white)
![SQLAlchemy](https://img.shields.io/badge/SQLAlchemy-D71F00?style=for-the-badge&logo=sqlalchemy&logoColor=white)

**Tools and infra**

![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![Git](https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=for-the-badge&logo=githubactions&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black)
![Azure](https://img.shields.io/badge/Azure-0078D4?style=for-the-badge&logo=microsoftazure&logoColor=white)
![Caddy](https://img.shields.io/badge/Caddy-1F88C0?style=for-the-badge&logo=caddy&logoColor=white)

**ML**

![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=for-the-badge&logo=pytorch&logoColor=white)

## Featured project

### [Verdict](https://github.com/Amogh-Koushik/Verdict): online judge for college contests

A self-hosted judge. Users submit C++ or Python solutions, worker processes run them against hidden tests in sandboxed Docker containers, and verdicts and a live ICPC-style scoreboard update in the browser as they're decided.

**What it does**
- Problems with Markdown statements, per-problem time and memory limits, and versioned test archives
- Contests with a countdown, problems hidden until the start, and a live ICPC scoreboard
- Verdicts AC, WA, TLE, MLE, RE, CE and SE, streamed to the browser
- Admin tools for problems, contests, test uploads, rejudging and stats

**How it works**
- **Postgres as the job queue:** workers claim submissions with `FOR UPDATE SKIP LOCKED` and a lease, and writes are fenced on that lease, so a stalled worker can't overwrite newer results. New submissions are judged before rejudges.
- **Sandbox:** a fresh container per submission, with no network, a non-root user, a read-only root filesystem, and CPU, memory and process limits
- **Live updates:** workers signal through Redis pub/sub, and the web processes relay events to browsers over server-sent events
- **Deployment:** Docker Compose on an Azure VM behind Caddy with automatic HTTPS

**Measured:** in load tests of 100 submissions per run, 4 workers judged about 79 submissions a minute on my laptop and about 51 a minute on a 2-vCPU Azure VM, with no wrong verdicts in any run.

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-DC382D?style=flat-square&logo=redis&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![htmx](https://img.shields.io/badge/htmx-3366CC?style=flat-square&logo=htmx&logoColor=white)
![pytest](https://img.shields.io/badge/pytest-0A9EDC?style=flat-square&logo=pytest&logoColor=white)
![Caddy](https://img.shields.io/badge/Caddy-1F88C0?style=flat-square&logo=caddy&logoColor=white)

<sub>I wrote the design and spec and handled the deployment. The code was written with Claude Code, and I'm reviewing it section by section.</sub>

## In progress

### ContestPulse: Codeforces tracker for my coding club

What it will do: members register their Codeforces handles, the app syncs ratings and contest history in the background, and it shows a club leaderboard, rating charts, contest reminders, and a personal upsolve queue that clears itself when a problem gets accepted.

The core challenge is the Codeforces API limit of about one request every two seconds, so the design centres on a job queue, a shared rate limiter, incremental sync and caching. I'm building this one myself, from scratch.

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-DC382D?style=flat-square&logo=redis&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)

## Hackathon and team projects

### [Pratibimb](https://github.com/Amogh-Koushik/Cascade2026): attention digital twin · CASCADE '26

An Android app that, during a focus session, estimates how much each incoming notification will cost your attention. It holds back notifications that pull hard but matter little and releases them at your next break, with every live decision made on the phone. I led our team of four.

![Kotlin](https://img.shields.io/badge/Kotlin-7F52FF?style=flat-square&logo=kotlin&logoColor=white)
![Jetpack Compose](https://img.shields.io/badge/Jetpack_Compose-4285F4?style=flat-square&logo=jetpackcompose&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white)

### [RiskScope AI](https://github.com/Amogh-Koushik/HacksagonFinal2026): emergency triage assistant · Hacksagon 2026

Predicts an Emergency Severity Index level (1 to 5) from patient vitals and symptoms. Hard-coded clinical safety rules override the model for life-threatening patterns, low-confidence predictions are escalated, and SHAP explains each prediction. Built to assist clinicians, not replace them.

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=flat-square&logo=scikitlearn&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white)
![React](https://img.shields.io/badge/React-61DAFB?style=flat-square&logo=react&logoColor=black)
![Supabase](https://img.shields.io/badge/Supabase-3FCF8E?style=flat-square&logo=supabase&logoColor=white)

### [Sol-1](https://github.com/Amogh-Koushik/FinalGDGRepo): Q&A platform for IIIT Nagpur · GDG On Campus

A knowledge-sharing platform for IIIT Nagpur students, open only to `@iiitn.ac.in` accounts. It has difficulty-tiered questions with a credit system, admin moderation, OTP email verification, and a RAG chatbot that answers questions about the college.

![React](https://img.shields.io/badge/React-61DAFB?style=flat-square&logo=react&logoColor=black)
![Node.js](https://img.shields.io/badge/Node.js-5FA04E?style=flat-square&logo=nodedotjs&logoColor=white)
![SQLite](https://img.shields.io/badge/SQLite-003B57?style=flat-square&logo=sqlite&logoColor=white)

<sub>Pratibimb and RiskScope were fast hackathon builds made with heavy use of AI coding assistants.</sub>

## Problem solving

![CodeChef](https://img.shields.io/badge/CodeChef-3%E2%98%85-5B4638?style=for-the-badge&logo=codechef&logoColor=white)

Working through Striver's sheet, Blind 75 and NeetCode 150 in C++.

## Community

- AI/ML Co-Lead, GDG On Campus IIIT Nagpur: presented the team's intro session for first-year students

- Hackathons: CASCADE 2026 (team lead), Hacksagon 2026 (team lead), Smart India Hackathon 2026 (team lead)

## Connect

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/amogh-koushik)
