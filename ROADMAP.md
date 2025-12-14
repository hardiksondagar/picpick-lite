# PicPick Lite - Feature Roadmap

## Use Case
Wedding/vacation/event photographers need to quickly select the best photos from thousands of shots. Features are prioritized to speed up selection, improve decision-making, and streamline export.

---

## Phase 1: Speed Up Selection (High Priority)

### ⭐ 5-Star Rating System
- Replace binary starred/not with 1-5 star ratings
- 1 = reject/delete, 3 = maybe, 5 = must have
- Keyboard shortcuts: 1-5 keys to rate
- Filter by rating level
- Export by rating threshold (e.g., "export 4-5 stars only")

### 🚀 Auto-Advance Mode
- Toggle: after starring/rating, auto-jump to next photo
- Save clicks during rapid selection
- Configurable delay (instant or 500ms)
- Status indicator in header

### ❌ Reject/Hide Photos
- Mark bad photos to hide from view (X key)
- "Show rejected" toggle to review later
- Helps narrow down selection quickly
- Save rejected state to localStorage

### 📊 Progress Tracking
- "Reviewed 450/1200 photos (37%)"
- "Starred 45 photos in last 15 minutes"
- Visual progress bar in header
- Motivates completion of large batches

### 🔖 Session Resume
- "Resume where you left off" button
- Last viewed marker in grid
- Save scroll position
- "Continue from photo 451" on page load

---

## Phase 2: Better Decision Making (High Priority)

### 🔍 Comparison Mode
- Select 2-4 photos to view side-by-side
- Essential for choosing between burst shots
- Keyboard shortcuts: C to compare selected
- Sync zoom/pan across compared images
- Vote/star directly from comparison view

### 🔎 100% Zoom / Focus Check
- Click to zoom to actual pixels
- Check sharpness and focus
- Pan around image when zoomed
- Pinch-to-zoom on mobile

### 👀 Previous/Next Preview
- Show thumbnails of adjacent photos while in modal
- Quick context without closing modal
- Click thumbnail to jump

### 🏷️ Flag for Review
- Mark photos to revisit when unsure
- Separate from starred/rejected
- "Review flagged" filter mode
- F key to flag

### 📸 Duplicate/Burst Grouping
- Auto-detect photos taken within 2 seconds
- Group burst shots together visually
- "Choose 1 from 5 similar" workflow
- Expand/collapse burst groups

---

## Phase 3: Organization & Collections (Medium Priority)

### 📁 Custom Collections
- Create named collections: "Ceremony", "Reception", "Family"
- Assign photos to multiple collections
- Filter by collection
- Export by collection

### 🎨 Color Labels
- Red/Blue/Green/Yellow labels (like Apple Photos)
- Quick keyboard shortcuts (Shift+1-5)
- Filter by color label
- Use for categorization: red=family, blue=ceremony

### ⏰ Smart Time Grouping
- Auto-detect event phases by time gaps
- "Morning Prep", "Ceremony", "Dinner", "Party"
- Editable group names and boundaries
- Balance selection across time periods

### 👤 Face Grouping (Advanced)
- Basic face detection using TensorFlow.js
- Click face → see all photos with similar faces
- Group by person
- Ensure key people are represented

---

## Phase 4: Export & Sharing (Medium Priority)

### 📐 Resize on Export
- Presets: "Instagram (1080px)", "Web (1920px)", "Full resolution"
- Custom size input
- Compress JPEG quality slider
- Preview file sizes before export

### 📝 Rename on Export
- Pattern-based renaming: "Wedding_001.jpg"
- Include date/collection name
- Preview renamed files before export
- Preserve original filenames option

### 📋 Copy to Clipboard
- Quick share single photo
- Use Clipboard API
- Share to Messages/WhatsApp directly

### 👁️ Export Preview
- Grid view of photos about to export
- Final check before saving
- Remove/add from export list
- Summary: "45 photos, ~230MB"

### 📊 Selection Balance
- Show counts: "23 portrait, 45 landscape"
- "15 ceremony, 30 reception" breakdown
- Warn if imbalanced (e.g., only 3 ceremony photos)

---

## Phase 5: Advanced Features (Lower Priority)

### 🖼️ Basic Editing (Non-destructive)
- Crop tool
- Rotate/flip (90° increments)
- Brightness/contrast/saturation sliders
- Filters: B&W, sepia, vintage
- Export edited version (original preserved)

### 🎬 Slideshow Mode
- Auto-play starred/filtered photos
- Configurable interval (3s, 5s, 10s)
- Transitions/animations
- Fullscreen mode
- Music support (user-uploaded track)

### 🔤 EXIF Metadata Viewer
- Show camera model, settings, date taken
- GPS location on map
- Lens info, ISO, aperture
- Copy metadata to clipboard

### 📈 Statistics Dashboard
- Charts: photos by hour, by folder, by rating
- Heatmap of shooting times
- Most active shooting period
- Selection rate trends

### 🎯 Smart Suggestions
- "These 5 photos are very similar - keep 1?"
- Auto-detect blurry photos (flag for review)
- Find underexposed/overexposed shots
- Suggest best photo from burst (sharpest)

### 🗜️ ZIP Export
- Bundle starred photos into downloadable ZIP
- Use JSZip library
- Include folder structure
- Progress bar for large exports

### 🔍 Advanced Search
- Search by filename
- Filter by date range picker
- Filter by dimensions (portrait/landscape)
- Filter by file size
- Color search (dominant color)

### ⚡ Multi-Select Operations
- Ctrl/Cmd+click to select multiple
- Bulk star/unstar/rate
- Bulk assign to collection
- Bulk export selection

### 🎨 Themes
- Light mode
- Custom accent colors
- High contrast mode
- Auto dark/light based on time

---

## Technical Improvements

### Performance
- Virtual scrolling for 10,000+ photos
- Web Workers for image processing
- IndexedDB for faster metadata access
- Thumbnail caching improvements

### UX Polish
- Drag & drop photos to reorder
- Undo/redo for all actions
- Keyboard shortcut cheatsheet (? key)
- Touch gestures on mobile (swipe to star)
- Haptic feedback on mobile

### Data Management
- Import/export all settings as JSON backup
- Sync starred list between devices (export/import)
- Session history (undo starring actions)
- Clear cache option

---

## Priority Summary

**Must Have (Phase 1-2):**
1. 5-star rating system
2. Comparison mode
3. Auto-advance mode
4. Progress tracking
5. Reject/hide photos

**Should Have (Phase 3-4):**
6. Custom collections
7. Resize on export
8. 100% zoom
9. Color labels
10. Export preview

**Nice to Have (Phase 5):**
11. Face detection
12. Basic editing
13. Slideshow mode
14. Statistics dashboard
15. Smart suggestions

---

## Out of Scope
- Cloud sync (keeping it 100% local)
- AI auto-selection (too complex)
- Video support (photos only)
- RAW file support (browser limitations)
- Printing layouts (export only)

