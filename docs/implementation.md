# Dynamic Content Loading Implementation

This document explains how the website has been updated to load content dynamically from markdown files instead of having hardcoded content in the HTML.

## Changes Made

### Before
- All story content was hardcoded in a JavaScript object within `index.html`
- Content was static and required editing the HTML file to make changes

### After
- Story content is stored in individual markdown files in the `/stories/` directory
- Content is loaded dynamically using JavaScript `fetch()` API
- A simple markdown-to-HTML parser converts the markdown to displayable HTML

## File Structure

```
/stories/
├── 01-tower-of-babylon.md
├── 02-understand.md  
├── 03-division-by-zero.md
├── 04-story-of-your-life.md
├── 05-seventy-two-letters.md
├── 06-evolution-of-human-science.md
├── 07-hell-is-the-absence-of-god.md
└── 08-liking-what-you-see.md
```

## How It Works

1. **Story Metadata**: The JavaScript contains a metadata object mapping chapter numbers to titles and filenames
2. **Dynamic Loading**: When a chapter is selected, the corresponding markdown file is fetched
3. **Markdown Parsing**: A simple parser converts markdown to HTML (handles paragraphs and headers)
4. **Content Display**: The parsed HTML is inserted into the page, maintaining the same visual presentation

## Benefits

- **Easier Content Management**: Stories can be edited as markdown files without touching the HTML
- **Better Separation of Concerns**: Content is separated from presentation code
- **Maintainability**: Adding new stories or editing existing ones is now straightforward
- **Source Format**: Content can be derived from PDF conversion to markdown, making it easier to update from source documents

## Technical Implementation

- Uses native JavaScript `fetch()` API for loading files
- Includes error handling for failed file loads
- Maintains loading states for better user experience
- Preserves all original functionality (navigation, progress tracking, etc.)
- No external dependencies required (uses custom markdown parser)

## Future Enhancements

This implementation provides a foundation for future improvements such as:
- Automated PDF-to-markdown conversion
- Content versioning
- Multi-language support using different markdown files
- Search functionality across all stories