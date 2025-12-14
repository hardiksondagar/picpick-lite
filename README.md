# PicPick Lite

A lightweight, browser-only photo selection tool. No installation, no server, no dependencies - just open the HTML file and start curating your photos.

## The Problem

You have thousands of photos from a wedding, vacation, or event. You need to select the best ones for an album or sharing. Manually clicking through folders is tedious. You want a fast, visual way to star favorites and export them.

## The Solution

PicPick Lite gives you a clean, keyboard-driven interface to:
- Browse all photos in a folder (including subfolders)
- Star/unstar with a single keystroke
- Filter by subfolder, date, and starred status
- Export selected photos to any folder
- Resume your session automatically after refresh

All processing happens in your browser. Your photos never leave your device.

## Features

### 📁 Folder Access
- Select any folder on your computer
- Automatically scans all subfolders recursively
- Folder access persists across browser refreshes (no need to re-select)

### ⭐ Photo Selection
- Star/unstar with **Space** key
- Visual indicators on thumbnails
- Quick filters: All Photos / Starred Only
- Export starred photos to any destination folder

### 📅 Smart Organization
- Groups photos by date
- Subdivides each day by time (event-based clustering)
- Filter by subfolder to focus on specific sessions

### ⌨️ Keyboard Navigation
- **Space** - Star/unstar current photo
- **← / →** - Navigate between photos
- **Esc** - Close modal

### 🎨 Customizable Grid
- Three size options: Small (150px), Medium (200px), Large (250px)
- Responsive layout adapts to screen size

### 💾 Session Persistence
- Your starred selections are saved automatically
- Folder access is remembered
- Scroll position and filters restored on refresh
- "Clear Session" option in header to start fresh

### ⚡ Performance Optimized
- Client-side thumbnail generation for fast loading
- Lazy image loading (only loads visible photos)
- Pagination (50 photos per batch)
- Works smoothly with thousands of photos

## How to Use

### 1. Open the File
Just double-click `index.html` or open it in any modern browser.

**Note:** For security reasons, some browsers require the file to be served via HTTP. If the file doesn't work when opened directly, you can serve it using Python:

```bash
# Python 3
python -m http.server 8080

# Then open: http://localhost:8080/index.html
```

### 2. Select Your Photos Folder
Click "Choose Folder" and select the directory containing your photos. Grant permission when prompted.

The app will scan all photos (JPG, JPEG, PNG, GIF, WebP) in the folder and subfolders.

### 3. Review and Star
- Click any photo to view full size
- Press **Space** to star/unstar
- Use arrow keys to navigate
- Filter by folder or date to focus your selection

### 4. Export Starred Photos
Click "Export Starred" and choose a destination folder. All starred photos will be copied there with their folder structure preserved.

## Browser Compatibility

Requires a modern browser with support for:
- File System Access API (Chrome 86+, Edge 86+)
- Canvas API
- IndexedDB
- localStorage

**Supported:**
- ✅ Chrome/Chromium 86+
- ✅ Edge 86+
- ✅ Opera 72+

**Not Supported:**
- ❌ Firefox (no File System Access API support yet)
- ❌ Safari (no File System Access API support yet)

## Technical Details

### Architecture
- **Zero dependencies** - Pure HTML, CSS, and vanilla JavaScript
- **Client-side only** - No server, no uploads, no cloud
- **Privacy-first** - Photos never leave your device

### Storage
- **IndexedDB** - Stores folder handle for persistence
- **localStorage** - Stores starred photo paths and UI preferences
- **sessionStorage** - Temporary scroll position tracking

### Thumbnail Generation
Photos are dynamically resized in the browser using Canvas API:
- Max dimensions: 300x300px
- JPEG compression: 70% quality
- On-demand loading as you scroll

### Data Structure
```javascript
{
  id: number,
  path: string,           // relative/to/folder/photo.jpg
  folder: string,         // relative/to/folder
  filename: string,       // photo.jpg
  lastModified: number,   // Unix timestamp
  starred: boolean,
  thumbnailUrl: string    // data:image/jpeg;base64,...
}
```

## File Size

The entire application is **~40KB** of minified HTML/CSS/JS in a single file.

## Comparison with PicPick (Full Version)

| Feature | PicPick Lite | PicPick Full |
|---------|-------------|--------------|
| Installation | None (browser-only) | Python + dependencies |
| AI Clustering | ❌ | ✅ |
| Face Recognition | ❌ | ✅ |
| Duplicate Detection | ❌ | ✅ |
| Simple Star/Export | ✅ | ✅ |
| Offline-first | ✅ | ✅ |
| Processing Speed | Instant | ~20-30 min initial scan |

**Use PicPick Lite when:**
- You just need basic selection/export
- You want instant startup
- You don't want to install anything

**Use PicPick Full when:**
- You have thousands of near-duplicate photos
- You want AI-powered clustering
- You need face-based filtering

## Contributing

Found a bug? Have a feature idea? Open an issue or PR!

## License

MIT License - Use it however you want!

## Credits

Built with frustration from manually clicking through 5000 wedding photos. 📸

