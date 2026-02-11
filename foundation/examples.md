# Foundation Examples

Positive and negative calibration pairs. These are the most powerful component of the taste system — they show, not tell.

---

## 1. Hero Section

### Good

```html
<section class="hero">
  <div class="hero-content">
    <h1>We design spaces that<br>people remember</h1>
    <p>Architecture and interior design for hospitality, residential, and cultural projects across Europe.</p>
    <a href="/projects" class="hero-link">View our work</a>
  </div>
</section>
```

```css
.hero {
  padding: var(--space-40) var(--space-8);
  min-height: 80vh;
  display: flex;
  align-items: flex-end;
}

.hero-content {
  max-width: 680px;
}

.hero h1 {
  font-family: var(--font-display);
  font-size: clamp(2.5rem, 5vw, 3.75rem);
  font-weight: 500;
  line-height: 1.1;
  letter-spacing: -0.03em;
  color: var(--color-text-primary);
  margin-bottom: var(--space-6);
}

.hero p {
  font-size: var(--text-lg);
  line-height: 1.5;
  color: var(--color-text-secondary);
  max-width: 540px;
  margin-bottom: var(--space-8);
}

.hero-link {
  font-size: var(--text-base);
  color: var(--color-accent);
  text-decoration: underline;
  text-underline-offset: 4px;
}
```

**Why this works:** Typography does the heavy lifting. The headline is large enough to command attention without a background image. Generous bottom padding pushes content down, creating space that feels intentional. The CTA is a simple text link — not a button demanding attention. Content is constrained to a readable width.

### Bad

```html
<section class="hero" style="background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);">
  <div class="hero-overlay"></div>
  <div class="hero-content">
    <span class="hero-badge">✨ Award Winning</span>
    <h1>WELCOME TO OUR <span class="gradient-text">AMAZING</span> STUDIO</h1>
    <p>We are a world-class team of passionate designers and developers creating stunning digital experiences that push boundaries and transform brands.</p>
    <div class="hero-buttons">
      <button class="btn-primary pulse-animation">GET STARTED NOW</button>
      <button class="btn-secondary">Watch Video ▶</button>
    </div>
  </div>
  <div class="scroll-indicator bounce">↓ Scroll Down</div>
</section>
```

**Why this fails:** Gradient background competes with content. Badge ("Award Winning") is self-congratulatory decoration. All-caps headline with gradient text is visual noise. The copy is generic ("world-class", "stunning", "push boundaries"). Two CTAs compete for attention. Pulse animation on the button is desperate. Scroll indicator patronizes the user.

---

## 2. Navigation

### Good

```html
<header class="site-header">
  <nav class="nav" aria-label="Main navigation">
    <a href="/" class="nav-logo">Studio Name</a>
    <ul class="nav-links" role="list">
      <li><a href="/projects">Projects</a></li>
      <li><a href="/about">About</a></li>
      <li><a href="/contact">Contact</a></li>
    </ul>
  </nav>
</header>
```

```css
.site-header {
  position: sticky;
  top: 0;
  z-index: 10;
  background-color: var(--color-bg);
}

.nav {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: var(--space-4) var(--space-8);
  max-width: 1280px;
  margin: 0 auto;
}

.nav-logo {
  font-weight: 500;
  font-size: var(--text-base);
  color: var(--color-text-primary);
  text-decoration: none;
}

.nav-links {
  display: flex;
  gap: var(--space-8);
  list-style: none;
  padding: 0;
  margin: 0;
}

.nav-links a {
  font-size: var(--text-sm);
  color: var(--color-text-secondary);
  text-decoration: none;
  transition: color 150ms ease;
}

.nav-links a:hover {
  color: var(--color-text-primary);
}

.nav-links a:focus-visible {
  outline: 2px solid var(--color-accent);
  outline-offset: 4px;
  border-radius: 2px;
}
```

**Why this works:** Three links — that's all most sites need. Logo is text, not an oversized image. Nav is sticky but unobtrusive (same background as page). Links are secondary color that darken on hover — subtle, not flashy. Focus states are visible and properly offset. `aria-label` identifies the navigation landmark.

### Bad

```html
<header class="mega-header glass-effect">
  <div class="header-top-bar">
    <div class="social-links">
      <a href="#"><i class="fab fa-facebook"></i></a>
      <a href="#"><i class="fab fa-twitter"></i></a>
      <a href="#"><i class="fab fa-instagram"></i></a>
      <a href="#"><i class="fab fa-linkedin"></i></a>
    </div>
    <div class="header-contact">📞 1-800-DESIGN | ✉️ hello@studio.com</div>
  </div>
  <nav class="main-nav">
    <img src="logo-full-color.png" class="logo-large" />
    <div class="nav-links">
      <div class="dropdown">
        <a href="#">Services ▾</a>
        <div class="dropdown-mega-panel">...</div>
      </div>
      <a href="#">Portfolio</a>
      <a href="#">Team</a>
      <a href="#">Blog</a>
      <a href="#">Careers</a>
      <a href="#">Testimonials</a>
      <a href="#">FAQ</a>
      <a href="#">Contact</a>
    </div>
    <button class="btn-cta-header">Free Consultation</button>
  </nav>
</header>
```

**Why this fails:** Two-row header wastes vertical space. Social icons in the header are vanity — visitors don't come to your site to find your Twitter. Eight navigation items force the visitor to parse too many choices. Mega dropdown adds hidden complexity. Glass-effect is decoration that harms readability. CTA button in the nav creates visual competition with the content below.

---

## 3. Card Grid

### Good

```html
<section class="projects">
  <h2 class="section-heading">Selected Projects</h2>
  <div class="project-grid">
    <article class="project-card">
      <a href="/projects/coastal-house">
        <figure class="project-image">
          <img
            src="/images/coastal-house-640.webp"
            srcset="/images/coastal-house-640.webp 640w, /images/coastal-house-1024.webp 1024w, /images/coastal-house-1280.webp 1280w"
            sizes="(max-width: 768px) 100vw, (max-width: 1280px) 50vw, 640px"
            alt="Coastal House — whitewashed concrete exterior with floor-to-ceiling ocean views"
            width="640"
            height="427"
            loading="lazy"
          >
        </figure>
        <div class="project-info">
          <h3>Coastal House</h3>
          <p>Residential — Algarve, 2024</p>
        </div>
      </a>
    </article>
    <!-- more cards -->
  </div>
</section>
```

```css
.projects {
  padding: var(--space-32) var(--space-8);
}

.section-heading {
  font-size: var(--text-sm);
  font-weight: 400;
  letter-spacing: 0.08em;
  text-transform: uppercase;
  color: var(--color-text-muted);
  margin-bottom: var(--space-12);
}

.project-grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: var(--space-8);
  max-width: 1280px;
  margin: 0 auto;
}

@media (max-width: 768px) {
  .project-grid {
    grid-template-columns: 1fr;
  }
}

.project-card a {
  text-decoration: none;
  color: inherit;
  display: block;
}

.project-image {
  margin: 0;
  overflow: hidden;
  aspect-ratio: 3 / 2;
}

.project-image img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  transition: transform 600ms cubic-bezier(0.4, 0, 0.2, 1);
}

.project-card a:hover .project-image img {
  transform: scale(1.03);
}

.project-info {
  padding-top: var(--space-4);
}

.project-info h3 {
  font-size: var(--text-lg);
  font-weight: 500;
  color: var(--color-text-primary);
}

.project-info p {
  font-size: var(--text-sm);
  color: var(--color-text-secondary);
  margin-top: var(--space-1);
}
```

**Why this works:** Two-column grid is generous — each image gets space to breathe. Section heading is deliberately understated (small, uppercase, muted) so the work dominates. Cards are just image + title + metadata — nothing extra. Hover effect is a subtle zoom (1.03 scale, 600ms) that rewards interaction without distracting. Images use proper `srcset`, `sizes`, `loading`, `width`, `height`, and descriptive `alt` text.

### Bad

```html
<div class="projects-section">
  <div class="section-header">
    <h2>Our <span class="highlight">Amazing</span> Projects</h2>
    <p>Check out some of our recent work that we're proud of</p>
    <div class="filter-tabs">
      <button class="active">All</button>
      <button>Residential</button>
      <button>Commercial</button>
      <button>Interior</button>
    </div>
  </div>
  <div class="project-grid four-cols">
    <div class="project-card shadow-hover">
      <div class="card-badge">Featured</div>
      <img src="project1.jpg" />
      <div class="card-overlay">
        <h3>Coastal House</h3>
        <p>A beautiful coastal home with stunning views</p>
        <div class="card-tags">
          <span class="tag">#residential</span>
          <span class="tag">#coastal</span>
          <span class="tag">#modern</span>
        </div>
        <button class="btn-view">View Project →</button>
      </div>
    </div>
  </div>
</div>
```

**Why this fails:** Self-congratulatory heading ("Amazing"). Filter tabs add UI complexity without clear benefit on most portfolio sites. Four columns makes each image too small to evaluate. "Featured" badge is noise — if it's on the page, you already selected it. Overlay pattern hides the project info until hover (invisible on mobile, inaccessible to screen readers). Hashtags are decoration. The explicit "View Project" button is redundant when the entire card should be clickable. Image has no `alt`, no `srcset`, no dimensions.

---

## 4. Typography Hierarchy

### Good

```html
<article class="article">
  <header class="article-header">
    <p class="article-meta">March 2024 — Case Study</p>
    <h1>Rethinking the hotel lobby as a neighborhood gathering place</h1>
    <p class="article-lede">When Hotel & Mur asked us to redesign their ground floor, we started by watching how the neighborhood already used the space.</p>
  </header>
  <div class="article-body">
    <p>The lobby had been renovated twice in the last decade, each time becoming more polished and less welcoming...</p>
    <h2>What the space wanted to be</h2>
    <p>We spent three weeks observing foot traffic patterns...</p>
  </div>
</article>
```

```css
.article {
  max-width: 680px;
  margin: 0 auto;
  padding: var(--space-32) var(--space-6);
}

.article-meta {
  font-size: var(--text-sm);
  color: var(--color-text-muted);
  margin-bottom: var(--space-4);
}

.article-header h1 {
  font-family: var(--font-display);
  font-size: clamp(2rem, 4vw, 3rem);
  font-weight: 500;
  line-height: 1.15;
  letter-spacing: -0.02em;
  color: var(--color-text-primary);
  margin-bottom: var(--space-6);
}

.article-lede {
  font-size: var(--text-xl);
  line-height: 1.4;
  color: var(--color-text-secondary);
  margin-bottom: var(--space-16);
}

.article-body p {
  font-size: var(--text-base);
  line-height: 1.6;
  color: var(--color-text-primary);
  margin-bottom: var(--space-6);
}

.article-body h2 {
  font-size: var(--text-2xl);
  font-weight: 500;
  line-height: 1.3;
  letter-spacing: -0.01em;
  margin-top: var(--space-16);
  margin-bottom: var(--space-6);
}
```

**Why this works:** Four clear typographic levels — meta (small/muted), headline (large/display), lede (medium/secondary), body (standard/primary). Each level is distinguished by size, weight, color, AND line-height — not just one property. The 680px max-width keeps line length comfortable. Generous `margin-top` on h2 creates breathing room between sections. `clamp()` on the headline provides fluid scaling without breakpoint jumps.

### Bad

```html
<div class="blog-post">
  <h1 style="font-size: 48px; font-weight: 800; text-align: center; text-transform: uppercase;">
    RETHINKING THE HOTEL LOBBY
  </h1>
  <div class="divider"><hr></div>
  <p class="intro" style="font-size: 18px; font-style: italic; text-align: center; max-width: 800px; margin: 0 auto;">
    When Hotel &amp; Mur asked us to redesign their ground floor, we started by watching how the neighborhood already used the space.
  </p>
  <div class="content" style="font-size: 16px; max-width: 900px; margin: 0 auto;">
    <p>The lobby had been renovated twice...</p>
    <h2 style="font-size: 32px; font-weight: 800; border-bottom: 3px solid #333;">What the space wanted to be</h2>
  </div>
</div>
```

**Why this fails:** Inline styles make the system unmaintainable and override any design tokens. All-caps headline with weight 800 is aggressive. Centered headline text is harder to read at long lengths. The decorative `<hr>` divider adds noise. Italic lede is a cliché. The 900px max-width allows lines that are too long. The h2 border-bottom is a decorative crutch that substitutes for proper spacing and hierarchy. Hard-coded pixel values instead of design tokens.

---

## 5. Footer

### Good

```html
<footer class="site-footer">
  <div class="footer-inner">
    <div class="footer-primary">
      <p class="footer-name">Studio Name</p>
      <p class="footer-location">Berlin, Germany</p>
    </div>
    <nav class="footer-nav" aria-label="Footer navigation">
      <ul role="list">
        <li><a href="/projects">Projects</a></li>
        <li><a href="/about">About</a></li>
        <li><a href="/contact">Contact</a></li>
        <li><a href="/imprint">Imprint</a></li>
      </ul>
    </nav>
    <div class="footer-secondary">
      <p>&copy; 2024 Studio Name</p>
    </div>
  </div>
</footer>
```

```css
.site-footer {
  border-top: 1px solid var(--color-border-subtle);
  padding: var(--space-16) var(--space-8);
  margin-top: var(--space-32);
}

.footer-inner {
  max-width: 1280px;
  margin: 0 auto;
  display: flex;
  justify-content: space-between;
  align-items: flex-start;
  flex-wrap: wrap;
  gap: var(--space-8);
}

.footer-name {
  font-weight: 500;
  color: var(--color-text-primary);
}

.footer-location {
  font-size: var(--text-sm);
  color: var(--color-text-muted);
  margin-top: var(--space-1);
}

.footer-nav ul {
  list-style: none;
  padding: 0;
  display: flex;
  gap: var(--space-6);
}

.footer-nav a {
  font-size: var(--text-sm);
  color: var(--color-text-secondary);
  text-decoration: none;
}

.footer-nav a:hover {
  color: var(--color-text-primary);
}

.footer-secondary {
  font-size: var(--text-sm);
  color: var(--color-text-muted);
}
```

**Why this works:** Three elements: identity, navigation, copyright. A single subtle border separates the footer from content. The layout is horizontal on desktop, wraps naturally on mobile. No newsletter signup, no social icons, no sitemap — just the essentials.

### Bad

```html
<footer class="mega-footer dark-bg">
  <div class="footer-cta">
    <h2>Ready to start your project?</h2>
    <p>Let's create something amazing together!</p>
    <button class="btn-cta-large">Get In Touch</button>
  </div>
  <div class="footer-columns">
    <div class="footer-col">
      <h4>Services</h4>
      <ul><li>Web Design</li><li>Development</li><li>Branding</li><li>SEO</li><li>Consulting</li></ul>
    </div>
    <div class="footer-col">
      <h4>Company</h4>
      <ul><li>About</li><li>Team</li><li>Careers</li><li>Blog</li><li>Press</li></ul>
    </div>
    <div class="footer-col">
      <h4>Resources</h4>
      <ul><li>FAQ</li><li>Documentation</li><li>Privacy Policy</li><li>Terms</li><li>Sitemap</li></ul>
    </div>
    <div class="footer-col">
      <h4>Connect</h4>
      <div class="social-grid"><!-- 8 social icons --></div>
      <div class="newsletter">
        <input type="email" placeholder="Your email">
        <button>Subscribe</button>
      </div>
    </div>
  </div>
  <div class="footer-bottom">
    <p>© 2024 Studio. All rights reserved. Made with ❤️</p>
    <div class="partner-logos"><!-- 6 certification badges --></div>
  </div>
</footer>
```

**Why this fails:** The footer CTA is a sales pitch where visitors expect closure. Four columns of links replicate a sitemap nobody asked for. Newsletter signup in the footer has negligible conversion rates and adds form complexity. Eight social icons are vanity. "Made with love" is a cliché. Certification badges are for the studio's ego, not the visitor's needs. The dark background creates an unnecessary visual break.

---

## 6. Form

### Good

```html
<form class="contact-form" action="/contact" method="post">
  <div class="form-group">
    <label for="name">Name</label>
    <input type="text" id="name" name="name" required autocomplete="name">
  </div>
  <div class="form-group">
    <label for="email">Email</label>
    <input type="email" id="email" name="email" required autocomplete="email">
  </div>
  <div class="form-group">
    <label for="message">How can we help?</label>
    <textarea id="message" name="message" rows="5" required></textarea>
  </div>
  <button type="submit" class="form-submit">Send message</button>
</form>
```

```css
.contact-form {
  max-width: 540px;
}

.form-group {
  margin-bottom: var(--space-6);
}

.form-group label {
  display: block;
  font-size: var(--text-sm);
  font-weight: 500;
  color: var(--color-text-primary);
  margin-bottom: var(--space-2);
}

.form-group input,
.form-group textarea {
  width: 100%;
  padding: var(--space-3) var(--space-4);
  font-size: var(--text-base);
  font-family: inherit;
  color: var(--color-text-primary);
  background: var(--color-bg);
  border: 1px solid var(--color-border);
  border-radius: 4px;
  transition: border-color 150ms ease;
}

.form-group input:focus,
.form-group textarea:focus {
  outline: none;
  border-color: var(--color-accent);
  box-shadow: 0 0 0 3px var(--color-accent-muted);
}

.form-submit {
  font-size: var(--text-base);
  font-weight: 500;
  color: var(--color-bg);
  background: var(--color-text-primary);
  border: none;
  padding: var(--space-3) var(--space-8);
  border-radius: 4px;
  cursor: pointer;
  transition: opacity 150ms ease;
}

.form-submit:hover {
  opacity: 0.85;
}

.form-submit:focus-visible {
  outline: 2px solid var(--color-accent);
  outline-offset: 2px;
}
```

**Why this works:** Three fields — the minimum needed. Labels are visible (not placeholder-only). Inputs use `autocomplete` for speed. Focus states are clear (border color change + focus ring). The submit button is visually distinct but not aggressive. Form width is constrained for comfortable reading. All native form elements — no custom components needed.

### Bad

```html
<div class="contact-section">
  <h2>Drop us a line! 👋</h2>
  <p>Fill out the form below and our team will get back to you within 24-48 hours.</p>
  <form>
    <div class="form-row two-col">
      <div class="field">
        <input type="text" placeholder="First Name *">
      </div>
      <div class="field">
        <input type="text" placeholder="Last Name *">
      </div>
    </div>
    <div class="field">
      <input type="email" placeholder="Email Address *">
    </div>
    <div class="field">
      <input type="tel" placeholder="Phone Number">
    </div>
    <div class="field">
      <select><option>Select a service...</option><option>Web Design</option></select>
    </div>
    <div class="field">
      <input type="text" placeholder="Budget Range">
    </div>
    <div class="field">
      <textarea placeholder="Tell us about your project..."></textarea>
    </div>
    <div class="field">
      <label><input type="checkbox"> I agree to the privacy policy</label>
    </div>
    <button class="btn-submit-large">SEND MESSAGE →</button>
  </form>
</div>
```

**Why this fails:** Seven fields plus a checkbox — every additional field reduces completion rate. Placeholder-only labels disappear when typing, making the form harder to use. No `<label>` elements means screen readers can't associate labels with inputs. Split first/last name is unnecessary for most contact forms. Phone, service dropdown, and budget fields are premature — gather those in the conversation. The privacy checkbox adds legal friction without clear benefit in this context. All-caps button text is aggressive.
