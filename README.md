# Public Assets Folder

This folder contains static assets that are served directly by the web server.

## Profile Image Setup

### Quick Start

1. **Add your profile photo** to this folder (e.g., `profile.jpg`)
2. **Update the path** in `src/data/profile/image.ts` if you use a different filename
3. The image will automatically appear on the home page

### Recommended Specifications

- **Format**: JPG, PNG, or WebP
- **Size**: 400x400px or larger
- **Aspect Ratio**: Square (1:1)
- **File Size**: Keep under 500KB for best performance
- **Quality**: High-quality headshot or professional photo

### File Naming

You can use any filename, but common choices are:

- `profile.jpg`
- `avatar.png`
- `headshot.jpg`
- `photo.webp`

### Example Files

```
public/
├── profile.jpg              ← Your profile photo (add this!)
├── profile-placeholder.svg  ← Default placeholder (already included)
└── README.md               ← This file
```

### Updating the Image Path

If you name your file differently, update `src/data/profile/image.ts`:

```typescript
export const profileImage: ProfileImage = {
  src: '/your-image-name.jpg', // ← Change this
  alt: 'Your Name',
  width: 200,
  height: 200,
}
```

### Optimization Tips

1. **Compress your image** before uploading using tools like:
   - [TinyPNG](https://tinypng.com/) for PNG/JPG
   - [Squoosh](https://squoosh.app/) for WebP

2. **Use WebP format** for smaller file sizes:
   - Convert with online tools or image editors
   - Better compression than JPG/PNG

3. **Remove metadata** to reduce file size:
   - Use tools like ExifTool or online services

### Fallback Behavior

If your image fails to load, the placeholder SVG (`profile-placeholder.svg`) will be shown automatically. This ensures your site always looks professional.

## Adding Other Assets

You can add other static files to this folder:

- **Favicons**: `favicon.ico`, `favicon.svg`
- **Documents**: Resume PDFs, certificates, etc.
- **Images**: Project screenshots, logos, etc.
- **Icons**: App icons, social media images

### Example Structure

```
public/
├── profile.jpg
├── favicon.ico
├── resume.pdf
├── projects/
│   ├── project1-screenshot.png
│   └── project2-demo.jpg
└── education/
    ├── transcript.pdf
    └── degree-certificate.pdf
```

### Accessing Public Files

Files in this folder are served from the root URL:

```tsx
// File: public/profile.jpg
// URL: /profile.jpg

<img src="/profile.jpg" alt="Profile" />
```

```tsx
// File: public/resume.pdf
// URL: /resume.pdf

<a href="/resume.pdf">Download Resume</a>
```

## Notes

- Files are served as-is (no processing)
- Paths are relative to domain root
- No imports needed (just reference by path)
- Changes require dev server restart
