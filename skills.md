# skills.md — Skills, Playbooks & Chat-History Memory

> Companion to `agent.md`. This file lists the skills/capabilities involved in
> the AlertoMarikeño project, step-by-step playbooks for common tasks, and a
> quick-reference memory log so chat history and "how do I…?" answers are easy
> to recall later.

---

## 1. Skills Matrix

What the project requires, and where it shows up.

| Skill area | Used for | Tools / notes |
|------------|----------|---------------|
| Web frontend | Public portal & admin UI | HTML, CSS, JavaScript |
| Web backend | Server-side logic, routing, auth | PHP on Apache |
| Database design | Storing weather, river discharge, predictions, users | MySQL |
| Data engineering | Cleaning historical weather/river data, feature building | Python (pandas) |
| Machine learning | Training & comparing flood-prediction models | Python, scikit-learn, XGBoost |
| Model evaluation | Choosing the best model | F1-score, confusion matrix |
| Geospatial / mapping | Hazard maps for Marikina | Web map layer (frontend) |
| Notifications | Early-warning alerts | SMS gateway + email (SMTP) |
| QA / evaluation | System quality assessment | ISO 25010 (functional suitability, reliability, maintainability) |
| Process | Iterative delivery | Agile methodology |

---

## 2. Playbooks (common tasks)

> These are templates. Fill in exact commands/paths once the source code is
> committed to the repo.

### 2.1 Run the web app locally
1. Start Apache + MySQL (e.g., XAMPP/LAMP or Docker).
2. Place the PHP app under the web root (e.g., `htdocs/` or `/var/www/html`).
3. Import the database schema into MySQL.
4. Copy `config.example.php` to `config.php` and set DB credentials + API keys.
5. Open the site in a browser (e.g., `http://localhost/alertomarikeno`).

### 2.2 Train / re-evaluate the ML model
1. Create a Python env: `python3 -m venv .venv && source .venv/bin/activate`
2. Install deps: `pip install -r requirements.txt`
   (expected: pandas, scikit-learn, xgboost, and optionally catboost, lightgbm)
3. Run the training/evaluation script (compares XGBoost, CatBoost, LightGBM,
   Random Forest, Gradient Boosting by F1-score).
4. Export the chosen XGBoost model artifact for the backend to consume.

### 2.3 Add or update a flood alert (SMS / email)
1. Locate the alert/notification module in the PHP backend.
2. Configure the SMS gateway + SMTP credentials via environment/config (never
   hard-code keys).
3. Trigger on prediction threshold (e.g., predicted flood = positive class).
4. Test with a safe recipient before enabling broadcast.

### 2.4 Update the hazard map
1. Update the map data/overlay for Marikina hazard zones.
2. Verify it renders on the public portal across desktop, tablet, and mobile.

### 2.5 Capture a session into memory
1. At the end of a work session, add an entry to the Session Log in `agent.md`.
2. Add any reusable "how-to" answer to Section 4 below.

---

## 3. Glossary / Key Concepts

- **XGBoost** — eXtreme Gradient Boosting; the selected prediction model.
- **F1-score** — harmonic mean of precision and recall; primary model metric.
- **Confusion matrix** — table of true/false positives/negatives used to assess models.
- **ISO 25010** — software quality model; here focused on functional suitability,
  reliability, and maintainability.
- **River discharge** — volume of water flowing in the river over time; key input feature.
- **PAGASA** — the Philippine weather/hydrology agency; source domain for weather data.

---

## 4. Chat-History Quick Reference (memory log)

> Q&A and decisions worth remembering, newest first. Append as we go.

- **What is this project?** AlertoMarikeño — a web-based flood prediction system
  for Marikina City (Capstone, Group 4, San Beda University, BSIT).
- **Which ML model is used and why?** XGBoost — best F1-score on daily & hourly
  datasets vs. CatBoost, LightGBM, Random Forest, Gradient Boosting.
- **What is the stack?** HTML/CSS/JS frontend, PHP backend on Apache, MySQL
  database, Python + scikit-learn for ML.
- **How is quality measured?** ISO 25010 — functional suitability, reliability,
  maintainability (rated by IT professionals and end users; end-user composite
  mean 4.33 / "Agree").
- **What alert channels exist?** SMS and email early-warning notifications.
- **Why agent.md + skills.md?** To make it easy to remember chat history and
  project context across sessions (requested 2026-05-30).
- **Where are the example images?** `Capstone-Finals/examples/Example 1-7.png`
  (repo root). They were initially uncommitted/untracked, so they did not appear
  on GitHub until committed and pushed on 2026-05-31.
- **What is Draft v3?** A duplicate of the final paper PDF with a revised,
  single-paragraph abstract + keywords placed at the Chapter 1 location:
  `Draft v3 (Grammarian) Group 4 AlertoMarikeno - Final Paper.docx.pdf`.
- **XGBoost concrete scores?** F1 = 0.896 (daily) and 0.891 (hourly); correctly
  flagged Typhoon Ulysses (2020) at ~99.96% and Carina (2024) with near-perfect
  confidence.

<!--
- **[2026-05-30] Q:** ...
  **A:** ...
-->
