# SnapSheet 

<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:0f172a,50:2563eb,100:7c3aed&height=220&section=header&text=SnapSheet&fontSize=72&fontColor=ffffff&animation=fadeIn&fontAlignY=38&desc=Every%20photo%2C%20sized%20for%20where%20it%27s%20going.&descSize=20&descAlignY=58" alt="SnapSheet animated header" />

<br />

**Passport photos · Government forms · ID copies · Print-ready sheets**

<p>
  <a href="https://snapsheet-kritanshu.vercel.app/">🌐 Live Demo</a>
  ·
  <a href="#-quick-start">🚀 Quick Start</a>
  ·
  <a href="#-features">✨ Features</a>
  ·
  <a href="#-privacy-first">🔒 Privacy</a>
</p>

<p>
  <img src="https://img.shields.io/badge/version-2.0.0-blue?style=for-the-badge" alt="Version 2.0.0" />
  <img src="https://img.shields.io/badge/react-18-61DAFB?style=for-the-badge&logo=react&logoColor=white" alt="React 18" />
  <img src="https://img.shields.io/badge/vite-5-646CFF?style=for-the-badge&logo=vite&logoColor=white" alt="Vite 5" />
  <img src="https://img.shields.io/badge/PWA-ready-5A0FC8?style=for-the-badge" alt="PWA ready" />
  <img src="https://img.shields.io/badge/privacy-on--device-success?style=for-the-badge" alt="On-device processing" />
</p>

<img src="public/icons/icon-512.png" width="160" alt="SnapSheet app icon" />

</div>

---

## 🎯 What Is SnapSheet?

SnapSheet is a free, private, browser-based photo utility that turns everyday phone photos into correctly sized passport photos, exam uploads, ID copies, collages, and print-ready sheets.

Everything happens locally in your browser. No account, cloud upload, server-side processing, or photo storage required.

> **Short version:** one photo, the right pixels, the right size, the right format, without uploading it anywhere.

---

## ✨ Features

<table>
<tr>
<td width="50%" valign="top">

### 🛂 Passport & Visa Photos

Create and export photos for 13 document types across 11 countries and regions.

- Automatic face detection and head framing
- On-device straightening and size guidance
- Head size, tilt, background, lighting, and sharpness checks
- White, off-white, light blue, and light grey backgrounds
- Sheets for 4 × 6 in, A4, A5, and US Letter
- Cut lines, optional name/date strip, PDF, print, or 600 DPI JPG
- Editable custom dimensions

</td>
<td width="50%" valign="top">

### 📝 Government & Exam Forms

Resize photos, signatures, thumbs, declarations, and postcard photos to published form requirements.

- SSC, IBPS/SBI, UPSC, NEET UG, and PAN presets
- Editable pixel dimensions and file-size limits
- Automatic signature and ink crop cleanup
- Best-fit JPEG quality without exceeding size limits
- Padding for minimum file-size requirements
- Direct download in the required format

</td>
</tr>
<tr>
<td width="50%" valign="top">

### 🪪 ID Card Copies

Prepare both sides of an ID card on a single true-size page.

- Four-point perspective correction
- Magnifier for precise corner placement
- 85.6 × 54 mm and custom card sizes
- A4 and US Letter layouts
- Colour, grayscale, and crisp-scan modes
- Purpose watermark for one-use copies
- Stacked, side-by-side, and multi-set layouts

</td>
<td width="50%" valign="top">

### 🖨️ Print Studio

Build photo sheets, contact sheets, prints, and collages with precise measurements.

- Grid, exact-print, and six collage layouts
- Real millimetre controls for margins, gaps, and borders
- Standard and custom paper sizes
- Crop, zoom, rotate, straighten, and mirror controls
- Ten looks plus brightness, contrast, saturation, and warmth
- Synced copies and fill-the-page mode
- PDF, JPG, PNG, ZIP, direct print, and phone share sheet

</td>
</tr>
</table>

---

## 🔒 Privacy First

<div align="center">

| Your photo | What happens |
|:---:|---|
| 📷 Selected on your device | Processed in the browser tab |
| ☁️ Uploaded to SnapSheet | Never |
| 🗄️ Stored on SnapSheet servers | Never—there are no SnapSheet servers for photos |
| 💾 Saved automatically | Only in local IndexedDB when autosave is enabled |
| 🤖 AI processing | Face detection and segmentation run on-device |

</div>

The card copy workflow also keeps card photos limited to the current tab and does not save them through the normal autosave flow.

---

## 🚀 Quick Start

### Prerequisites

- **Node.js 18 or newer**
- **npm**

### Run locally

```bash
git clone https://github.com/kritxnshu/SnapSheet-2.0.git
cd SnapSheet-2.0
npm install
npm run dev
```

Open **http://localhost:5173**.

### Available commands

| Command | Description |
|---|---|
| `npm run dev` | Start the Vite development server |
| `npm test` | Run the Vitest unit test suite |
| `npm run build` | Create a production build in `dist/` |
| `npm run preview` | Preview the production build locally |

---

## 🧭 App Routes

| Route | Tool |
|---|---|
| `/` | SnapSheet home and tool switcher |
| `/passport` | Passport and visa photo creator |
| `/form-photo` | Photo, signature, thumb, and declaration resizer |
| `/id-copy` | ID card perspective correction and copy sheets |
| `/studio` | Photo print and collage studio |

---

## 🛠️ Tech Stack

<div align="center">

![React](https://img.shields.io/badge/React-18-61DAFB?logo=react&logoColor=white)
![Vite](https://img.shields.io/badge/Vite-5-646CFF?logo=vite&logoColor=white)
![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-3-38B2AC?logo=tailwind-css&logoColor=white)
![Canvas](https://img.shields.io/badge/Canvas-2D-E34F26)
![IndexedDB](https://img.shields.io/badge/IndexedDB-Local_Data-4B8BBE)
![PWA](https://img.shields.io/badge/PWA-Offline-5A0FC8)

</div>

- **React 18** for the interface
- **Vite 5** for development and production builds
- **Tailwind CSS 3** for responsive styling
- **Canvas 2D** for consistent previews and exports
- **jsPDF** for PDF generation
- **fflate** for ZIP exports
- **heic2any** for lazy-loaded HEIC/HEIF decoding
- **MediaPipe Tasks Vision** for on-device face detection and segmentation
- **IndexedDB** and a service worker for autosave and offline support

### How processing works

```mermaid
flowchart LR
    A[Choose a photo] --> B[Read locally]
    B --> C{Processing mode}
    C --> D[Canvas editor]
    C --> E[Face detection]
    C --> F[Background removal]
    D --> G[Preview]
    E --> G
    F --> G
    G --> H[Export PDF / JPG / PNG / Print / ZIP]
```

MediaPipe's WebAssembly runtime ships with the app. Vision models are downloaded once on first use of AI-assisted features and are then cached by the browser.

---

## 📁 Project Structure

```text
src/
├── components/       Shared UI, studio panels, cropper, and corner picker
├── lib/              Layout, rendering, export, imaging, filters, history, storage
│                     and on-device document/photo processing
├── pages/            Home, Passport, FormPhoto, IdCopy, and Studio routes
├── App.jsx           Routes and page-level loading
└── main.jsx          Application entry point

public/
├── icons/            App icons, favicon, and PWA artwork
├── manifest.webmanifest
└── sw.js             Offline service worker

vercel.json           SPA routing and asset cache headers
vite.config.js        Vite configuration
```

---

## 🌐 Deployment

SnapSheet is a static Vite application and can be deployed to Vercel, Netlify, Cloudflare Pages, GitHub Pages, or any modern static host.

The included `vercel.json`:

- Rewrites app routes to `index.html`
- Keeps the service worker uncached
- Applies immutable caching to hashed assets
- Supports MediaPipe assets at `/mediapipe/`

### Deploy to Vercel

```bash
npm install -g vercel
vercel
```

For hosts that do not read Vercel configuration, enable an SPA fallback from all application routes to `index.html`.

---

## 🧪 Quality & Browser Support

The unit suite covers layout math, rendering helpers, filters, undo history, passport framing and checks, form file sizing, perspective correction, and DPI metadata.

SnapSheet targets recent versions of:

- Google Chrome / Chromium
- Microsoft Edge
- Mozilla Firefox
- Safari on macOS and iOS

Some advanced features, such as clipboard access and direct share/download behaviour, depend on browser support and secure-context permissions.

> MediaPipe and browser canvas features are used with progressive fallbacks where possible.

---

## ⚠️ Document Requirements

SnapSheet is a formatting aid, not an official authority. Government and document requirements can change.

Before submitting a photo, always verify:

- Pixel dimensions and file size
- Background colour
- Head position and dimensions
- Recent vs. newly captured photos
- Official file type requirements

The app highlights that requirements can change and keeps size, pixel, and KB values editable.

---

## 🤝 Contributing

Contributions, bug reports, and feature suggestions are welcome.

1. Fork the repository.
2. Create a focused branch.

   ```bash
   git checkout -b feature/my-improvement
   ```

3. Make your change and run tests.

   ```bash
   npm test
   npm run build
   ```

4. Commit the change with a clear message.
5. Open a pull request with screenshots or steps for UI changes.

Please keep generated files, dependencies, and unrelated formatting changes out of pull requests.

---

## 🗺️ Roadmap Ideas

- Additional country passport presets
- Multi-language interface
- More government form specifications
- Batch passport-sheet exports
- Custom printable proof sheets
- Stronger browser privacy indicators
- Expanded automated test coverage

Have a useful preset or feature request? Open an issue with the official specification or an example notice.

---

## 🧑‍💻 Author

Built with care by **Kritanshu Krishnan**.

<div align="center">

<a href="https://github.com/kritxnshu">
  <img src="https://img.shields.io/badge/GitHub-kritxnshu-181717?style=for-the-badge&logo=github" alt="GitHub profile" />
</a>

<a href="https://snapsheet-kritanshu.vercel.app/">
  <img src="https://img.shields.io/badge/Try-SnapSheet-2563eb?style=for-the-badge&logo=vercel&logoColor=white" alt="Try SnapSheet" />
</a>

<br /><br />

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:7c3aed,50:2563eb,100:0f172a&height=120&section=footer" alt="Animated footer" />

</div>
