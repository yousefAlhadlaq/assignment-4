# Technical Documentation

**Project:** Portfolio Website  
**Course:** SWE363  
**Last Updated:** December 2024

## Quick Overview

This is a static portfolio website built with HTML, CSS, and vanilla JavaScript. No frameworks, just the basics.

## Project Structure

```
assignment-4/
├── index.html          # Main page
├── css/styles.css      # All styles
├── js/script.js        # All JavaScript
├── assets/
│   ├── images/         # Pictures
│   └── CV.pdf          # My resume
└── docs/               # Documentation
```

## How Things Work

### Theme Toggle

The dark/light mode uses CSS variables. When you click the button:

1. JavaScript flips a `data-theme` attribute on the `<html>` tag
2. CSS swaps out all the colors based on that attribute
3. Your choice gets saved in localStorage so it remembers

### Project Filtering

Projects are stored as an array in JavaScript. When you change the filter dropdown:

1. It filters the array based on category
2. Then sorts by whatever you picked (date or name)
3. Re-renders the project cards

### GitHub Repos

The site fetches my GitHub repos using their public API. It only loads when you scroll to that section (saves bandwidth). If the API fails (happens sometimes due to rate limits), it shows an error message instead of breaking.

### Form Validation

The contact form validates as you type:

- Name: at least 2 letters
- Email: has to look like an email (regex check)
- Subject: at least 5 characters
- Message: 10-1000 characters

It also auto-saves drafts to localStorage every second, so you don't lose your message if you accidentally refresh.

## Responsive Design

The site adjusts for different screen sizes:

- **Desktop (1200px+):** Full layout
- **Tablet (768-992px):** Slightly compressed
- **Mobile (under 768px):** Hamburger menu, stacked layout

## Browser Support

Works on:

- Chrome, Firefox, Safari, Edge (recent versions)
- Mobile browsers

## Running Locally

Just open `index.html` in a browser. For the best experience, use a local server:

```bash
# If you have Python
python -m http.server 8000

# Or with Node
npx http-server
```

## Common Issues

**GitHub repos not loading?**  
Probably hit the API rate limit (60/hour). Just wait a bit.

**Images broken?**  
Check that the file paths match exactly (case-sensitive on some systems).

**Mobile menu not working?**  
Make sure JavaScript is enabled and there are no console errors.

## Customization

To make this your own:

1. Change the GitHub username in `script.js` (look for `GITHUB_USERNAME`)
2. Update project data in the `projectsData` array
3. Replace images in `assets/images/`
4. Edit personal info in `index.html`
5. Adjust colors in the CSS variables at the top of `styles.css`
