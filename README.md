# Editable CV Site with LocalStorage

An editable version of your CV website where users can customize content and save changes locally using browser localStorage.

## Features

- **Double-Click to Edit**: Click on any text to edit it in place
- **Auto-Save**: Changes are automatically saved to your browser's localStorage
- **Persistent**: Your edits persist across page refreshes (only on your browser)
- **Reset Button**: Restore all content to original values
- **Visual Feedback**: Editing mode shows a subtle highlight
- **Responsive Design**: Works on desktop and mobile devices

## How to Use

1. **Edit Content**: Double-click any editable text (name, job titles, descriptions, etc.)
2. **Save**: Press Enter or click outside the text to save
3. **Cancel**: Press Escape to cancel editing
4. **Reset**: Click "Reset to Original" button to restore all content

## What Can Be Edited?

Almost everything:
- Your name
- Contact information (email, location)
- Bio/tagline
- Job titles, companies, and dates
- Job descriptions
- Project titles and descriptions
- Education details
- Skills
- Writing titles and dates
- Life captions

## How It Works

- **localStorage**: All edits are stored in your browser's localStorage
- **No Server**: Everything runs client-side, no backend needed
- **Privacy**: Your edits are only visible to you on your device
- **GitHub Pages Compatible**: Works perfectly as a static site

## Deploying to GitHub Pages

### Option 1: Create New Repository

1. Create a new repository on GitHub (e.g., `editable-cv`)
2. Clone this directory or push the files:
   ```bash
   cd editable-cv-site
   git init
   git add .
   git commit -m "Initial commit: Editable CV"
   git branch -M main
   git remote add origin https://github.com/YOUR_USERNAME/editable-cv.git
   git push -u origin main
   ```

3. Enable GitHub Pages:
   - Go to repository Settings
   - Navigate to "Pages" section
   - Under "Source", select branch `main` and folder `/ (root)`
   - Click Save
   - Your site will be live at `https://YOUR_USERNAME.github.io/editable-cv/`

### Option 2: Use Existing Repository

1. Copy `index.html` to your existing repository
2. Commit and push:
   ```bash
   git add index.html
   git commit -m "Add editable CV version"
   git push
   ```

3. Access it at: `https://YOUR_USERNAME.github.io/REPO_NAME/index.html`

## Technical Details

### Browser Storage
- Uses `localStorage` API
- Storage key: `cvEdits`
- Data format: JSON object with key-value pairs
- Storage limit: ~5-10MB (varies by browser)

### Compatibility
- Modern browsers (Chrome, Firefox, Safari, Edge)
- Mobile browsers supported
- No external dependencies
- Pure HTML, CSS, and vanilla JavaScript

### Data Persistence
- **Same Device + Same Browser**: Edits persist
- **Different Device**: Original content shown
- **Different Browser**: Original content shown
- **Private/Incognito Mode**: Edits lost when window closes

## Customization

### Add More Editable Fields

To make more content editable, add the `data-editable` attribute:

```html
<div data-editable="unique-key">Your content here</div>
```

### Change Colors

Edit the CSS variables in the `<style>` section:
- Edit button colors
- Hover effects
- Border colors

### Disable Editing on Specific Elements

Remove the `data-editable` attribute from elements you want to keep static.

## Troubleshooting

**Edits not saving?**
- Check browser console for errors
- Ensure localStorage is enabled (some privacy modes disable it)
- Try a different browser

**Can't edit text?**
- Make sure you're double-clicking, not single-clicking
- Check that the element has `data-editable` attribute

**Reset button not working?**
- Clear browser cache
- Hard refresh (Ctrl+Shift+R or Cmd+Shift+R)

## Privacy Note

All edits are stored locally in your browser. No data is sent to any server. Each visitor's edits are completely private to them.

## License

Feel free to use this as a template for your own editable CV!
