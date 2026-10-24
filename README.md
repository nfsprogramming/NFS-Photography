# NFS Photography Portfolio

A high-contrast, interactive portfolio website for **NFS Photography** (ESTD 2024), founded by mobile photographer **Nifras**. Built with React 19, Vite, Tailwind CSS, Framer Motion, GSAP, and Three.js.

---

## Overview

NFS Photography showcases fine-art mobile photography across portrait, urban, nature, macro, and minimalist categories. The web application features an immersive dark aesthetic, real-time 3D particle starfields, smooth inertial scrolling, interactive photography metadata (EXIF details), and direct client booking.

---

## Features

- **3D Starfield Hero**: Interactive Three.js particle canvas rendered via `@react-three/fiber` and `@react-three/drei` with dynamic typewriter messaging.
- **Masonry Portfolio Gallery**: Dynamic category filtering (`All`, `Portrait`, `Urban`, `Nature`, `Macro`, `Minimalist`) with skeleton shimmer loaders.
- **Photo Metadata (EXIF) Display**: Displays technical shot parameters (camera body, focal length, ISO, aperture, shutter speed) on hover (desktop) and tap (mobile).
- **Interactive Lightbox**: Full-resolution viewer with keyboard shortcuts (`Escape` to close, arrow keys for navigation) and metadata readout.
- **About & Philosophy**: Narrative bio with custom portrait imagery and core pillars (Vision, Focus, Light).
- **Milestones & Key Statistics**: Animated impact metrics (500+ projects shot, 15+ awards, 5+ years experience).
- **Verified Certifications**: Recognition modal featuring official credentials and certificate inspectability.
- **4-Step Creative Process**: Visual roadmap covering Observation, Composition, Capture, and Curation.
- **Booking & Contact Hub**: Direct client inquiry form wired with EmailJS, complemented by immediate WhatsApp chat integration.
- **Fluid Micro-interactions**: Lenis smooth inertial scrolling, GSAP ScrollTrigger transitions, custom cursor follower, and 3D tilt response.

---

## Tech Stack

| Layer | Technologies |
| :--- | :--- |
| **Frontend Framework** | React 19, React DOM 19 |
| **Build Tool & Bundler** | Vite 7 (`@vitejs/plugin-react`) |
| **Styling** | Tailwind CSS v4 (`@tailwindcss/vite`), Custom CSS Design Tokens |
| **Motion & Dynamics** | Framer Motion, GSAP (ScrollTrigger), Lenis |
| **3D Graphics** | Three.js, React Three Fiber, React Three Drei |
| **Icons & Utilities** | Lucide React, clsx, tailwind-merge |
| **Messaging** | EmailJS (`@emailjs/browser`) |
| **Code Quality** | ESLint 9 |
| **Deployment Target** | Vercel (SPA routing configured via `vercel.json`) |

---

## Project Structure

```text
E:/NFS Photography/
├── public/
│   ├── certificate.jpg        # Award certificate asset
│   ├── favicon.png            # Site favicon
│   ├── logo.jpg               # Studio brand logo
│   ├── nifras-portrait.jpg    # Artist portrait
│   └── work1.jpg - work6.jpg  # Portfolio gallery assets
├── src/
│   ├── components/
│   │   ├── About.jsx / .css          # Bio and philosophy cards
│   │   ├── Achievements.jsx / .css   # Recognition showcase
│   │   ├── Contact.jsx               # EmailJS inquiry form & WhatsApp link
│   │   ├── CustomCursor.jsx          # Mouse tracking cursor follower
│   │   ├── Footer.jsx / .css         # Site footer & social links
│   │   ├── Gallery.jsx / .css        # Masonry grid, filters, & lightbox
│   │   ├── Hero.jsx / .css           # Three.js starry canvas & typography
│   │   ├── Navbar.jsx / .css         # Floating header & mobile drawer
│   │   ├── PageTransition.jsx        # Framer Motion entrance wrapper
│   │   ├── ParallaxWrapper.jsx       # Scroll-based parallax helper
│   │   ├── Process.jsx               # Workflow steps
│   │   ├── Recognition.jsx           # Certificate verification modal
│   │   ├── ScrollProgress.jsx        # Top reading scroll progress indicator
│   │   ├── SmoothScroll.jsx          # Lenis smooth inertial scroll wrapper
│   │   ├── Stats.jsx                 # Statistical counter milestones
│   │   └── TiltCard.jsx              # 3D interactive tilt container
│   ├── data/
│   │   ├── certificates.js    # Certification metadata
│   │   └── gallery.js         # Photo entries and EXIF specifications
│   ├── App.jsx                # Application root and layout composition
│   ├── index.css              # Global tokens, typography, and utility classes
│   └── main.jsx               # Vite React entry point
├── eslint.config.js           # ESLint configuration
├── index.html                 # HTML document entry with OpenGraph metadata
├── LICENSE                    # MIT License
├── package.json               # Project manifest, scripts, and dependencies
├── vercel.json                # Vercel SPA rewrite configuration
└── vite.config.js             # Vite configuration with chunk splitting
```

---

## Prerequisites

- **Node.js**: Version 18.0.0 or higher
- **npm**: Version 9.0.0 or higher

---

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/nfsprogramming/NFS-Photography.git
   cd NFS-Photography
   ```

2. Install dependencies:
   ```bash
   npm ci
   ```

---

## Development

To start the Vite local development server with hot-module replacement (HMR):

```bash
npm run dev
```

Open your browser and navigate to `http://localhost:5173`.

---

## Code Quality & Linting

Run ESLint across all JavaScript and JSX source files:

```bash
npm run lint
```

---

## Production Build

To compile and optimize assets for production:

```bash
npm run build
```

The output bundle will be generated in the `dist/` directory.

To preview the production build locally:

```bash
npm run preview
```

---

## Configuration

### EmailJS Integration
The contact form in [Contact.jsx](file:///e:/NFS%20Photography/src/components/Contact.jsx) utilizes EmailJS for direct message delivery. Update your Service ID, Template ID, and Public Key in `src/components/Contact.jsx` or extract them to environment variables (`VITE_EMAILJS_SERVICE_ID`, etc.) if needed:

```javascript
emailjs.send(
  'service_gvcc30c',
  'template_qt44l3y',
  form,
  'MMvbBVoBxkE98blQA'
);
```

### Vercel Deployment
Single Page Application (SPA) routing is configured in [vercel.json](file:///e:/NFS%20Photography/vercel.json):
```json
{
  "rewrites": [
    {
      "source": "/:path*",
      "destination": "/index.html"
    }
  ]
}
```

---

## License

This project is licensed under the [MIT License](LICENSE) &copy; 2026 NFS Programming.

