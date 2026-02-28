# 🧠 AI Domain Intelligence Quiz

A psychological profiling tool that helps aspiring AI engineers discover which industry domain they're best suited for — based on instincts, values, and thinking style rather than technical knowledge.

## 🎯 What It Does

Most career quizzes ask you directly what you like. This one doesn't.

It uses **20 indirect psychological questions** — probing things like what failures bother you, what headlines grab your attention, what teams energize you, and what kind of legacy matters to you — to map your psychology to one of six high-demand AI engineering domains.

At the end, you receive:
- A **personal archetype** (e.g. *The Systems Strategist*, *The Empathetic Engineer*) with a detailed description of your thinking style
- A **ranked list of all 6 AI domains** scored against your answers with match percentages

---

## 🗂️ Domains Covered

| Domain | Focus Areas |
|---|---|
| 🟣 **Fintech & Finance AI** | Fraud detection, trading algorithms, risk modeling, financial advisors |
| 🟢 **Healthcare & Biotech AI** | Clinical tools, drug discovery, diagnostics, medical imaging |
| 🟠 **Legal Tech AI** | Contract analysis, legal research, compliance automation, due diligence |
| 🩷 **Enterprise SaaS AI** | Productivity copilots, workflow automation, AI product features |
| 💚 **Climate Tech AI** | Energy optimization, carbon accounting, grid management |
| 🟡 **Defense & Government AI** | Intelligence analysis, logistics, security systems |

---

## ✨ Features

- **20 indirect questions** — no obvious right answers, designed to surface genuine instincts
- **Psychological archetype system** — 6 distinct engineer personality profiles
- **Scored domain ranking** — all 6 domains ranked by match percentage
- **Animated UI** — smooth transitions, progress tracking, responsive layout
- **Zero dependencies** — pure HTML, CSS, and vanilla JavaScript
- **Single file** — the entire app lives in one `index.html` file

---

## 🚀 Getting Started

### Option 1 — Open Directly
Just download `index.html` and open it in any modern browser. No server needed.

```bash
git clone https://github.com/AvijatChahar/AI-Domain-Assessment-Test/
cd AI-Domain-Assessment-Test
open index.html   # macOS
# or double-click the file in your file explorer
```

### Option 2 — Serve Locally
If you prefer a local server:

```bash
# Using Python
python -m http.server 8000

# Using Node.js (npx)
npx serve .
```
---

## 📁 Project Structure

```
ai-domain-quiz/
│
├── index.html        # The entire application (HTML + CSS + JS)
└── README.md         # This file
```

Everything is intentionally kept in a single file for maximum portability. No build step, no bundler, no framework.

---

## 🎨 Design Decisions

- **Dark theme** with a deep navy/black base (`#0a0a0f`) for a professional, technical aesthetic
- **Typography**: [Syne](https://fonts.google.com/specimen/Syne) (display) + [DM Mono](https://fonts.google.com/specimen/DM+Mono) (body) — loaded from Google Fonts
- **Color system**: CSS custom properties for consistent theming across all components
- **Scoring**: Each answer distributes weighted points across relevant domains. Questions are designed so multiple domains can score simultaneously — the ranking reflects relative affinity, not binary yes/no matching.

---

## 🧩 How the Scoring Works

Each answer option carries a `scores` object that distributes points to one or more domains:

```js
{
  text: "Reading about how markets or economies work",
  scores: { fintech: 3, enterprise: 1 }
}
```

After all 20 questions, each domain's total is normalized against the highest-scoring domain to produce a percentage. The domain with the most points wins the top rank.

This means the results reflect **relative strength of fit**, not absolute scores — so even a 60% match on your top domain tells you something meaningful about your priorities.

---

## 🛠️ Customization

Want to add questions, domains, or archetypes? Everything is data-driven.

**Add a question** — append to the `questions` array in the `<script>` tag:
```js
{
  text: "Your question here",
  options: [
    { text: "Option A", scores: { fintech: 2 } },
    { text: "Option B", scores: { health: 3 } },
    { text: "Option C", scores: { legal: 1, enterprise: 1 } },
    { text: "Option D", scores: { climate: 2 } }
  ]
}
```

**Add a domain** — add an entry to the `domains` object and a corresponding entry in the `archetypes` array, then reference the new key in question scores.

---

## 🤝 Contributing

Contributions are welcome. Some ideas for extension:

- Add a shareable results URL (encode answers as query params)
- Add a "What to learn next" section per domain result
- Localization / multi-language support
- Export results as PDF or image card

To contribute, fork the repo, make your changes on a feature branch, and open a pull request.

---

## 📄 License

MIT License — free to use, modify, and distribute.

---

## 🙏 Acknowledgements

Built as part of a broader exploration into AI engineering career paths across Fintech, Healthcare, Legal Tech, Enterprise SaaS, Climate Tech, and Defense. Quiz methodology inspired by indirect psychological profiling techniques used in vocational aptitude research.

---

*Made with intention. Not a personality test — a thinking-style map.*
