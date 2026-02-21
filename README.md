# Ali Mahmood - Portfolio Website v2

A stunning, modern portfolio website with light/dark theme toggle, beautiful animations, and seamless user experience.

## ✨ What's New in v2

- **🌞 Light Theme Default** - Clean, professional light theme as default
- **🌓 Theme Toggle** - Smooth switch between light and dark modes (persists in localStorage)
- **🎬 Stunning Preloader** - Animated logo reveal with progress bar and floating shapes
- **🎨 Enhanced Animations** - Scroll reveal, parallax effects, card tilt, staggered animations
- **📊 Impact Section** - Showcase measurable results and value delivered
- **🔗 Demo Links** - Project cards now support both repository and demo links
- **📱 Mobile Optimized** - Responsive design with mobile menu

---

## 🚀 Quick Start

### Run Locally

```bash
# Option 1: Python (simplest)
cd portfolio-v2
python -m http.server 8000
# Visit http://localhost:8000

# Option 2: Node.js
npx serve .
# Visit http://localhost:3000

# Option 3: VS Code Live Server
# Right-click index.html → "Open with Live Server"
```

---

## 🎨 Customization Guide

### 1. Adding Your Photo

Find this section in `index.html` (around line 580):

```html
<div class="about-image-placeholder">
    <!-- Replace with: <img src="your-photo.jpg" alt="Muhammad Ali Mahmood"> -->
    <svg>...</svg>
</div>
```

**Replace with:**
```html
<div class="about-image-placeholder">
    <img src="your-photo.jpg" alt="Muhammad Ali Mahmood" style="width: 100%; height: 100%; object-fit: cover;">
</div>
```

---

### 2. Adding/Removing Demo Links on Projects

Each project card has a `project-links` section. Here are all the patterns:

#### Project with BOTH Repository and Demo:
```html
<div class="project-links">
    <a href="https://github.com/alihawk/your-repo" target="_blank" class="project-link">
        <svg><!-- GitHub icon --></svg>
        Repository
    </a>
    <a href="https://your-demo-url.com" target="_blank" class="project-link">
        <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
            <path d="M18 13v6a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2V8a2 2 0 0 1 2-2h6"/>
            <polyline points="15 3 21 3 21 9"/>
            <line x1="10" y1="14" x2="21" y2="3"/>
        </svg>
        Live Demo
    </a>
</div>
```

#### Project with ONLY Repository (no demo):
```html
<div class="project-links">
    <a href="https://github.com/alihawk/your-repo" target="_blank" class="project-link">
        <svg><!-- GitHub icon --></svg>
        Repository
    </a>
    <!-- No demo link -->
</div>
```

#### Confidential Project (no links):
```html
<div class="project-links">
    <span class="project-link disabled">
        <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
            <rect x="3" y="11" width="18" height="11" rx="2" ry="2"/>
            <path d="M7 11V7a5 5 0 0 1 10 0v4"/>
        </svg>
        Confidential
    </span>
</div>
```

---

### 3. Removing a Section (e.g., Honors & Awards)

The Honors & Awards section is already commented out in the code. To remove ANY section:

**Option A: Comment it out (recommended - easy to bring back)**
```html
<!-- 
<section class="your-section" id="your-section">
    ... section content ...
</section>
-->
```

**Option B: Delete the entire section**
Just delete from `<section class="...">` to `</section>`

**Don't forget to also:**
1. Remove the nav link from `<ul class="nav-center">`
2. Remove the mobile menu link from `<div class="mobile-menu">`

---

### 4. Changing Theme Colors

Find the CSS variables at the top of `<style>` (around line 15):

```css
:root {
    /* Light Theme Colors */
    --bg-primary: #fafafa;        /* Main background */
    --bg-secondary: #ffffff;      /* Section backgrounds */
    --accent-primary: #6366f1;    /* Primary purple */
    --accent-secondary: #8b5cf6;  /* Secondary purple */
    --accent-tertiary: #06b6d4;   /* Cyan accent */
    ...
}

[data-theme="dark"] {
    /* Dark Theme Colors */
    --bg-primary: #0f0f1a;
    ...
}
```

---

### 5. Updating Impact Numbers

Find the Impact section and update the `data-count` and `data-suffix` attributes:

```html
<div class="impact-number" data-count="40" data-suffix="%">0%</div>
```

- `data-count` = The target number to animate to
- `data-suffix` = What appears after the number (%, +, x, etc.)

---

### 6. Adding a New Project

Copy this template and paste it inside `<div class="projects-grid">`:

```html
<div class="project-card reveal">
    <div class="project-image">
        <div class="project-image-inner">🆕</div> <!-- Use an emoji or image -->
    </div>
    <div class="project-body">
        <span class="project-category">Category • Type</span>
        <h3 class="project-title">Your Project Title</h3>
        <p class="project-description">
            Description of your project goes here. Keep it concise but informative.
        </p>
        <div class="project-tech">
            <span>Tech1</span>
            <span>Tech2</span>
            <span>Tech3</span>
        </div>
        <div class="project-links">
            <a href="https://github.com/..." target="_blank" class="project-link">
                <svg><!-- GitHub icon --></svg>
                Repository
            </a>
            <a href="https://demo-url.com" target="_blank" class="project-link">
                <svg><!-- External link icon --></svg>
                Live Demo
            </a>
        </div>
    </div>
</div>
```

---

### 7. Adjusting Preloader Duration

Find this in the JavaScript section (around line 1180):

```javascript
window.addEventListener('load', () => {
    setTimeout(() => {
        document.getElementById('preloader').classList.add('hidden');
        document.body.classList.remove('loading');
    }, 2500);  // ← Change this value (milliseconds)
});
```

---

## 🌐 Deployment

### GitHub Pages (FREE)
```bash
git init
git add .
git commit -m "Portfolio website"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPO.git
git push -u origin main
# Go to Settings → Pages → Select "main" branch
```

### Vercel (FREE - Instant)
```bash
npx vercel
# Follow the prompts
```

### Netlify (FREE)
1. Go to [netlify.com](https://netlify.com)
2. Drag and drop the folder
3. Done!

---

## 💡 Domain Name Suggestions

| Domain | Style | Price Range |
|--------|-------|-------------|
| `alimahmood.dev` ⭐ | Professional | $12-15/year |
| `ali.engineer` | Clean | $30-40/year |
| `alibuilds.io` | Creative | $30-40/year |
| `mahmoodali.com` | Traditional | $10-12/year |

**Where to buy:**
- [Namecheap](https://namecheap.com) - Best deals
- [Cloudflare](https://cloudflare.com) - No markup pricing
- [Porkbun](https://porkbun.com) - Very affordable

---

## 📁 File Structure

```
portfolio-v2/
├── index.html      # Everything in one file (HTML + CSS + JS)
├── README.md       # This file
└── assets/         # (Optional) Add images here
    ├── photo.jpg   # Your professional photo
    └── resume.pdf  # Your resume (optional)
```

---

## 🎯 Key Features

| Feature | Description |
|---------|-------------|
| **Preloader** | Animated logo with progress bar |
| **Theme Toggle** | Light/Dark mode with localStorage persistence |
| **Scroll Animations** | Reveal, parallax, and stagger effects |
| **Card Tilt** | 3D tilt effect on hover (desktop) |
| **Counter Animation** | Numbers animate when in view |
| **Impact Section** | Showcase measurable achievements |
| **Mobile Menu** | Hamburger menu with smooth transitions |
| **Floating Shapes** | Animated background elements |

---

## 🔧 Browser Support

- Chrome 80+
- Firefox 75+
- Safari 13+
- Edge 80+

---

## 📝 License

MIT - Feel free to use and modify!

---

**Built with ❤️ by Muhammad Ali Mahmood**
