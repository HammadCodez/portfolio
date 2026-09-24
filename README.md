# CS344: Web Engineering — Lab 03: HTML Advanced - Personal Portfolio II

**Student Name**: Muhammad Hammad Butt  
**Registration Number**: 501399  
**Class / Section**: Section-B  
**Institution**: National University of Sciences and Technology (NUST) — SEECS  
**Live GitHub Pages URL**: `https://hammadkodez.github.io/portfolio/`  
**GitHub Repository**: `https://github.com/HammadKodez/portfolio`  

---

## 1. Project Overview

This repository represents the official submission for **Lab 03: HTML Advanced - Personal Portfolio II** in the CS344 Web Engineering course. The project elevates the multi-page portfolio built in Lab 02 into an enterprise-grade, responsive visual showcase adhering strictly to the **CSS Float and Clear System**, **External Stylesheets**, and **Zero-JavaScript** architectural constraints.

### Key Highlights
- **100% Strict External CSS**: All layout, typographic, color, and responsive rules reside exclusively within `css/style.css`. There are **zero inline styles** (`style="..."`) and **zero internal `<style>` tags** across all pages.
- **Float & Clear Architecture**: Complete navigation, hero staging, content sections, image galleries, and multi-column footers are engineered using vanilla CSS `float: left`, `float: right`, and modern micro-clearfix hacks.
- **Zero JavaScript Runtime**: To strictly comply with Lab 03's explicit "Usage of Javascript" pitfall clause, all components (interactive navigation, Pinterest-style image gallery, contact dispatch form, and skill matrices) function purely through HTML5 semantics and CSS3 pseudo-classes.
- **Pure Vanilla CSS**: Built with zero external CSS libraries or frameworks (no Bootstrap, Tailwind, or external design APIs).
- **Consolidated Media Assets**: All visual assets are centralized in the standard `images/` directory with cross-platform lowercase aliases.

---

## 2. Mandatory Lab 03 Specifications & Implementation

### A. Navigation Menu (Float & Clear)
- **Implementation**: The horizontal navigation links inside `.top-nav-capsule` and `.top-left-group` are styled horizontally using `float: left`.
- **Clearing Mechanism**: The parent container `.top-bar-container` employs the micro-clearfix pseudo-element (`::after { content: ""; display: table; clear: both; }`), guaranteeing that the header container encloses all floated navigation nodes without collapse.

### B. Content Layout (Side-by-Side Images & Text)
- **Implementation**: In `index.html` (Engineer Profile Section) and `contact.html` (Inquiry Grid), content is structured into side-by-side columns:
  - Left column: `.side-img-col { float: left; width: 38%; }`
  - Right column: `.side-text-col { float: right; width: 60%; }`
- **Clearing Mechanism**: Clearfix hacks ensure that succeeding sections (such as Stats and Projects) clear the floated columns completely without overlapping.

### C. Image Gallery (Float & Clear Pinterest Layout)
- **Implementation**: In `gallery.html`, 20 personal high-resolution photographs capturing university life at NUST SEECS, startup incubation at NSTP Hatch 8, and technical sessions are organized into 4 vertical columns:
  - Each column: `.gallery-pin-col { float: left; width: 23.5%; margin-right: 2%; }` (last column has `margin-right: 0`).
  - Container: `.gallery-pinterest-container::after { content: ""; display: table; clear: both; }`
- **Design Philosophy**: Fulfills the user requirement for a Pinterest-style, full-bleed visual showcase with authentic photo aspect ratios, clean mono indexing, and zero project thumbnails.

### D. Side-by-Side Hobbies Cards
- **Implementation**: In `hobbies.html`, each hobby entry is an independent card with `.hobby-img-floated { float: left; width: 140px; height: 140px; margin-right: 18px; }` and `.hobby-content-floated { overflow: hidden; }` forming a block formatting context beside the image.

### E. Multi-Column Floated Footer
- **Implementation**: In all pages, the footer divides into a primary 40% brand column (`float: left; width: 40%;`) and three 20% navigation columns (`float: left; width: 20%;`), fully contained by `.footer-content::after { clear: both; }`.

---

## 3. Directory & File Structure

```
portfolio/
├── .gitignore               # Ignores sensitive PDFs, archives, temporary files
├── 404.html                 # Custom 404 error page (pure CSS float layout)
├── contact.html             # Pure HTML5 side-by-side contact form & info
├── gallery.html             # Pinterest-style 20-photo gallery with float: left
├── hobbies.html             # Side-by-side floated hobby cards & daily routine
├── home.html                # Alternative root page matching index.html
├── index.html               # Main portfolio landing page with hero & side-by-side bio
├── projects.html            # 9 production projects in float-based 3-column grid
├── skills.html              # Multi-column competency matrices with pure CSS bars
├── css/
│   └── style.css            # 100% complete external stylesheet for all 8 pages
├── images/                  # 34 verified image assets (personal photos & thumbnails)
│   ├── hammad-portrait.png
│   ├── hammad-nstp-portrait.jpeg
│   ├── nstp-cohort-group.jpeg
│   ├── nstp-hall.jpeg
│   ├── me-01.jpg ... me-16.jpeg
│   ├── hobby-books.jpg
│   ├── hobby-fitness.jpg
│   ├── hobby-gaming.jpg
│   └── letseetechthumb.png ...
└── README.md                # Comprehensive documentation & deployment instructions
```

---

## 4. Verification & Quality Assurance Summary

| Checkpoint | Requirement | Result |
| :--- | :--- | :--- |
| **External CSS Only** | All styles in `css/style.css` | **PASS (100%)** |
| **Zero `<style>` Tags** | No internal CSS in any HTML file | **PASS (0 detected)** |
| **Zero Inline Styles** | No `style="..."` attributes | **PASS (0 detected)** |
| **Zero JavaScript** | No `<script>` tags, no JS dependencies | **PASS (0 detected)** |
| **Float Navigation** | `float: left` on links + clearfix | **PASS** |
| **Float Content Layout** | Side-by-side image & text with clear | **PASS** |
| **Float Gallery Grid** | At least 5 images aligned with float | **PASS (20 images)** |
| **Asset Integrity** | All image references point to valid files | **PASS (34 images valid)** |
| **Privacy Protection** | No resume/CV files or downloadable links | **PASS (Completely removed)** |

---

## 5. Local Setup & Testing

To inspect the portfolio locally:

1. Clone or download the repository:
   ```bash
   git clone https://github.com/HammadKodez/portfolio.git
   cd portfolio
   ```

2. Start a lightweight static web server:
   ```bash
   python -m http.server 8000
   ```

3. Open your browser and navigate to:
   ```
   http://localhost:8000
   ```

4. Verify across viewports (Desktop `1440px`, Tablet `768px`, Mobile `375px`) to observe responsive float collapsing and clear behavior.

---

## 6. GitHub Pages Deployment Instructions

1. Initialize git (if not already done) and stage the production files:
   ```bash
   git init
   git add .
   git commit -m "Complete CS344 Web Engineering Lab 03 Migration"
   ```

2. Push to GitHub:
   ```bash
   git branch -M main
   git remote add origin https://github.com/HammadKodez/portfolio.git
   git push -u origin main
   ```

3. Enable GitHub Pages:
   - Navigate to the repository on GitHub: `Settings > Pages`.
   - Under **Build and deployment > Source**, select **Deploy from a branch**.
   - Choose `main` branch and `/ (root)` folder.
   - Click **Save**.
   - Within 1–2 minutes, GitHub Pages will deploy the portfolio live at:  
     `https://hammadkodez.github.io/portfolio/`
