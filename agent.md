# agent.md — Project Context & Memory

> Purpose: This file is the single source of truth that an AI assistant (or a
> teammate) should read first when working on this repository. It captures what
> the project is, how it is built, the conventions we follow, and a running log
> of decisions and chat history so context is never lost between sessions.

---

## 1. Project at a Glance

- **Name:** AlertoMarikeño
- **Title:** A Web-Based Flood Prediction System for Marikina City
- **Type:** Capstone Project — Bachelor of Science in Information Technology (BSIT)
- **Institution:** San Beda University – Manila, Department of Information Technology
- **Group:** Group 4
- **Adviser / Professor:** Rosemarie M. Perreras (co-adviser: Jennifer T. Carpio)

### Team
| Member | Name |
|--------|------|
| 1 | Francisco, Mark Vincent E. |
| 2 | Santos, Jerald Dontierro P. |
| 3 | Santos, Alexis D. |
| 4 | Tallungan, Kurt Harry T. |

### One-line summary
A localized, data-driven disaster risk reduction web app that gives Marikina
residents real-time river level monitoring, machine-learning-based flood
prediction, hazard mapping, and alerts via SMS and email.

---

## 2. Goals & Objectives

**General objective:** Design and develop a web-based flood prediction
application that predicts future flood occurrences in Marikina City.

**Specific objectives:**
1. Design and develop the web-based flood prediction application.
2. Test the most capable prediction algorithm for flood risk based on river
   discharge and weather data.
3. Apply the chosen algorithm (XGBoost) for flood prediction, evaluated by F1-score.
4. Evaluate the system for functional suitability, reliability, and
   maintainability using the ISO 25010 software quality model.

---

## 3. Core Features

- Real-time river level / river discharge monitoring
- Machine-learning-based flood prediction (daily and hourly datasets)
- Hazard mapping for Marikina City
- Alerts and early warning via **SMS** and **email**
- Evacuation center information
- Community forum
- Public-facing portal + administrator dashboard

---

## 4. Tech Stack

| Layer | Technology |
|-------|------------|
| Frontend | HTML, CSS, JavaScript |
| Backend / server-side | PHP |
| Web server | Apache |
| Database | MySQL (relational) — stores historical weather & river discharge data and prediction records |
| Machine learning | Python + scikit-learn |
| ML models evaluated | XGBoost (selected), CatBoost, LightGBM, Random Forest, Gradient Boosting |
| Evaluation framework | ISO 25010 Software Quality Model |
| Methodology | Agile software development |

### Why XGBoost
XGBoost (eXtreme Gradient Boosting) achieved the highest F1 scores on both the
daily-based and hourly-based datasets, correctly identifying past major flood
events (e.g., Typhoon Ulysses/Vamco, Typhoon Carina/Gaemi) and translating
weather data into actionable alerts.

---

## 5. Repository Structure

```
Capstone-Finals/
├── README.md
├── agent.md      <- this file (project context + memory)
├── skills.md     <- skills matrix + task playbooks + chat-history log
└── Draft v2 (Grammarian) Group 4 AlertoMarikeno - Final Paper.docx.pdf
```

> Note: As of the latest session this repo contains the final paper and docs.
> When source code (PHP app, ML notebooks/scripts, SQL schema) is added, update
> the structure above and the relevant playbooks in `skills.md`.

---

## 6. Conventions & Guidance for the Agent

- **Read this file first**, then `skills.md`, before making changes.
- Keep the project's official name spelled **AlertoMarikeño** in user-facing
  text; `AlertoMarikeno` (no ñ) is acceptable in file names and identifiers.
- Prefer small, reviewable changes. Push to a branch and open a PR rather than
  committing to `main` directly.
- Do not commit secrets (DB credentials, SMS/email API keys). Use environment
  variables or a local config file that is git-ignored.
- When adding code, document how to run it in `skills.md` under Playbooks.
- Update the Decision Log and Session Log (below) whenever a notable decision is
  made or a session ends.

---

## 7. Decision Log

| Date | Decision | Rationale |
|------|----------|-----------|
| 2026-05-30 | Use XGBoost as the production prediction model | Best F1 score on daily & hourly datasets vs. CatBoost, LightGBM, Random Forest, Gradient Boosting |
| 2026-05-30 | Evaluate quality with ISO 25010 (functional suitability, reliability, maintainability) | Required by capstone; gives a structured, citable assessment |
| 2026-05-30 | Added `agent.md` and `skills.md` as persistent context/memory files | Make it easy to remember project context and chat history across sessions |

---

## 8. Session Log (chat history memory)

> Append a short entry at the end of each working session. Keep it factual:
> what was discussed, what changed, and what is next.

### 2026-05-30 — Session 1
- **Discussed:** Adding `agent.md` and `skills.md` to the repo to help easily
  remember chat history and project context.
- **Context established:** Project is AlertoMarikeño, a web-based flood
  prediction system for Marikina City (Group 4, San Beda University, BSIT).
  Stack = HTML/CSS/JS + PHP + MySQL + Apache; ML in Python/scikit-learn with
  XGBoost selected; evaluated via ISO 25010.
- **Changed:** Created `agent.md` and `skills.md`.
- **Next:** Add application source code and ML scripts to the repo, then expand
  the playbooks and structure sections.

<!--
### YYYY-MM-DD — Session N
- Discussed:
- Changed:
- Next:
-->
