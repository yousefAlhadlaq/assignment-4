# Technical Documentation - Portfolio Website

**Project:** Professional Portfolio Website  
**Course:** SWE363 - Web Programming and Applications  
**Student:** Yousef Alhadlaq  
**University:** King Fahd University of Petroleum & Minerals  
**Date:** December 2024

---

## Table of Contents

1. [Project Overview](#1-project-overview)
2. [Technology Stack](#2-technology-stack)
3. [File Structure](#3-file-structure)
4. [HTML Implementation](#4-html-implementation)
5. [CSS Architecture](#5-css-architecture)
6. [JavaScript Functionality](#6-javascript-functionality)
7. [API Integration](#7-api-integration)
8. [State Management](#8-state-management)
9. [Responsive Design](#9-responsive-design)
10. [Performance Optimization](#10-performance-optimization)
11. [Browser Compatibility](#11-browser-compatibility)
12. [Deployment Guide](#12-deployment-guide)
13. [Testing Checklist](#13-testing-checklist)
14. [Troubleshooting](#14-troubleshooting)
15. [Future Improvements](#15-future-improvements)

---

## 1. Project Overview

### Purpose

This portfolio website serves as a professional online presence showcasing my work in cybersecurity, data science, and web development. It was developed as part of Assignment 4 for SWE363.

### Key Features

- Fully responsive design (mobile, tablet, desktop)
- Dark/light theme toggle with preference persistence
- GitHub API integration for real-time repository display
- Project filtering and sorting system
- Contact form with real-time validation
- Animated skill progress bars
- Downloadable CV button
- Visit counter and time-based greetings

### Design Philosophy

The website follows modern web design principles:

- Mobile-first approach
- Clean and minimal interface
- Professional color scheme (purple/blue gradient)
- Smooth animations and transitions
- Accessible and semantic markup

---

## 2. Technology Stack

### Core Technologies

| Technology | Version | Purpose                 |
| ---------- | ------- | ----------------------- |
| HTML5      | -       | Structure and content   |
| CSS3       | -       | Styling and layout      |
| JavaScript | ES6+    | Interactivity and logic |

### APIs Used

| API                       | Purpose                 |
| ------------------------- | ----------------------- |
| GitHub REST API           | Fetch repository data   |
| LocalStorage API          | Save user preferences   |
| Intersection Observer API | Scroll-based animations |

### Development Tools

| Tool            | Purpose               |
| --------------- | --------------------- |
| VS Code         | Code editor           |
| Git             | Version control       |
| GitHub          | Code hosting          |
| GitHub Pages    | Deployment            |
| Chrome DevTools | Testing and debugging |

---

## 3. File Structure

```
assignment-4/
│
├── index.html                    # Main HTML document (469 lines)
│
├── css/
│   └── styles.css               # Complete stylesheet (1600+ lines)
│       ├── Lines 1-84: CSS Variables
│       ├── Lines 85-145: Reset & Base Styles
│       ├── Lines 146-370: Navigation & Header
│       ├── Lines 371-500: Hero Section
│       ├── Lines 501-700: Sections (About, Skills, Projects)
│       ├── Lines 701-1000: Components (Cards, Forms, Buttons)
│       ├── Lines 1001-1300: Animations
│       └── Lines 1301-1600: Responsive Media Queries
│
├── js/
│   └── script.js                # JavaScript functionality (940 lines)
│       ├── Lines 1-25: State Management
│       ├── Lines 26-85: Visit Timer & Greeting
│       ├── Lines 86-140: Theme Toggle
│       ├── Lines 141-200: Mobile Menu
│       ├── Lines 201-380: Project Data & Filtering
│       ├── Lines 381-410: Skills Animation
│       ├── Lines 411-520: GitHub API
│       ├── Lines 521-765: Form Validation
│       └── Lines 766-940: Utilities & Initialization
│
├── assets/
│   ├── images/
│   │   ├── my_personal_photo.JPG
│   │   ├── KFUPM_LOGO.jpg
│   │   ├── cybersecurity.jpg
│   │   ├── Data Science.png
│   │   ├── machinelearning1.jpg
│   │   └── web development.jpeg
│   └── CV.pdf                   # Downloadable resume
│
├── docs/
│   ├── technical-documentation.md   # This file
│   └── ai-usage-report.md          # AI usage documentation
│
├── .gitignore                   # Git ignore rules
└── README.md                    # Project overview
```

---

## 4. HTML Implementation

### Document Structure

The HTML follows semantic HTML5 standards:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <!-- Meta tags, title, CSS link -->
</head>
<body>
  <header>        <!-- Sticky navigation -->
  <div>           <!-- Timer banner -->
  <main>
    <section id="hero">       <!-- Hero with CTA buttons -->
    <section id="about">      <!-- About me & preferences -->
    <section id="skills">     <!-- Skill categories & bars -->
    <section id="projects">   <!-- Filterable projects grid -->
    <section id="github">     <!-- GitHub repos from API -->
    <section id="contact">    <!-- Contact form -->
  </main>
  <footer>        <!-- Copyright & social links -->
  <button>        <!-- Back to top -->
  <script>        <!-- JavaScript -->
</body>
</html>
```

### Semantic Elements Used

| Element     | Purpose                     |
| ----------- | --------------------------- |
| `<header>`  | Site header with navigation |
| `<nav>`     | Navigation menu             |
| `<main>`    | Primary content area        |
| `<section>` | Content sections (6 total)  |
| `<article>` | Project cards               |
| `<footer>`  | Site footer                 |
| `<form>`    | Contact form                |

### Accessibility Features

1. **ARIA Labels**

   - Theme toggle button: `aria-label="Toggle theme"`
   - Mobile menu button: `aria-label="Toggle menu"`
   - Back to top button: `aria-label="Back to top"`

2. **Form Labels**

   - All form inputs have associated `<label>` elements
   - Error messages linked to inputs

3. **Image Alt Text**

   - All images have descriptive alt attributes
   - Profile photo: `alt="Yousef Alhadlaq"`

4. **Heading Hierarchy**
   - Single `<h1>` in hero section
   - `<h2>` for section titles
   - `<h3>` for subsections

---

## 5. CSS Architecture

### CSS Variables System

Located at the top of `styles.css`, variables enable easy theming:

```css
:root {
  /* Colors */
  --primary-color: #667eea;
  --primary-dark: #5a67d8;
  --secondary-color: #764ba2;
  --accent-color: #f093fb;

  /* Text Colors */
  --text-primary: #2d3748;
  --text-secondary: #4a5568;

  /* Background Colors */
  --bg-primary: #ffffff;
  --bg-secondary: #f7fafc;
  --bg-card: #ffffff;

  /* Spacing */
  --spacing-sm: 1rem;
  --spacing-md: 1.5rem;
  --spacing-lg: 2rem;
  --spacing-xl: 3rem;

  /* Typography */
  --font-primary: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto,
    sans-serif;
  --font-size-base: 1rem;
  --font-size-lg: 1.125rem;
  --font-size-xl: 1.25rem;

  /* Shadows */
  --shadow-sm: 0 1px 3px rgba(0, 0, 0, 0.1);
  --shadow-md: 0 4px 6px rgba(0, 0, 0, 0.1);
  --shadow-lg: 0 10px 25px rgba(0, 0, 0, 0.15);

  /* Transitions */
  --transition-fast: 0.15s ease;
  --transition-medium: 0.3s ease;

  /* Border Radius */
  --radius-sm: 0.25rem;
  --radius-md: 0.5rem;
  --radius-lg: 1rem;
}
```

### Dark Theme Implementation

Dark mode overrides the CSS variables:

```css
[data-theme="dark"] {
  --text-primary: #f7fafc;
  --text-secondary: #e2e8f0;
  --bg-primary: #1a202c;
  --bg-secondary: #2d3748;
  --bg-card: #2d3748;
  --border-color: #4a5568;
}
```

### Layout Techniques

1. **CSS Grid** - Used for projects grid

   ```css
   .projects-grid {
     display: grid;
     grid-template-columns: repeat(auto-fill, minmax(320px, 1fr));
     gap: var(--spacing-xl);
   }
   ```

2. **Flexbox** - Used for navigation and cards
   ```css
   .nav-container {
     display: flex;
     justify-content: space-between;
     align-items: center;
   }
   ```

### Animation System

Key animations defined:

```css
@keyframes fadeInUp {
  from {
    opacity: 0;
    transform: translateY(30px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

@keyframes slideDown {
  from {
    transform: translateY(-100%);
  }
  to {
    transform: translateY(0);
  }
}

@keyframes bounce {
  0%,
  100% {
    transform: translateY(0);
  }
  50% {
    transform: translateY(-10px);
  }
}
```

---

## 6. JavaScript Functionality

### State Management

Centralized state object manages all application state:

```javascript
const appState = {
  theme: localStorage.getItem("theme") || "light",
  userLevel: localStorage.getItem("userLevel") || "all",
  visitStartTime: Date.now(),
  visitCount: parseInt(localStorage.getItem("visitCount") || "0") + 1,
  projects: [],
  githubRepos: [],
  formDraft: JSON.parse(localStorage.getItem("formDraft") || "{}"),
  isMobileMenuOpen: false,
};
```

### Theme Toggle

Switches between light and dark modes:

```javascript
themeToggle.addEventListener("click", () => {
  const currentTheme = document.documentElement.getAttribute("data-theme");
  const newTheme = currentTheme === "dark" ? "light" : "dark";

  if (newTheme === "dark") {
    document.documentElement.setAttribute("data-theme", "dark");
  } else {
    document.documentElement.removeAttribute("data-theme");
  }

  localStorage.setItem("theme", newTheme);
});
```

### Project Filtering & Sorting

Filters and sorts projects based on user selection:

```javascript
function applyFiltersAndSort() {
  let filteredProjects = [...appState.projects];

  // Apply category filter
  if (selectedCategory !== "all") {
    filteredProjects = filteredProjects.filter(
      (p) => p.category === selectedCategory
    );
  }

  // Apply user level filter
  if (appState.userLevel !== "all") {
    filteredProjects = filteredProjects.filter(
      (p) => p.level === appState.userLevel
    );
  }

  // Apply sorting
  filteredProjects.sort((a, b) => {
    switch (sortValue) {
      case "date-desc":
        return b.date.localeCompare(a.date);
      case "date-asc":
        return a.date.localeCompare(b.date);
      case "name-asc":
        return a.name.localeCompare(b.name);
      case "name-desc":
        return b.name.localeCompare(a.name);
    }
  });

  renderProjects(filteredProjects);
}
```

### Form Validation

Real-time validation with visual feedback:

```javascript
const validationRules = {
  name: {
    required: true,
    minLength: 2,
    maxLength: 50,
    pattern: /^[a-zA-Z\s]+$/,
    message: "Name must be 2-50 characters, letters only",
  },
  email: {
    required: true,
    pattern: /^[^\s@]+@[^\s@]+\.[^\s@]+$/,
    message: "Please enter a valid email address",
  },
  subject: {
    required: true,
    minLength: 5,
    maxLength: 100,
    message: "Subject must be 5-100 characters",
  },
  message: {
    required: true,
    minLength: 10,
    maxLength: 1000,
    message: "Message must be 10-1000 characters",
  },
};
```

---

## 7. API Integration

### GitHub API Configuration

```javascript
const GITHUB_USERNAME = "yousefalhadlaq";
const GITHUB_API_URL = `https://api.github.com/users/${GITHUB_USERNAME}/repos`;
```

### Fetch Implementation

```javascript
async function fetchGitHubRepos() {
  try {
    const response = await fetch(`${GITHUB_API_URL}?sort=updated&per_page=6`);

    if (!response.ok) {
      throw new Error(`GitHub API error: ${response.status}`);
    }

    const repos = await response.json();

    // Calculate statistics
    const stats = repos.reduce(
      (acc, repo) => ({
        stars: acc.stars + (repo.stargazers_count || 0),
        forks: acc.forks + (repo.forks_count || 0),
      }),
      { stars: 0, forks: 0 }
    );

    // Update UI
    renderRepositories(repos);
    updateStats(stats);
  } catch (error) {
    console.error("Error fetching GitHub repos:", error);
    displayErrorMessage();
  }
}
```

### Rate Limiting

- GitHub API allows 60 requests/hour for unauthenticated requests
- Error handling displays fallback message when limit exceeded
- API call deferred until user scrolls to GitHub section

---

## 8. State Management

### LocalStorage Usage

| Key          | Purpose                      | Type   |
| ------------ | ---------------------------- | ------ |
| `theme`      | User's theme preference      | string |
| `userLevel`  | Preferred project difficulty | string |
| `visitCount` | Number of site visits        | number |
| `formDraft`  | Auto-saved form content      | object |

### Saving Data

```javascript
// Save theme preference
localStorage.setItem("theme", "dark");

// Save complex objects
localStorage.setItem(
  "formDraft",
  JSON.stringify({
    name: "John",
    email: "john@email.com",
    subject: "Hello",
    message: "Draft message...",
    timestamp: Date.now(),
  })
);
```

### Retrieving Data

```javascript
// Get simple values with fallback
const theme = localStorage.getItem("theme") || "light";

// Get and parse objects
const draft = JSON.parse(localStorage.getItem("formDraft") || "{}");
```

---

## 9. Responsive Design

### Breakpoints

| Breakpoint       | Target Devices           |
| ---------------- | ------------------------ |
| Default          | Desktop (1200px+)        |
| max-width: 992px | Tablet landscape         |
| max-width: 768px | Tablet portrait / Mobile |
| max-width: 480px | Small mobile             |

### Media Query Examples

```css
/* Tablet */
@media (max-width: 992px) {
  .hero-title {
    font-size: 2.5rem;
  }
  .projects-grid {
    grid-template-columns: repeat(2, 1fr);
  }
}

/* Mobile */
@media (max-width: 768px) {
  .nav-links {
    display: none;
  }
  .mobile-menu-btn {
    display: flex;
  }
  .projects-grid {
    grid-template-columns: 1fr;
  }
  .about-content {
    flex-direction: column;
  }
}

/* Small Mobile */
@media (max-width: 480px) {
  :root {
    --spacing-xl: 2rem;
    --font-size-4xl: 2rem;
  }
  .hero-cta {
    flex-direction: column;
  }
}
```

### Mobile Menu

```css
.mobile-menu {
  display: none;
  position: fixed;
  top: 70px;
  left: 0;
  right: 0;
  max-height: 0;
  overflow: hidden;
  transition: max-height 0.3s ease;
}

.mobile-menu.active {
  max-height: 500px;
}
```

---

## 10. Performance Optimization

### Implemented Optimizations

1. **Lazy Loading Images**

   - Project images use `loading="lazy"` attribute
   - Images load only when entering viewport

2. **Deferred Script Loading**

   - JavaScript loads with `defer` attribute
   - Doesn't block HTML parsing

3. **CSS Preloading**

   - Critical CSS preloaded in `<head>`
   - Faster initial render

4. **Intersection Observer**

   - Animations trigger only when visible
   - GitHub API loads when section is visible

5. **Content Visibility**
   - Below-the-fold sections use `content-visibility: auto`
   - Browser skips rendering off-screen content

### Performance Targets

| Metric                         | Target |
| ------------------------------ | ------ |
| LCP (Largest Contentful Paint) | < 2.5s |
| FCP (First Contentful Paint)   | < 1.5s |
| Total Page Size                | < 2MB  |

---

## 11. Browser Compatibility

### Supported Browsers

| Browser       | Minimum Version |
| ------------- | --------------- |
| Chrome        | 90+             |
| Firefox       | 88+             |
| Safari        | 14+             |
| Edge          | 90+             |
| iOS Safari    | 14+             |
| Chrome Mobile | 90+             |

### Features Used (All Well-Supported)

- CSS Grid
- CSS Flexbox
- CSS Variables
- CSS Animations
- Fetch API
- Async/Await
- Intersection Observer
- LocalStorage

---

## 12. Deployment Guide

### Prerequisites

- GitHub account
- Git installed locally
- Repository created on GitHub

### Deployment Steps

1. **Initialize Git Repository**

   ```bash
   git init
   git add .
   git commit -m "Initial commit"
   ```

2. **Connect to GitHub**

   ```bash
   git remote add origin https://github.com/username/assignment-4.git
   git branch -M main
   git push -u origin main
   ```

3. **Enable GitHub Pages**

   - Go to repository Settings
   - Navigate to Pages section
   - Select source: main branch
   - Click Save
   - Wait 2-3 minutes

4. **Access Live Site**
   - URL: `https://username.github.io/assignment-4/`

---

## 13. Testing Checklist

### Functionality Testing

| Feature              | Status |
| -------------------- | ------ |
| Navigation links     | ☐      |
| Theme toggle         | ☐      |
| Mobile menu          | ☐      |
| Project filtering    | ☐      |
| Project sorting      | ☐      |
| GitHub API loading   | ☐      |
| Form validation      | ☐      |
| Form auto-save       | ☐      |
| CV download          | ☐      |
| Back to top button   | ☐      |
| Smooth scrolling     | ☐      |
| Skill bar animations | ☐      |

### Responsive Testing

| Device              | Status |
| ------------------- | ------ |
| Desktop (1920x1080) | ☐      |
| Laptop (1366x768)   | ☐      |
| Tablet (768x1024)   | ☐      |
| Mobile (375x667)    | ☐      |

### Browser Testing

| Browser | Status |
| ------- | ------ |
| Chrome  | ☐      |
| Firefox | ☐      |
| Safari  | ☐      |
| Edge    | ☐      |

---

## 14. Troubleshooting

### Common Issues & Solutions

**Issue:** GitHub repos not loading

- Check internet connection
- Verify GitHub username is correct
- Check browser console for errors
- Wait if rate limit exceeded (60 requests/hour)

**Issue:** Images not displaying

- Verify image paths are correct
- Check file extensions match exactly (case-sensitive)
- Ensure images exist in assets/images folder

**Issue:** Mobile menu not working

- Check JavaScript is loaded
- Verify no console errors
- Clear browser cache

**Issue:** Theme not saving

- Check localStorage is enabled
- Clear browser data and try again
- Check for JavaScript errors

**Issue:** Form validation not showing

- Verify input IDs match JavaScript selectors
- Check validation functions are called
- Test with different input values

---

## 15. Future Improvements

### Planned Enhancements

- [ ] Add backend for contact form (Node.js)
- [ ] Implement actual email sending
- [ ] Add blog section
- [ ] Individual project detail pages
- [ ] Search functionality
- [ ] Multi-language support
- [ ] More micro-animations
- [ ] Testimonials section

### Technical Improvements

- [ ] Add unit tests
- [ ] Implement CI/CD pipeline
- [ ] Add service worker for offline support
- [ ] Optimize images with WebP format
- [ ] Add structured data (JSON-LD)

---

**Document Version:** 1.0  
**Last Updated:** December 2024  
**Author:** Yousef Alhadlaq
