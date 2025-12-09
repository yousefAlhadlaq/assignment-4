# Portfolio Website - Assignment 4

**Course:** SWE363 - Web Programming  
**Student:** Yousef Alhadlaq  
**University:** KFUPM

## Live Demo

[View the website here](https://yourusername.github.io/assignment-4/)  
_(Update this link once you deploy)_

## What This Is

A personal portfolio website I built for SWE363. It shows off my work in cybersecurity and data science, and includes a bunch of interactive features.

## Main Features

- Responsive design (works on phones, tablets, desktop)
- Dark/Light mode toggle
- Project filtering and sorting
- GitHub repos pulled from the API
- Contact form with real-time validation
- Animated skill bars
- CV download button

## Tech Stack

Just the basics:

- HTML5
- CSS3 (with Grid and Flexbox)
- Vanilla JavaScript
- GitHub API

## Getting Started

1. Clone the repo
2. Open `index.html` in your browser

That's it. No build step needed.

For a better dev experience, run a local server:

```bash
python -m http.server 8000
```

## Project Structure

```
assignment-4/
├── index.html
├── css/styles.css
├── js/script.js
├── assets/
│   ├── images/
│   └── CV.pdf
└── docs/
    ├── technical-documentation.md
    └── ai-usage-report.md
```

## Customization

### Change Colors

Edit the CSS variables at the top of `styles.css`:

```css
:root {
  --primary-color: #667eea;
  --secondary-color: #764ba2;
}
```

### Update GitHub Username

In `script.js`, find:

```javascript
const GITHUB_USERNAME = "yousefalhadlaq";
```

### Add Your Own Projects

Look for the `projectsData` array in `script.js` and add your projects there.

## Deployment

1. Push to GitHub
2. Go to Settings → Pages
3. Select the main branch
4. Wait a couple minutes
5. Your site is live!

## Known Limitations

- GitHub API has a rate limit (60 requests/hour if not authenticated)
- Contact form doesn't actually send emails (no backend)
- You need to add your own CV.pdf file

## AI Usage

I used Claude AI to help with development. Full details in `docs/ai-usage-report.md`.

## Credits

- KFUPM for the education
- SWE363 course staff
- GitHub for the API
