# Digital Vault Redesign Specification

This document details the redesigned static website layout and styling system for the **Digital Vault** landing page, reflecting a "Premium Cyber-Security" aesthetic.

## 🎨 Design System & Rationale

### 1. Cyber-Security Color Scheme
- **Background (`--bg`)**: `#0b0f17` (Deep space slate).
- **Cards/Panels (`--panel`)**: `rgba(17, 24, 39, 0.75)` (Semi-transparent dark slate).
- **Accents**: 
  - Cyber Blue (`--accent` / `#38bdf8`) for high-tech glow and primary indicators.
  - Active Blue (`--accent-strong` / `#0ea5e9`) for hover transitions.
  - Gold/Amber accent glow (`rgba(255, 215, 0, 0.05)`) optionally utilized to highlight security shields.
- **Typography**: 
  - Headings: `Outfit` (sleek, geometric, modern sans-serif).
  - Body: `Plus Jakarta Sans` (highly legible, clean, tech-oriented sans-serif).

### 2. Glassmorphism Utilities
- **Cards**: Soft borders (`rgba(255, 255, 255, 0.08)`), thick backdrop blur (`16px`), and deep shadows to establish layering.
- **Elevations**: Hovering shifts cards up `4px` and blends a cyan shadow glow (`rgba(56, 189, 248, 0.25)`) to give it an interactive, responsive feel.

---

## 📄 Code Listings

### 1. Stylesheet (`assets/styles.css`)

```css
@import url('https://fonts.googleapis.com/css2?family=Outfit:wght@300;400;500;600;700;800&family=Plus+Jakarta+Sans:wght@300;400;500;600;700&display=swap');

:root {
  color-scheme: dark;
  --bg: #0b0f17;
  --panel: rgba(17, 24, 39, 0.75);
  --text: #f3f4f6;
  --muted: #9ca3af;
  --border: rgba(255, 255, 255, 0.08);
  --accent: #38bdf8;
  --accent-strong: #0ea5e9;
  --accent-glow: rgba(56, 189, 248, 0.12);
  --shadow: 0 20px 40px rgba(0, 0, 0, 0.45);
}

* {
  box-sizing: border-box;
}

html {
  scroll-behavior: smooth;
}

body {
  margin: 0;
  font-family: 'Plus Jakarta Sans', -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;
  line-height: 1.6;
  color: var(--text);
  background: 
    radial-gradient(circle at top right, rgba(14, 165, 233, 0.12), transparent 45%),
    radial-gradient(circle at 10% 40%, rgba(37, 99, 235, 0.08), transparent 35%),
    var(--bg);
  min-height: 100vh;
}

a {
  color: var(--accent);
  text-decoration: none;
  transition: color 0.2s ease;
}

a:hover {
  color: var(--accent-strong);
}

.page-shell {
  width: min(1100px, calc(100% - 2rem));
  margin: 0 auto;
  padding: 1.5rem 0 3rem;
}

.page-shell-narrow {
  width: min(820px, calc(100% - 2rem));
}

.site-header,
.site-footer {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 1rem;
}

.site-header {
  padding: 0.5rem 0 2rem;
}

.site-footer {
  margin-top: 3rem;
  padding: 2rem 0 0.5rem;
  border-top: 1px solid var(--border);
  color: var(--muted);
  flex-wrap: wrap;
  font-size: 0.9rem;
}

.brand {
  color: var(--text);
  text-decoration: none;
  font-weight: 800;
  letter-spacing: -0.01em;
  font-family: 'Outfit', sans-serif;
  display: inline-flex;
  align-items: center;
  gap: 0.75rem;
  font-size: 1.35rem;
}

.brand img {
  width: 36px;
  height: 36px;
  border-radius: 10px;
  box-shadow: 0 4px 12px rgba(56, 189, 248, 0.2);
}

.site-nav {
  display: flex;
  gap: 1.5rem;
  flex-wrap: wrap;
  align-items: center;
}

.site-nav a {
  color: var(--muted);
  font-weight: 500;
}

.site-nav a:hover {
  color: var(--accent);
}

.site-nav a.lang-switch {
  background: rgba(255, 255, 255, 0.05);
  border: 1px solid var(--border);
  padding: 0.3rem 0.65rem;
  border-radius: 6px;
  font-size: 0.85rem;
}

.site-nav a.lang-switch:hover {
  background: var(--accent-glow);
  border-color: var(--accent);
}

.card {
  background: var(--panel);
  border: 1px solid var(--border);
  border-radius: 28px;
  box-shadow: var(--shadow);
  backdrop-filter: blur(16px);
  transition: transform 0.3s cubic-bezier(0.16, 1, 0.3, 1), border-color 0.3s ease, box-shadow 0.3s ease;
}

.hero {
  padding: clamp(2.5rem, 6vw, 4.5rem) clamp(1.5rem, 4vw, 3rem);
  text-align: center;
  display: flex;
  flex-direction: column;
  align-items: center;
  position: relative;
  overflow: hidden;
  background: radial-gradient(circle at bottom, rgba(56, 189, 248, 0.07), transparent 60%), var(--panel);
}

.hero:hover {
  transform: translateY(-2px);
  border-color: rgba(56, 189, 248, 0.2);
  box-shadow: 0 30px 60px rgba(0, 0, 0, 0.5), 0 0 30px rgba(56, 189, 248, 0.05);
}

.eyebrow {
  margin: 0 0 1.25rem;
  font-size: 0.82rem;
  letter-spacing: 0.15em;
  text-transform: uppercase;
  color: var(--accent);
  font-weight: 700;
  background: rgba(56, 189, 248, 0.08);
  padding: 0.35rem 1rem;
  border-radius: 999px;
  border: 1px solid rgba(56, 189, 248, 0.2);
  display: inline-block;
  font-family: 'Outfit', sans-serif;
}

h1,
h2,
h3,
p {
  margin-top: 0;
}

h1, h2, h3 {
  font-family: 'Outfit', sans-serif;
}

h1 {
  font-size: clamp(2.2rem, 5vw, 3.8rem);
  line-height: 1.1;
  margin-bottom: 1.25rem;
  background: linear-gradient(135deg, #ffffff 40%, #a5b4fc 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  font-weight: 800;
  letter-spacing: -0.02em;
}

h2 {
  font-size: clamp(1.6rem, 3vw, 2.2rem);
  line-height: 1.2;
  margin-bottom: 0.85rem;
  background: linear-gradient(135deg, #ffffff 60%, #9ca3af 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  font-weight: 700;
  letter-spacing: -0.01em;
}

h3 {
  font-size: 1.2rem;
  line-height: 1.3;
  margin-bottom: 0.65rem;
  color: #ffffff;
}

.lead {
  font-size: 1.15rem;
  color: var(--muted);
  max-width: 60ch;
  line-height: 1.6;
}

.section-heading {
  margin: 4rem 0 2rem;
  text-align: center;
}

.section-heading .eyebrow {
  margin-bottom: 0.85rem;
}

.section-lead {
  color: var(--muted);
  max-width: 64ch;
  margin: 0 auto;
  font-size: 1.05rem;
}

.hero-links {
  display: flex;
  gap: 1rem;
  flex-wrap: wrap;
  margin-top: 2rem;
  justify-content: center;
}

.vault-note {
  margin: 2rem 0 0;
  padding-top: 1.5rem;
  border-top: 1px solid var(--border);
  color: var(--muted);
  font-size: 0.9rem;
}

.button {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  min-height: 3.25rem;
  padding: 0.85rem 2rem;
  border-radius: 999px;
  font-weight: 600;
  transition: all 0.2s cubic-bezier(0.16, 1, 0.3, 1);
  font-size: 1rem;
}

.button-primary {
  color: #0b0f17;
  background: linear-gradient(135deg, var(--accent) 0%, #60a5fa 100%);
  border: none;
  box-shadow: 0 6px 20px rgba(56, 189, 248, 0.25);
}

.button-primary:hover {
  transform: translateY(-2px);
  box-shadow: 0 10px 25px rgba(56, 189, 248, 0.4);
  background: linear-gradient(135deg, #0ea5e9 0%, #3b82f6 100%);
  color: #ffffff;
}

.button-secondary {
  color: var(--text);
  background: rgba(255, 255, 255, 0.05);
  border: 1px solid var(--border);
}

.button-secondary:hover {
  background: rgba(255, 255, 255, 0.09);
  transform: translateY(-2px);
  border-color: rgba(255, 255, 255, 0.2);
}

.feature-section {
  margin-top: 1.5rem;
}

.feature-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 1.25rem;
}

.feature-card {
  padding: 1.75rem;
  border-radius: 24px;
}

.feature-card:hover {
  transform: translateY(-4px);
  border-color: rgba(56, 189, 248, 0.25);
  box-shadow: 0 25px 50px rgba(0, 0, 0, 0.5), 0 0 25px rgba(56, 189, 248, 0.07);
}

.page-content {
  padding: 2.25rem 2.25rem;
  border-radius: 24px;
}

.page-content a {
  overflow-wrap: anywhere;
}

.page-content h2 {
  margin-top: 2rem;
  color: #ffffff;
  font-size: 1.45rem;
}

.page-content p:last-child {
  margin-bottom: 0;
}

.muted {
  color: var(--muted);
}

.android-first {
  margin-top: 2rem;
  padding: 2rem;
  text-align: center;
  background: radial-gradient(circle at top left, rgba(56, 189, 248, 0.04), transparent 50%), var(--panel);
}

.android-first .eyebrow {
  margin-bottom: 1rem;
}

.android-first p {
  max-width: 64ch;
  margin: 0 auto;
  color: var(--muted);
}

ul {
  padding-left: 1.2rem;
}

li + li {
  margin-top: 0.45rem;
}

@media (max-width: 800px) {
  .site-header,
  .site-footer {
    align-items: flex-start;
    flex-direction: column;
    gap: 1.25rem;
  }

  .page-shell {
    width: min(1100px, calc(100% - 1.5rem));
  }
}
```
