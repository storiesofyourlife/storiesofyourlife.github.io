# The Guardian's Awakening - Interactive Novel Website

Always reference these instructions first and fallback to search or bash commands only when you encounter unexpected information that does not match the info here.

## Project Overview

This is a static HTML/CSS/JavaScript website that presents an interactive novel called "The Guardian's Awakening". The site is deployed via GitHub Pages and requires no build process, dependencies, or package managers.

## Working Effectively

### Initial Setup and Serving
- No installation or build steps required - this is a pure static website
- Serve the website locally for testing:
  - `cd /home/runner/work/storiesofyourlife.github.io/storiesofyourlife.github.io`
  - `python3 -m http.server 8080` - Takes <5 seconds to start. NEVER CANCEL.
  - Open browser to `http://localhost:8080`
- Alternative serving methods:
  - Node.js: `npx http-server -p 8080` (if available)
  - Any static file server can serve this site

### Repository Structure
```
.
├── README.md                          # Minimal project description
├── index.html                         # Main website file with embedded JavaScript
├── styles.css                         # CSS styles for the website
└── docs/
    ├── english.md                     # English story documentation
    ├── chinese.md                     # Chinese story documentation
    └── Stories of Your Life and Others PDF.pdf  # Reference material
```

### No Build, Test, or Lint Tools
- **CRITICAL**: This project has NO package.json, NO build scripts, NO test framework, NO linting tools
- Do NOT attempt to run `npm install`, `npm test`, `npm run build`, or any package manager commands
- Do NOT create package.json or add build tools unless specifically required by the task
- Do NOT look for or expect any CI/CD workflows - none exist

## Validation and Testing

### ALWAYS Test User Scenarios After Changes
Manual validation is CRITICAL since there are no automated tests. Always perform these steps:

1. **Serve the site locally** (see commands above)
2. **Complete User Journey Testing**:
   - Load the homepage and verify it displays "The Guardian's Awakening"
   - Click through multiple chapters (1, 2, 5, 10) and verify:
     - Content changes correctly
     - Progress percentage updates (10%, 20%, 50%, 100%)
     - Chapter navigation highlights active chapter
     - All text loads properly
   - Test navigation links in header (Library, Bookmarks, Discover, Settings)
   - Verify responsive design by resizing browser window
   - Check that chapter content scrolls properly

3. **Browser Developer Tools Validation**:
   - Open browser DevTools (F12)
   - Check Console for JavaScript errors (should be none except blocked font loading)
   - Verify no network errors except external font loading
   - Test interactive elements respond correctly

### Screenshot Documentation
- ALWAYS take screenshots when making UI/UX changes to document the visual impact
- Use browser developer tools to test different screen sizes
- Validate changes work on both desktop and mobile layouts

## Deployment and GitHub Pages

- **Deployment Method**: GitHub Pages (automatic from repository)
- **Live Site**: https://storiesofyourlife.github.io (when deployed)
- **Branch**: Changes are deployed from the main branch automatically
- **Domain**: Repository follows GitHub Pages naming convention (*.github.io)
- No special deployment configuration required

## Common Development Tasks

### Making Content Changes
- **Chapter Content**: Edit the `chapterData` object in `index.html` (starts around line 60)
- **Styling**: Edit `styles.css` 
- **Navigation**: Modify the HTML structure in `index.html`
- **ALWAYS** test locally after any changes before committing

### Adding New Chapters
1. Add new chapter entry to `chapterData` object in `index.html`
2. Add corresponding navigation link in the chapter list HTML
3. Update progress calculation if total chapter count changes
4. Test navigation and content loading thoroughly

### Debugging Issues
- Check browser Console for JavaScript errors
- Verify HTML structure hasn't been broken
- Confirm CSS selectors still match DOM elements
- Test event listeners are properly attached

## File Contents Reference

### index.html Key Sections
- `<head>`: External font loading, CSS linking
- `<header>`: Site title and subtitle  
- `<nav>`: Navigation menu (non-functional placeholders)
- `<aside class="chapters">`: Chapter navigation list
- `<section class="content">`: Main content area
- `<script>`: JavaScript with chapter data and navigation logic

### styles.css Key Classes
- `.container`: Page width container (1200px max)
- `.chapters`: Left sidebar chapter navigation
- `.content`: Main content area with scrolling
- `.chapter-link`: Chapter navigation styling
- `.progress`: Progress indicator styling

## Timing Expectations

All operations in this project are very fast:
- **Server startup**: <5 seconds
- **Site loading**: <2 seconds  
- **Navigation between chapters**: <1 second
- **No build time** - static files only

## Troubleshooting Common Issues

### Site Not Loading
- Verify you're serving from the correct directory
- Check that `index.html` exists in the current directory
- Ensure port 8080 is not already in use

### JavaScript Not Working
- Check browser Console for errors
- Verify `chapterData` object syntax is valid
- Confirm all HTML IDs referenced in JavaScript exist

### Styling Issues
- Verify `styles.css` is linked correctly in `index.html`
- Check for CSS syntax errors
- Test with browser developer tools

### External Font Loading Blocked
- Font loading errors are expected in sandboxed environments
- Site functionality is not affected by font loading failures
- Fallback fonts will be used automatically

## What NOT to Do

- Do NOT add build tools, package managers, or testing frameworks unless explicitly required
- Do NOT attempt to run non-existent scripts or commands
- Do NOT modify the core HTML structure without thorough testing
- Do NOT ignore manual validation - there are no automated tests to catch issues
- Do NOT assume any backend functionality exists - this is purely client-side

Remember: This is a simple, elegant static website. Keep changes minimal and always validate manually in a real browser environment.