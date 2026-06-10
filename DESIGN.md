# Aref's Portfolio Website — Design & Documentation (Continuous-Scroll Version)

## Current Version: Continuous-Scroll Design (May 2026)

### Latest Updates

**Recent Implementation (Current Session):**
- ✅ Complete redesign from terminal aesthetic to modern continuous-scroll portfolio
- ✅ Integrated Excalidraw SVG graphics (whoami.svg, Projects.svg)
- ✅ Integrated SVG icons for contact and stack sections (phone-calling-svgrepo-com.svg, experience-information-knowledge-svgrepo-com.svg)
- ✅ Removed white backgrounds from SVGs for full transparency
- ✅ Made `.section-visual` containers transparent to blend seamlessly with page background
- ✅ Implemented rotating typewriter tagline in sticky header
- ✅ Responsive design with mobile breakpoints (single column on ≤768px)
- ✅ Smooth scroll behavior with Intersection Observer animations

### Design Direction

A **modern, visually elegant** continuous-scroll portfolio that showcases work through hand-drawn Excalidraw graphics and clean typography. The design emphasizes:
- **Visual hierarchy** with full-height sections and alternating backgrounds
- **Hand-drawn aesthetics** integrating Excalidraw SVGs for personality
- **Light, modern color palette** from Catppuccin Mocha adapted for light backgrounds
- **Smooth interactions** with typewriter animations and scroll-based reveals
- **Accessibility** with semantic HTML and readable color contrast

## Overview (Archived)

A **premium, visually sophisticated** terminal-themed personal portfolio website that mimics a real terminal session with **exceptional attention to aesthetic details**. *(This was the initial design direction before pivoting to continuous-scroll.)*

**Previous Aesthetic Direction**: Brutalist retro-futurism with maximalist motion—bold colors, atmospheric depth, intentional visual effects, and responsive feedback on every interaction. *(Archived for reference.)*

## Visual Design

### Color Palette (Current: Light Catppuccin Mocha)

Based on user's terminal configuration (Catppuccin Mocha), adapted for light mode:

**Primary Colors**
- Background: `#F5F5F7` (soft off-white)
- Alternate Background: `#EBEBF0` (light gray)
- Foreground/Text: `#1E1E2E` (dark charcoal)
- Foreground Light: `#45475A` (medium gray)

**Accent Colors**
- Cyan: `#94E2D5` (bright teal/cyan)
- Magenta: `#F5C2E7` (soft pink/magenta)
- Yellow: `#F9E2AF` (warm yellow)
- Blue: `#89B4FA` (periwinkle blue)

### Typography

- **Font**: JetBrains Mono (loaded from Google Fonts)
- **Fallback**: System monospace
- **Base Font Size**: 1em, scales responsively
- **Line Height**:
  - Body text: 1.6em
  - Section descriptions: 1.8em for better readability
- **Font Weights**: 400 (regular), 500 (medium), 700 (bold)

### Layout

**Header (Sticky)**
```
┌────────────────────────────────────────┐
│ Aref: [rotating tagline text]          │
│ ↓ scroll to explore                    │
└────────────────────────────────────────┘
```

**Page Sections (Full-height, alternating backgrounds)**
```
┌────────────────────────────────────────┐
│  whoami                    [SVG Visual]│
│  (Text on left)                        │
└────────────────────────────────────────┘

┌────────────────────────────────────────┐
│  [SVG Visual]              projects    │
│                           (Text on R)  │
└────────────────────────────────────────┘

┌────────────────────────────────────────┐
│  contact                   [SVG Icon] │
│  (Text on left)                        │
└────────────────────────────────────────┘

┌────────────────────────────────────────┐
│  [SVG Icon]                stack       │
│                           (Text on R)  │
└────────────────────────────────────────┘
```

**Responsive (Mobile ≤768px)**
- Single column layout
- Text above visual/icon
- Full-width sections
- Reduced padding

### Key Visual Elements

1. **Sticky Header**
   - Title: `Aref:` (cyan) + rotating tagline (yellow)
   - Tagline cycles through 6 different descriptions
   - Typewriter effect: ~50ms per character to type, ~30ms to delete
   - Scroll hint: `↓ scroll to explore` in light gray
   - Backdrop blur effect with semi-transparent white
   - `position: sticky; top: 0; z-index: 100`

2. **Full-Height Sections**
   - `min-height: 100vh` for each section
   - Grid layout: 2 columns on desktop (1fr 1fr gap: 60px)
   - Alternating backgrounds: `--bg` and `--bg-alt`
   - Smooth fade-in animation on scroll (`section-fade-in` keyframes)
   - Responsive: single column on mobile

3. **Section Text Content**
   - Section title: 2.5em, bold, dark text
   - Title spans in cyan accent color
   - Description: 1.1em, light gray, pre-wrapped (preserves formatting)
   - Clean monospace typography with proper line spacing

4. **Visual Elements (SVGs)**
   - `width: 100%; height: 100%; object-fit: contain`
   - Transparent background (no white boxes)
   - Hand-drawn Excalidraw graphics for personality
   - Scalable and crisp at any resolution
   - SVG icons from SVGRepo for contact/stack sections

5. **Contact Section Special**
   - Contact info displayed inline in description text
   - Phone icon SVG visual
   - Links with contact details (GitHub, Email, LinkedIn)

6. **Stack Section**
   - Tech stack displayed as formatted text
   - Languages, environment, tools listed with arrows
   - Experience/knowledge icon visual

### Animations & Interactions

- **Typewriter Tagline**: Character-by-character typing (~50ms per char), deletion (~30ms per char), 2.5s pause between cycles
- **Section Fade-In**: Intersection Observer triggers `section-fade-in` animation (0.8s ease-out) when section enters viewport
- **Smooth Scroll**: HTML `scroll-behavior: smooth` for all internal navigation
- **Hover Effects**: Subtle color transitions (0.2s) on interactive elements
- **Title Animation**: Initial fade-in on page load (0.8s ease-out)

## Interaction Flow

### Initial Load
1. Page renders with sticky header
2. Title: "Aref:" + initial tagline displayed instantly
3. Typewriter animation starts: cycles through 6 taglines continuously
4. Scroll hint appears below
5. Sections load with fade-in animations as user scrolls

### User Scrolling
1. Page scrolls smoothly with `scroll-behavior: smooth`
2. As each section enters viewport (threshold: 10%), Intersection Observer triggers fade-in animation
3. SVG graphics display transparently against background colors
4. Text content remains statically positioned

### Tagline Animation (Continuous)
1. Current tagline types out character-by-character (50ms per character)
2. Holds displayed for 2.5 seconds
3. Deletes character-by-character (30ms per character)
4. 300ms pause
5. Next tagline begins typing
6. Cycles repeat indefinitely through array of 6 taglines:
   - "an open source contributor"
   - "a backend engineer"
   - "a systems enthusiast"
   - "a problem solver"
   - "crafting elegant code"
   - "always learning"

### Responsive Behavior
- Desktop (>768px): Grid layout with text and SVG side-by-side
- Mobile (≤768px): Single column with text above SVG/icon

## Section Content

### whoami Section
**Visual**: Hand-drawn stick figure with question mark (whoami.svg)
**Content**:
```
Aref

AUS CS student, graduating Spring 2026
Systems & backend enthusiast
Linux advocate (currently daily-driving Nobara/Niri)
Always tinkering with low-level systems
```

### projects Section
**Visual**: Complex hand-drawn architecture diagram (Projects.svg)
**Content**: Five projects with descriptions
```
LipSync/
Real-time lip reading system for AR
Jetson Orin + Vuzix Z-4K glasses
Custom ONNX model pipeline

CICD Is Overrated/
FastAPI app with full CI/CD pipeline
Six parallel GitHub Actions jobs (lint, test, coverage, type-check, security, audit)
Auto-versioning with semantic-release, Docker deployment to GHCR

Tracer/
CLI tool: scans repos & generates Mermaid diagrams
Supports Python, JS/TS, Rust, Go, Java, C++
No LLM required — works with local paths & GitHub URLs

repo2mermaid/
CLI tool: convert codebases to architecture diagrams
Automated visual documentation

cv-tailor/
Claude API + LaTeX integration
AI-powered CV tailoring
```

### contact Section
**Visual**: Phone icon (phone-calling-svgrepo-com.svg)
**Content**:
```
Open to opportunities, questions, or just chatting about systems! Reach out and let's connect.

GitHub: https://github.com/Aref
Email: aref@email.com
LinkedIn: https://linkedin.com/in/Aref
```

### stack Section
**Visual**: Knowledge/experience icon (experience-information-knowledge-svgrepo-com.svg)
**Content**: Tech stack and tools
```
Languages:
Go - systems, networking, tooling
Rust - performance-critical, embedded
C - low-level, kernel work
Python - scripting, automation, tooling
Java - enterprise, backend systems

Environment:
Linux - Nobara / Niri (Wayland compositor)
Shell - Fish shell
Editor - Neovim + custom config

Currently exploring: eBPF, async runtimes, distributed systems
```

## Responsive Design

### Desktop (>768px)
- Two-column grid layout: section text on left/right, SVG visual on opposite side
- Alternating layouts for visual interest
- Comfortable padding (60px) and spacing (gap: 60px)
- Standard font sizes (2.5em titles, 1.1em body)
- Full SVG/icon display at max dimensions

### Mobile/Tablet (≤768px)
- Single-column layout: text stacked above SVG/icon
- Reduced padding (40px vertical, 20px horizontal)
- Smaller section titles (1.8em)
- Smaller body text (1em)
- SVG containers: `min-height: 300px` (reduced from 400px)
- Header padding reduced (15px)
- All touch targets maintain ≥44px for accessibility

## Technical Stack

- **HTML**: Semantic structure with section elements
- **CSS**: Custom properties, grid/flexbox layouts, responsive design
- **JavaScript**: Async/await for typewriter effect, Intersection Observer for scroll animations
- **Assets**: 4 SVG files (whoami.svg, Projects.svg, phone-calling-svgrepo-com.svg, experience-information-knowledge-svgrepo-com.svg)
- **Fonts**: Google Fonts (JetBrains Mono)
- **Deployment**: Static hosting (GitHub Pages, Netlify, Vercel, custom server)

## ✨ Implementation Summary (Current Version)

### Frontend Architecture
- **Single HTML File**: All-in-one implementation with embedded CSS and JavaScript
- **Framework**: Vanilla JavaScript (no dependencies)
- **Fonts**: Google Fonts (JetBrains Mono)
- **Graphics**: Excalidraw SVGs + SVGRepo icons
- **Styling**: CSS custom properties (variables) for theming

### Key Features Implemented
1. **Rotating Typewriter Tagline**
   - Async/await pattern with character-by-character typing
   - 6 rotating descriptions cycling continuously
   - CSS animations for smooth visual appearance

2. **Scroll-based Animations**
   - Intersection Observer API monitors section visibility
   - Fade-in animations trigger when sections enter viewport
   - `scroll-behavior: smooth` for native scroll smoothing

3. **Transparent SVG Integration**
   - Removed white background rectangles from Excalidraw exports
   - Used `background: transparent` on `.section-visual` containers
   - `object-fit: contain` ensures proper scaling

4. **Responsive Grid Layout**
   - CSS Grid for desktop (2 columns)
   - Media query breakpoint at 768px
   - Flexbox fallback for mobile (single column)

5. **Color System**
   - CSS custom properties (--bg, --fg, --accent-cyan, etc.)
   - Catppuccin Mocha color palette
   - Light mode adaptation for modern aesthetic

### Performance Optimizations
- Single HTTP request (one HTML file)
- No external build process needed
- Static file deployment anywhere
- Efficient Intersection Observer for animations

## Remaining Potential Improvements

### High Priority

1. **Project Card Expansion**
   - Click on a project in `ls projects/` to see more details
   - Could show: GitHub links, live demos, tech stack used, dates
   - Example: `cd LipSync/` → shows README-like details

2. **Experience/Resume Section**
   - New command: `cat resume.txt` or `history --jobs`
   - List internships, work experience, key accomplishments
   - Timeline format or bullet points

3. **Blog/Articles**
   - Command: `ls blog/` → lists recent posts
   - Click to expand: `cat blog/post-title.txt`
   - Showcase writing, tutorials, technical insights

4. **Interactive Features**
   - Keyboard support: Allow actual typing instead of just buttons
   - Command history with arrow keys
   - Search functionality (`grep`)
   - Tab completion suggestions

5. **Enhanced Project Details**
   - Real GitHub repo links (clickable)
   - GitHub stats: stars, language breakdown
   - Live demo links where applicable
   - Pull in real-time data from GitHub API

### Medium Priority

6. **Additional Visual Improvements**
   - Color-coded output sections (warnings in red, success in green)
   - Glitch effects on error states
   - More sophisticated cursor styles (underscore variant)
   - Different prompt styling based on context

7. **Additional Animation Enhancements**
   - Option to slow down/speed up typing animation
   - Smooth height transitions for expanding sections
   - Optional "screen burn-in" effect overlay
   - Matrix-style rain effect on long idle times

8. **More Theme Variants**
   - Add color schemes: Dracula, Nord, Solarized, Cyberpunk, Retro
   - System preference detection (`prefers-color-scheme`)
   - Quick toggle between multiple themes (dropdown menu)

9. **Sound Effects** (optional)
   - Subtle keyboard typing sounds
   - Beep on command completion
   - Option to toggle audio

10. **Performance & PWA**
    - Service Worker for offline support
    - Icon and manifest for installable PWA
    - Lazy-load images (if added)

### Lower Priority

11. **Social Links & Metadata**
    - Open Graph tags for better sharing
    - Favicon with terminal symbol
    - Social media preview image
    - Twitter/OG metadata

12. **Analytics**
    - Track which sections are most viewed
    - Scroll depth metrics
    - Command popularity

13. **Advanced Terminal Features**
    - `man <command>` → show help/details
    - `whoami --verbose` → expanded version
    - `pwd` → show current directory (for navigation context)
    - `echo` → custom input handling

14. **Database/Backend** (if needed)
    - Store visitor messages
    - Contact form submission
    - Blog comments
    - Project view counts

15. **Mobile-Specific**
    - Fullscreen mode option
    - Haptic feedback on button taps
    - Landscape/portrait optimization
    - Swipe gestures for navigation

## File Structure

```
portfolioWebsite/
├── index.html                                    # Main file (all-in-one HTML/CSS/JS)
├── whoami.svg                                    # Hand-drawn stick figure
├── Projects.svg                                  # Complex project diagram
├── phone-calling-svgrepo-com.svg               # Contact section icon
├── experience-information-knowledge-svgrepo-com.svg  # Stack section icon
├── DESIGN.md                                    # This documentation
└── README.md                                    # (optional) Deployment instructions
```

### Asset Specifications
- **whoami.svg**: 138×187px viewBox (displays at 300×400px max)
- **Projects.svg**: 408×490px viewBox (displays at 400×400px max)
- **phone-calling-svgrepo-com.svg**: 24×24px viewBox (scalable)
- **experience-information-knowledge-svgrepo-com.svg**: 64×64px viewBox (scalable)

## Deployment Options

- **GitHub Pages**: Push to repo, enable Pages in settings
- **Netlify**: Drag & drop the file or connect Git repo
- **Vercel**: Simple static hosting
- **Custom Server**: Serve as-is, no build step needed

## Browser Support

- Modern browsers (Chrome, Firefox, Safari, Edge)
- Mobile browsers (iOS Safari, Chrome Android)
- Requires: CSS Grid/Flexbox, CSS custom properties, ES6 JavaScript
- Graceful degradation for older browsers (layout may shift slightly)

## Future Vision

The ultimate version could become a full-featured terminal emulator in the browser with:
- Real command execution (via backend API)
- File system simulation
- Interactive tutorials
- Network requests via terminal
- Multiplayer collaborative terminal sessions

But for now, keeping it simple, fast, and visually polished is the goal. 🚀
