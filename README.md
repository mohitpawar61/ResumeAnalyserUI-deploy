# ResumeIQ — AI Resume Intelligence (Frontend)

A lightweight, dependency-free web interface for the [ResumeAnalyser](https://github.com/mohitpawar61/ResumeAnalyser-Gemini) API. Upload a resume, get an instant AI-powered quality review or run an ATS keyword match against a job description — no build tools, no frameworks, just HTML, CSS, and JavaScript.

**Live demo:**(https://resume-analyser-ui-deploy.vercel.app/)

---

## Features

- 📄 Drag-and-drop resume upload (PDF, DOCX, TXT, RTF)
- ✦ **Resume Review mode** — key skills, quality score (1–10), and 3 targeted improvement suggestions
- ⊕ **ATS Match mode** — paste a job description and get a 0–100 match score with matched/missing keywords
- 📊 Animated score gauge and structured result cards
- 📋 One-click copy of the raw analysis
- Zero build step — plain HTML/CSS/JS, deployable anywhere static files are served

## Tech Stack

| Layer | Technology |
|---|---|
| Markup | HTML5 |
| Styling | Vanilla CSS (custom properties, no framework) |
| Logic | Vanilla JavaScript (fetch API, no dependencies) |
| Fonts | Playfair Display, Plus Jakarta Sans, Space Mono (Google Fonts) |

## Project Structure

```
ResumeAnalyserUI/
├── index.html      # App shell — sidebar, upload zone, controls, results panel
├── style.css        # All styling
└── script.js        # App logic — upload handling, API calls, result rendering
```

## Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/mohitpawar61/ResumeAnalyserUI.git
cd ResumeAnalyserUI
```

### 2. Point it at your backend

Open `script.js` and set `API_BASE` to your running [ResumeAnalyser](https://github.com/mohitpawar61/ResumeAnalyser-Gemini) backend URL:

```js
const API_BASE = "https://your-backend-url.run.app/api/resume";
```

### 3. Run it locally

No build step required — just open `index.html` in a browser, or serve the folder with any static server:

```bash
npx serve .
```

## Deployment

Since this is a static site with no build process, it deploys instantly on any static host:

- **Netlify** — drag-and-drop the folder under *Deploy manually*, or connect the repo for auto-deploys
- **Vercel** — import the repo and set the Framework Preset to **Other** (no build command needed)
- **GitHub Pages** — enable Pages on this repo, serving from the `main` branch root

## API Contract

This UI expects the backend to expose:

| Endpoint | Method | Body | Returns |
|---|---|---|---|
| `/api/resume/analyze` | `POST` | `file` (multipart) | `{ "analysis": "<json string>" }` |
| `/api/resume/ats-check` | `POST` | `file`, `jd` (multipart) | `{ "atsReport": "<json string>" }` |

See the [backend repo](https://github.com/mohitpawar61/ResumeAnalyser-Gemini) for full API details.

## License

This project is for educational and personal portfolio use.

## Author

**Mohit Pawar**
- GitHub: [@mohitpawar61](https://github.com/mohitpawar61)
