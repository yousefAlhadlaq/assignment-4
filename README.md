# Professional Portfolio Website

**Course:** SWE363 - Web Programming and Applications  
**Student:** Yousef Alhadlaq  
**University:** King Fahd University of Petroleum & Minerals (KFUPM)  
**Semester:** Fall 2024

---

## Live Demo

**GitHub Pages URL:** [https://yousefalhadlaq.github.io/assignment-4/](https://yousefalhadlaq.github.io/assignment-4/)

---

## Table of Contents

1. [Project Overview](#project-overview)
2. [Features](#features)
3. [Technology Stack](#technology-stack)
4. [Project Structure](#project-structure)
5. [Getting Started](#getting-started)
6. [Deployment Guide](#deployment-guide)
7. [Customization](#customization)
8. [Browser Compatibility](#browser-compatibility)
9. [Assignment Requirements](#assignment-requirements)
10. [Known Issues](#known-issues)
11. [Documentation](#documentation)
12. [Credits](#credits)

---

## Project Overview

This is a professional portfolio website I built for SWE363 Assignment 4. It showcases my work in cybersecurity, data science, and web development with a modern, responsive design.

The website improves on Assignment 3 with better UI/UX design, smooth animations, mobile-first responsive layout, and professional documentation.

### Design Philosophy

- Clean, minimal interface
- Professional color scheme with purple and blue gradients
- Smooth animations and transitions
- Mobile-first approach
- Accessible and semantic markup

---

## Features

### Core Features

| Feature            | Description                                             |
| ------------------ | ------------------------------------------------------- |
| Responsive Design  | Optimized for mobile, tablet, and desktop devices       |
| Dark/Light Theme   | Toggle between themes, preference saved in localStorage |
| CV Download        | Button to download my resume as PDF                     |
| GitHub Integration | Real-time display of my GitHub repositories             |
| Smooth Scrolling   | Seamless navigation between sections                    |
| Mobile Navigation  | Hamburger menu with smooth animations                   |

### Advanced Features

| Feature             | Description                                                     |
| ------------------- | --------------------------------------------------------------- |
| Animated Skills     | Progress bars that animate when scrolled into view              |
| Project Filtering   | Filter projects by category (cybersecurity, data science, etc.) |
| Project Sorting     | Sort by date or name (ascending/descending)                     |
| User Preferences    | Saves filter selections across sessions                         |
| Form Validation     | Real-time validation with visual feedback                       |
| Auto-save Drafts    | Contact form saves drafts automatically                         |
| Visit Counter       | Tracks visits and displays personalized messages                |
| Time-based Greeting | Changes based on time of day                                    |
| Back to Top         | Button to quickly scroll back to page top                       |

### Design Elements

- Modern gradient color palette
- Clean typography with proper hierarchy
- Consistent spacing using CSS variables
- Subtle shadows for visual depth
- Hover effects and transitions
- ARIA labels for accessibility

---

## Technology Stack

### Frontend Technologies

| Technology        | Purpose                                    |
| ----------------- | ------------------------------------------ |
| HTML5             | Semantic structure and content             |
| CSS3              | Styling with Grid, Flexbox, and animations |
| JavaScript (ES6+) | Interactivity and API integration          |

### APIs Used

| API                       | Purpose                   |
| ------------------------- | ------------------------- |
| GitHub REST API           | Fetches repository data   |
| LocalStorage API          | Persists user preferences |
| Intersection Observer API | Scroll-based animations   |

### Development Tools

| Tool         | Purpose             |
| ------------ | ------------------- |
| VS Code      | Code editor         |
| Git          | Version control     |
| GitHub       | Repository hosting  |
| GitHub Pages | Static site hosting |

---

## Project Structure

```
assignment-4/
│
├── index.html                    # Main HTML file
│
├── css/
│   └── styles.css               # All CSS styles (1600+ lines)
│
├── js/
│   └── script.js                # All JavaScript (940 lines)
│
├── assets/
│   ├── images/                  # Project images
│   │   ├── my_personal_photo.JPG
│   │   ├── KFUPM_LOGO.jpg
│   │   ├── cybersecurity.jpg
│   │   ├── Data Science.png
│   │   ├── machinelearning1.jpg
│   │   └── web development.jpeg
│   └── CV.pdf                   # Downloadable resume
│
├── docs/
│   ├── technical-documentation.md   # Technical details
│   └── ai-usage-report.md          # AI assistance report
│
├── .gitignore                   # Git ignore rules
└── README.md                    # This file
```

---

## Getting Started

### Prerequisites

- Modern web browser (Chrome, Firefox, Safari, Edge)
- Git (for cloning)
- Text editor (VS Code recommended)

### Installation

1. **Clone the repository**

   ```bash
   git clone https://github.com/yousefalhadlaq/assignment-4.git
   cd assignment-4
   ```

2. **Open in browser**

   Option 1: Open `index.html` directly in your browser

   Option 2: Use a local server (recommended)

   ```bash
   # With Python 3
   python -m http.server 8000
   # Then visit: http://localhost:8000
   ```

   ```bash
   # With Node.js
   npx http-server
   ```

   Option 3: Use VS Code Live Server extension

---

## Deployment Guide

### Deploy to GitHub Pages

1. **Push code to GitHub**

   ```bash
   git init
   git add .
   git commit -m "Initial commit"
   git branch -M main
   git remote add origin https://github.com/yourusername/assignment-4.git
   git push -u origin main
   ```

2. **Enable GitHub Pages**

   - Go to repository Settings
   - Click on Pages in the sidebar
   - Under Source, select main branch
   - Click Save
   - Wait 2-3 minutes for deployment

3. **Access your site**
   - URL: `https://yourusername.github.io/assignment-4/`

---

## Customization

### Changing Colors

Edit CSS variables in `css/styles.css`:

```css
:root {
  --primary-color: #667eea;
  --secondary-color: #764ba2;
  --accent-color: #f093fb;
  /* Modify as needed */
}
```

### Updating GitHub Username

In `js/script.js`, find and change:

```javascript
const GITHUB_USERNAME = "yousefalhadlaq";
```

### Adding New Projects

Add to the `projectsData` array in `js/script.js`:

```javascript
{
  id: 9,
  name: 'Your Project Name',
  category: 'cybersecurity',  // Options: cybersecurity, data-science, machine-learning, web-dev
  level: 'intermediate',       // Options: beginner, intermediate, advanced
  date: '2024-12',
  description: 'Project description here',
  technologies: ['Tech1', 'Tech2', 'Tech3'],
  image: 'assets/images/your-image.jpg'
}
```

### Modifying Skills

Edit the skills section in `index.html`:

- Change skill names
- Adjust percentage values (data-progress attribute)
- Add or remove skill categories

### Adding Your CV

1. Create/export your CV as a PDF
2. Save it as `CV.pdf` in the `assets/` folder
3. The download button will automatically link to it

---

## Browser Compatibility

### Tested and Working

| Browser       | Version | Status |
| ------------- | ------- | ------ |
| Chrome        | 90+     | ✓      |
| Firefox       | 88+     | ✓      |
| Safari        | 14+     | ✓      |
| Edge          | 90+     | ✓      |
| iOS Safari    | 14+     | ✓      |
| Chrome Mobile | 90+     | ✓      |

### Responsive Breakpoints

| Device       | Width         |
| ------------ | ------------- |
| Desktop      | 1200px+       |
| Tablet       | 768px - 992px |
| Mobile       | 480px - 767px |
| Small Mobile | < 480px       |

---

## Assignment Requirements

### Technical Requirements (All Met)

| Requirement                        | Status |
| ---------------------------------- | ------ |
| Semantic HTML5 structure           | ✓      |
| Modern CSS3 (Grid, Flexbox)        | ✓      |
| Vanilla JavaScript (no frameworks) | ✓      |
| API integration (GitHub API)       | ✓      |
| LocalStorage for state persistence | ✓      |
| Form validation                    | ✓      |
| Responsive design                  | ✓      |
| Cross-browser compatibility        | ✓      |

### Documentation Requirements (All Met)

| Requirement             | Status |
| ----------------------- | ------ |
| README.md               | ✓      |
| Technical documentation | ✓      |
| AI usage report         | ✓      |
| Code comments           | ✓      |
| File organization       | ✓      |

### Presentation Requirements (All Met)

| Requirement         | Status |
| ------------------- | ------ |
| Professional design | ✓      |
| Working demo        | ✓      |
| Live deployment     | ✓      |

---

## Known Issues

1. **GitHub API Rate Limit**

   - Limited to 60 requests/hour without authentication
   - Error message displays when limit exceeded

2. **Contact Form**

   - Simulates submission (no backend server)
   - Form data saved locally only

3. **CV Download**
   - Requires you to add your own CV.pdf file
   - File must be placed in assets/ folder

---

## Documentation

Additional documentation available in the `docs/` folder:

- **[Technical Documentation](docs/technical-documentation.md)**

  - Complete technical details
  - Code architecture
  - Implementation specifics

- **[AI Usage Report](docs/ai-usage-report.md)**
  - AI assistance documentation
  - Work distribution
  - Learning outcomes

---

## Credits

- **KFUPM** - For providing excellent education
- **SWE363 Course Staff** - For guidance and support
- **GitHub** - For hosting and API access

---

## Future Improvements

- [ ] Add backend for contact form
- [ ] Implement actual email sending
- [ ] Add blog section
- [ ] Individual project pages
- [ ] Search functionality
- [ ] Multi-language support

---

**Author:** Yousef Alhadlaq  
**Date:** December 2024  
**Course:** SWE363 - Web Programming and Applications
