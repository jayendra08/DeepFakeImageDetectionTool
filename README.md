# Deepfake Image Detection System

A modern, responsive frontend UI for detecting deepfake images using AI. Built with React, Tailwind CSS, and featuring a clean, user-friendly interface.

## Features

✨ **Core Features:**
- 🖼️ Image upload with drag-and-drop support
- 👁️ Real-time image preview
- 🤖 Mock AI detection with 2-second simulation
- 📊 Color-coded results (Green for Real, Red for Fake)
- 📱 Fully responsive design (mobile + desktop)
- ✨ Smooth animations and transitions
- 🎯 Modern UI with gradient backgrounds

## Tech Stack

- **Frontend Framework:** React 18.2
- **Styling:** Tailwind CSS 3.3
- **Build Tool:** Create React App
- **State Management:** React Hooks (useState)

## Project Structure

```
DeepFakeImageDetection/
├── public/
│   └── index.html                 # HTML entry point
├── src/
│   ├── components/
│   │   ├── Navbar.js             # Header navigation
│   │   ├── ImageUploader.js       # File upload with drag-and-drop
│   │   └── ResultDisplay.js       # Detection result display
│   ├── App.js                     # Main application component
│   ├── index.js                   # React entry point
│   └── index.css                  # Global styles with Tailwind
├── package.json                   # Dependencies
├── tailwind.config.js             # Tailwind configuration
├── postcss.config.js              # PostCSS configuration
└── README.md                      # This file
```

## Installation & Setup

### Prerequisites
- Node.js 14+ and npm installed

### Steps

1. **Navigate to project directory:**
   ```bash
   cd DeepFakeImageDetection
   ```

2. **Install dependencies:**
   ```bash
   npm install
   ```

3. **Start the development server:**
   ```bash
   npm start
   ```
   The app will open at `http://localhost:3000`

4. **Build for production:**
   ```bash
   npm run build
   ```

## Usage

1. **Upload Image:**
   - Click the upload area or drag & drop an image
   - Supported formats: JPG, PNG, GIF, WebP
   - Max file size: 10MB

2. **View Preview:**
   - Selected image is displayed in the preview section
   - Shows filename

3. **Run Detection:**
   - Click the "Detect" button
   - Wait 2 seconds for the mock analysis
   - Results display with color-coded status

4. **Clear & Retry:**
   - Click "Clear" to reset and upload another image

## Component Details

### Navbar
- Header with project branding
- Displays project title and tagline

### ImageUploader
- Drag-and-drop file upload
- File browse functionality
- Image validation (format and size)
- Error messages for invalid files
- Image preview before detection

### ResultDisplay
- Loading spinner during analysis
- Color-coded result display
  - Green & ✅ for real images
  - Red & ❌ for fake images
- Contextual messages explaining results

### App (Main Component)
- Manages overall state
- Handles detection logic (2-second mock delay)
- Tracks detection count
- Responsive layout with tailored spacing

## Customization

### Change Detection Logic
Edit `handleDetect` in [src/App.js](src/App.js#L17):
```javascript
// Replace mock detection with real API call
const response = await fetch('/api/detect', {
  method: 'POST',
  body: formData
});
const data = await response.json();
setIsReal(data.isReal);
```

### Modify Colors
Edit [tailwind.config.js](tailwind.config.js) to customize gradient, button colors, or result colors.

### Adjust Delay Time
In [src/App.js](src/App.js#L26), change `2000` (milliseconds):
```javascript
setTimeout(() => {
  // ... detection logic
}, 2000); // Change this value
```

## Responsive Breakpoints

- **Mobile:** < 640px
- **Tablet:** 640px - 1024px
- **Desktop:** > 1024px

## Future Enhancements

- [ ] Backend integration with actual ML models
- [ ] Confidence score display
- [ ] Batch image upload
- [ ] Image history/gallery
- [ ] Export results as PDF
- [ ] Dark mode support
- [ ] Multiple language support
- [ ] Progressive Web App (PWA)

## Browser Support

- Chrome (latest)
- Firefox (latest)
- Safari (latest)
- Edge (latest)

## Performance Notes

- Image preview limited to 10MB for browser safety
- Mock detection set to 2 seconds for demo purposes
- Responsive images optimize for all screen sizes
- CSS animations use GPU acceleration

## License

MIT License - Feel free to use this project for personal and commercial purposes.

## Support

For issues or questions, please refer to the project repository or contact the development team.

---

**Note:** This is a frontend demonstration system. For production deployment, integrate with actual deep learning models and backend services.
