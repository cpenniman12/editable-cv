# Fully Editable CV Site with LocalStorage

A completely customizable CV website where users can edit all text, add/delete sections, and even change images - all saved locally using browser localStorage.

## Features

### Text Editing
- **Double-Click to Edit**: Any text on the page can be edited
- **Auto-Save**: Changes automatically save to localStorage
- **Persistent**: Edits remain across page refreshes

### Section Management
- **Add/Delete Jobs**: Add new work experience, delete old ones
- **Add/Delete Projects**: Manage your project portfolio
- **Add/Delete Education**: Add multiple degrees/certifications
- **Add/Delete Skills**: Customize your skillset
- **Add/Delete Images**: Manage your life/portfolio images

### Image Management
- **Change Profile Picture**: Upload your own photo (converts to base64)
- **Change Life Images**: Replace any image with your own
- **Add New Images**: Add more images to your life section
- **Delete Images**: Remove images you don't want

### Other Features
- **Reset Button**: Restore everything to original state
- **Visual Feedback**: Hover effects show what's editable
- **Responsive Design**: Works on desktop and mobile
- **No Server Needed**: Completely client-side

## How to Use

### Edit Text
1. **Double-click** any text (name, job titles, descriptions, etc.)
2. Type your changes
3. Press **Enter** to save or **Escape** to cancel
4. Changes are automatically saved

### Add/Delete Sections

**Add a Job:**
1. Scroll to Experience section
2. Click "+ Add Job" button
3. Double-click each field to edit

**Delete a Job:**
- Click "Delete Job" button on any job entry

**Same process works for:**
- Projects (+ Add Project)
- Education (+ Add Education)
- Skills (+ Add Skill)
- Life Images (+ Add Image)

### Change Images

**Profile Picture:**
1. Hover over your profile image
2. Click "Change" button
3. Select an image file from your computer
4. Image is converted to base64 and saved locally

**Life/Portfolio Images:**
1. Hover over any image in the Life section
2. Click "Change" to replace or "Delete" to remove
3. Click "+ Add Image" to add new images

### Reset Everything
- Click "Reset All" button in top-right
- Confirms before resetting
- Reloads page with original content

## What Gets Saved

Everything is stored in your browser's localStorage:
- All text edits (name, bio, job descriptions, etc.)
- Structural changes (added/deleted jobs, projects, skills)
- Image changes (stored as base64 data URLs)
- Section order and content

## Technical Details

### Storage
- **localStorage Key**: `cvEdits` (for text content)
- **localStorage Key**: `cvStructure` (for sections/structure)
- **Storage Limit**: ~5-10MB per domain (varies by browser)
- **Image Format**: Base64 data URLs

### Browser Compatibility
- Modern browsers (Chrome, Firefox, Safari, Edge)
- Mobile browsers supported
- No external dependencies
- Pure HTML, CSS, and vanilla JavaScript

### Data Persistence
- **Same Device + Same Browser**: All edits persist
- **Different Device**: Shows original content
- **Different Browser**: Shows original content
- **Private/Incognito Mode**: Edits lost when window closes
- **Clear Browser Data**: Edits lost if localStorage is cleared

## Deploying to GitHub Pages

Already deployed at: **https://cpenniman12.github.io/editable-cv/**

To update:
```bash
git add .
git commit -m "Update editable CV"
git push
```

Changes will be live in 1-2 minutes.

## Customization

### Make More Content Editable

Add the `data-editable` attribute with a unique key:

```html
<div data-editable="unique-key-here">Your content</div>
```

### Add New Section Types

1. Create HTML structure with unique data attributes
2. Add add/delete functions in JavaScript
3. Update `saveStructure()` and `loadStructure()` functions

### Change Styling

All styles are in the `<style>` section:
- Edit button colors
- Change hover effects
- Modify section layouts
- Adjust responsive breakpoints

## File Structure

```
editable-cv-site/
├── index.html          # Main editable CV page
├── README.md           # This file
└── original.html       # Reference copy of original site
```

## How It Works

### localStorage Architecture

**Two Storage Keys:**
1. `cvEdits`: Stores all text content changes
   ```json
   {
     "name": "John Smith",
     "job1-title": "Software Engineer",
     "bio": "Custom bio text..."
   }
   ```

2. `cvStructure`: Stores dynamic sections (jobs, projects, etc.)
   ```json
   {
     "jobs": [...],
     "projects": [...],
     "skills": [...],
     "life": [...],
     "nextIds": {...}
   }
   ```

### Image Storage

Images are converted to base64 data URLs:
- Selected via file input
- Converted using FileReader API
- Stored as data URL strings in localStorage
- Automatically loaded on page refresh

**Note:** Large images increase localStorage usage. Consider:
- Resizing images before upload
- Using smaller file sizes
- Limiting number of uploaded images

## Browser localStorage Limits

Typical limits per domain:
- **Chrome/Firefox**: ~10MB
- **Safari**: ~5MB
- **Mobile browsers**: ~5MB

**Tips:**
- Compress images before uploading
- Don't add too many large images
- Use "Reset All" to clear storage if needed

## Privacy

- All data stored locally in your browser
- Nothing sent to any server
- Each user's edits are completely private
- Only visible on their device/browser

## Use Cases

1. **Personal Resume Template**: Users customize CV for themselves
2. **Portfolio Builder**: Edit to create personalized portfolios
3. **CV Workshop**: Practice tailoring resumes for different roles
4. **Template Experimentation**: Try different content/layouts

## Limitations

- localStorage limited by browser (5-10MB)
- Large base64 images use significant storage
- Edits don't sync across devices
- No user accounts/authentication
- No server-side persistence

## Browser Developer Tools

View your saved data:
1. Open browser DevTools (F12)
2. Go to "Application" tab
3. Select "Local Storage"
4. Find your domain
5. See `cvEdits` and `cvStructure` keys

## Troubleshooting

**Edits not saving?**
- Check if localStorage is enabled (disabled in some privacy modes)
- Check browser console for errors
- Try a different browser

**Images not loading?**
- File size may be too large
- Try smaller/compressed images
- Check localStorage usage

**Page looks broken?**
- Click "Reset All" to restore
- Clear browser cache and reload
- Check browser console for errors

**Can't edit text?**
- Make sure you're double-clicking (not single-click)
- Element must have `data-editable` attribute
- Check if JavaScript is enabled

## License

Free to use and modify for your own projects!

## Credits

Based on Cooper Penniman's original CV design.
Enhanced with full editing capabilities using localStorage.
