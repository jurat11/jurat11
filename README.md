<h1 align="center">Jurat Nortojiev</h1>

<p align="center">
  <em>developer · thinker · questioner</em><br>
  Building products at the intersection of software, education, and curiosity.
</p>

<p align="center">
  <a href="https://juratnortojiev.us"><img alt="Website" src="https://img.shields.io/badge/juratnortojiev.us-E75E24?style=for-the-badge&logo=googlechrome&logoColor=white"></a>
  <a href="https://www.linkedin.com/in/jur-at-nortojiyev-5399b034a/"><img alt="LinkedIn" src="https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white"></a>
  <a href="https://x.com/JuratNortojiev"><img alt="X" src="https://img.shields.io/badge/@JuratNortojiev-000000?style=for-the-badge&logo=x&logoColor=white"></a>
  <a href="https://instagram.com/jurat1_"><img alt="Instagram" src="https://img.shields.io/badge/@jurat1__-E4405F?style=for-the-badge&logo=instagram&logoColor=white"></a>
  <a href="https://t.me/jurat1"><img alt="Telegram" src="https://img.shields.io/badge/@jurat1-26A5E4?style=for-the-badge&logo=telegram&logoColor=white"></a>
</p>

---

### Selected work

Everything here is live — click and it opens.

| | What it is | Live |
|---|---|---|
| **MARGINAL** | What your next dollar of retirement income actually costs, once Social Security taxation, capital gains stacking, the senior deduction phase-out and Medicare's IRMAA cliffs are all counted. A Rust tax engine compiled to WebAssembly: the arithmetic runs in your browser and your figures never leave it. | [marginal-sand.vercel.app](https://marginal-sand.vercel.app) |
| **Footnote** | An AI agent that reads a public company's SEC filings and writes an analysis where every number is cited to the exact filing it came from, and machine-verified. The language model never produces a number: Python builds a fact ledger, the model refers to facts by token, and a verifier rejects any figure that is not cited. | [demo](https://footnote-jurat.vercel.app) · [live](https://footnote.streamlit.app) |
| **KLIMB** | Digital SAT prep. A tagged question bank, per-skill mastery measured from a student's own attempts, and a study plan built backwards from their test date. | [quiet-study-three.vercel.app](https://quiet-study-three.vercel.app) |
| **Jurat OS** | A personal life OS — net worth that updates itself from live metal and equity prices, budgets, habits, tasks, and a Telegram bot that logs an expense from one sentence. | [jurat-os.vercel.app](https://jurat-os.vercel.app) |
| **PolyaBor** | Find and book football pitches across Uzbekistan. Search by time and neighbourhood, hold a slot, confirm in Telegram. | [polya-bor.vercel.app](https://polya-bor.vercel.app) |
| **NAV** | A guide to Uzbekistan's startup ecosystem: who is building what, which funds are active, where a founder actually starts. | [nav-international.vercel.app](https://nav-international.vercel.app) |
| **Agora Aid Program** | A full-scholarship admissions programme for the Class of 2031 — deliberately no framework, no build step, no dependencies. | [agora-aid.vercel.app](https://agora-aid.vercel.app) |
| **BiteWise** | Nutrition tracking that starts from what you actually ate: describe the meal, get the macros. | [v0-nutrition-info-app.vercel.app](https://v0-nutrition-info-app.vercel.app) |
| **NAVON Agency** | Brand and site for a creative agency — one long scroll that has to carry the whole pitch. | [navon-agency.vercel.app](https://navon-agency.vercel.app) |

---

### MARGINAL, in a bit more detail

Ask most retirees their tax rate and they name a bracket. That number is close to
meaningless: four separate mechanisms act on the same dollar at once, and a 12%
bracket can behave like 22.2%. One dollar over $109,000 of income raises a
Medicare premium by $974.40 for the year — a cliff, not a rate.

[MARGINAL](https://github.com/jurat11/marginal) draws that curve. The engine is
Rust compiled to 57 KB of WebAssembly; the page is one HTML file, one stylesheet
and one script, with no framework and no third-party code. There is no backend,
so there is nowhere for your numbers to go.

The part I care about is the proof. An independent Python implementation of the
same rules agrees with the engine to the cent across 200,000 randomised inputs,
every constant is traced to the IRS revenue procedure or the CMS notice it came
from, and CI re-runs all of it — including the exact WebAssembly a browser
downloads — on every push.

---

### Footnote, in a bit more detail

Financial write-ups are full of numbers you are asked to trust. Footnote refuses
that. It reads a company's SEC XBRL filings, builds a fact ledger in Python, and
lets the language model write the analysis using only tokens that point at ledger
facts — never a digit of its own. A renderer swaps each token for the value and a
footnote to the filing; a verifier then scans the prose, and any number that did
not come from a token gets the report rejected and rewritten.

[Footnote](https://github.com/jurat11/footnote) runs at zero API cost by default —
the writer is a deterministic engine, so the whole thing works with no paid key,
and drops in a real LLM the moment one exists. The proof is the same instinct as
MARGINAL: across a 25-company universe every report passes verification with zero
uncited numbers, and an independent second pass re-fetches every figure through a
different SEC endpoint and finds zero mismatches.

Two front doors: the [demo](https://footnote-jurat.vercel.app) is an instant,
always-on static page showing ten pre-built reports, and the
[live app](https://footnote.streamlit.app) analyzes any US-listed company on demand.

---

### The site is half the point

[juratnortojiev.us](https://juratnortojiev.us) isn't a CV in a template. It's the thing I keep rebuilding
when I want to learn something, and most of it is worth a click on its own:

- **[The Library](https://juratnortojiev.us/library)** — 42 books on a bookshelf you walk in 3D. Pull a spine, read its story. Every cover is the real edition.
- **[The Gallery](https://juratnortojiev.us/gallery)** — an infinite, draggable WebGL wall of public-domain masterpieces from the Met.
- **[Films](https://juratnortojiev.us/films)** — what I've watched, rated and ranked, synced from Letterboxd.
- **[Encyclopedia](https://juratnortojiev.us/encyclopedia)** — every page, book, film and project on the site as one searchable graph. `⌘K` from anywhere.

Built with Vite, React and react-three-fiber, and tuned to stay fast under all of it:
three.js loads only on the routes that render 3D, posters ship as WebP, and offscreen
rows skip layout entirely.

---

### What I reach for

<p>
  <img alt="Rust" src="https://img.shields.io/badge/Rust-000000?style=flat-square&logo=rust&logoColor=white">
  <img alt="WebAssembly" src="https://img.shields.io/badge/WebAssembly-654FF0?style=flat-square&logo=webassembly&logoColor=white">
  <img alt="TypeScript" src="https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white">
  <img alt="React" src="https://img.shields.io/badge/React-20232A?style=flat-square&logo=react&logoColor=61DAFB">
  <img alt="Next.js" src="https://img.shields.io/badge/Next.js-000000?style=flat-square&logo=nextdotjs&logoColor=white">
  <img alt="Vite" src="https://img.shields.io/badge/Vite-646CFF?style=flat-square&logo=vite&logoColor=white">
  <img alt="Three.js" src="https://img.shields.io/badge/three.js-000000?style=flat-square&logo=threedotjs&logoColor=white">
  <img alt="Tailwind CSS" src="https://img.shields.io/badge/Tailwind-06B6D4?style=flat-square&logo=tailwindcss&logoColor=white">
  <img alt="Python" src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white">
  <img alt="PostgreSQL" src="https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white">
  <img alt="Supabase" src="https://img.shields.io/badge/Supabase-3FCF8E?style=flat-square&logo=supabase&logoColor=white">
  <img alt="Telegram" src="https://img.shields.io/badge/Telegram%20Bots-26A5E4?style=flat-square&logo=telegram&logoColor=white">
  <img alt="Vercel" src="https://img.shields.io/badge/Vercel-000000?style=flat-square&logo=vercel&logoColor=white">
</p>

---

### Currently

- Writing a retirement tax engine in Rust that has to agree with a second implementation to the cent — **[MARGINAL](https://github.com/jurat11/marginal)**
- Teaching a question bank to work out what a student actually doesn't know yet — **KLIMB**
- Running my own life off a dashboard and a Telegram bot — **Jurat OS**
- Reading the Uzbek classics alongside the canon, in public → [the library](https://juratnortojiev.us/library)
- Working through *The Sopranos* → [what else I've watched](https://juratnortojiev.us/films)

### Reach me

Email is best: **juratjushkinovich@gmail.com** — or any of the badges up top.
I read every message.

<p align="center"><sub>Salem, Virginia · building on the web</sub></p>
