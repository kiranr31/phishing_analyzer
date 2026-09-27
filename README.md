# PRJ-11: Phishing Detection & Explainable Threat Analyzer

A web-based platform that scores email and SMS content for phishing risk and explains *why* — combining NLP-based ML classification, rule-based heuristics, and SHAP/LIME explainability, instead of returning a plain "Safe / Phishing" label with no reasoning.

**Team project — Chanakya University, MCA (Cyber Security & Deep Learning) — Sept–Nov 2026**

## Why this exists

Most phishing detection tools (spam filters, browser extensions, even modern AI scam checkers) give you a binary verdict with no explanation. Users can't tell *why* something was flagged, don't build any real ability to spot phishing themselves, and end up either ignoring warnings or over-trusting the tool. This project pairs detection with a plain-language explanation of the specific red flags — urgency language, suspicious links, mismatched sender domains, spoofed branding — plus a numeric risk score.

Full writeup: [Week 3 Report](docs/PRJ11_Week3_Report.docx) — problem statement, gap analysis, literature review, and scope.

## What it does

- Accepts pasted or uploaded email/SMS content
- Classifies it as Safe / Suspicious / Phishing with a risk score (0–100)
- Explains the verdict in plain language (SHAP/LIME under the hood)
- Checks embedded URLs against Google Safe Browsing, VirusTotal, and WHOIS domain age
- Keeps a personal scan history dashboard
- Includes a phishing-awareness survey module
- Admin dashboard for aggregate threat trends
- Optional browser extension (stretch goal)

## Tech stack

| Layer | Tools |
|---|---|
| Frontend | React.js, Chart.js/Plotly.js, Tailwind CSS / Material UI |
| Backend | Flask / FastAPI (Python) |
| ML / NLP | scikit-learn, Hugging Face Transformers (BERT), SHAP, LIME |
| Data | PostgreSQL / MongoDB |
| External APIs | Google Safe Browsing, VirusTotal, python-whois |
| Infra | Docker, Git/GitHub, Postman |

## Project structure

```
.
├── frontend/        # React app — scan UI, dashboard, admin panel
├── backend/         # Flask/FastAPI API — auth, scan pipeline, DB models
├── ml/              # Training notebooks, saved models, SHAP/LIME experiments
├── docs/            # SRS, weekly reports, ER diagram
└── README.md
```

Code for `frontend/`, `backend/`, and `ml/` is coming in upcoming weeks as development starts — this repo currently holds project documentation and planning artifacts.

## Datasets & APIs

- Training data: [PhishTank](https://phishtank.org/), [UCI ML Repository](https://archive.ics.uci.edu/) (Phishing Websites, SMS Spam Collection), Kaggle phishing/Enron email datasets
- Threat intel: [Google Safe Browsing API](https://developers.google.com/safe-browsing), [VirusTotal API](https://docs.virustotal.com/)

## Roadmap

| Week | Focus |
|---|---|
| 1–2 | Literature review, requirements, dataset collection |
| 3 | Problem statement, gap analysis, scope, SRS |
| 4 | ML baseline (classical models on structured + text features) |
| 5 | Heuristic rule engine + SHAP/LIME integration |
| 6 | Backend API — auth, scan submission, URL checks |
| 7 | Frontend dashboard |
| 8 | Survey module, admin dashboard |
| 9 | Integration testing, report writing, optional browser extension |

## Docs

- [`docs/PRJ11_SRS.docx`](docs/PRJ11_SRS.docx) — full Software Requirements Specification
- [`docs/PRJ11_Week3_Report.docx`](docs/PRJ11_Week3_Report.docx) — Week 3 report (problem statement, gap ID, lit review, scope)

## License

Academic project — Chanakya University coursework. Not licensed for external reuse at this stage.
