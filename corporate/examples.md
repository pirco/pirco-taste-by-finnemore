# Corporate / Institutional Examples

Positive and negative calibration pairs for corporate/institutional contexts. These demonstrate how the corporate taste package applies in practice.

---

## 1. Department Landing Page

### Good

```html
<main id="main-content">
  <nav aria-label="Breadcrumb" class="breadcrumb">
    <ol>
      <li><a href="/">Home</a></li>
      <li><a href="/academics">Academics</a></li>
      <li aria-current="page">Department of Computer Science</li>
    </ol>
  </nav>

  <div class="page-layout">
    <div class="page-content">
      <h1>Department of Computer Science</h1>
      <p class="page-lede">Undergraduate and graduate programs in computer science, with research strengths in artificial intelligence, systems, and human-computer interaction.</p>

      <section class="section-links">
        <h2>Programs</h2>
        <ul class="link-list">
          <li><a href="/academics/cs/bs">B.S. in Computer Science</a></li>
          <li><a href="/academics/cs/ms">M.S. in Computer Science</a></li>
          <li><a href="/academics/cs/phd">Ph.D. in Computer Science</a></li>
        </ul>
      </section>

      <section class="section-links">
        <h2>Resources</h2>
        <ul class="link-list">
          <li><a href="/academics/cs/courses">Course catalog</a></li>
          <li><a href="/academics/cs/research">Research areas</a></li>
          <li><a href="/academics/cs/faculty">Faculty directory</a></li>
          <li><a href="/academics/cs/advising">Academic advising</a></li>
        </ul>
      </section>

      <section>
        <h2>Recent News</h2>
        <ul class="news-list">
          <li>
            <time datetime="2024-11-15">Nov 15, 2024</time>
            <a href="/news/cs-grant-2024">Department receives $4.2M NSF grant for AI safety research</a>
          </li>
          <li>
            <time datetime="2024-10-28">Oct 28, 2024</time>
            <a href="/news/cs-ranking">CS program ranked #12 nationally by U.S. News</a>
          </li>
        </ul>
      </section>
    </div>

    <aside class="page-sidebar" aria-label="Department contact information">
      <div class="contact-block">
        <h2>Contact</h2>
        <address>
          <p>Engineering Building, Room 300</p>
          <p>123 University Ave</p>
          <p>Los Angeles, CA 90024</p>
          <p><a href="tel:+13105551234">(310) 555-1234</a></p>
          <p><a href="mailto:cs@university.edu">cs@university.edu</a></p>
        </address>
        <p class="office-hours">Mon–Fri, 9:00 AM – 5:00 PM</p>
      </div>

      <div class="sidebar-links">
        <h2>Quick Links</h2>
        <ul>
          <li><a href="/apply">Apply now</a></li>
          <li><a href="/academics/cs/scholarships">Scholarships</a></li>
          <li><a href="/academics/cs/handbook.pdf">Student Handbook (PDF, 1.2 MB)</a></li>
        </ul>
      </div>
    </aside>
  </div>
</main>
```

```css
.page-layout {
  display: grid;
  grid-template-columns: var(--content-width) var(--sidebar-width);
  gap: var(--space-12);
  max-width: var(--max-width);
  margin: 0 auto;
  padding: var(--space-8) var(--space-8) var(--space-24);
}

@media (max-width: 768px) {
  .page-layout {
    grid-template-columns: 1fr;
  }
}

.page-content h1 {
  font-size: clamp(1.75rem, 3vw, 2.5rem);
  font-weight: 600;
  line-height: 1.15;
  letter-spacing: -0.02em;
  color: var(--color-text-primary);
  margin-bottom: var(--space-4);
}

.page-lede {
  font-size: var(--text-lg);
  line-height: 1.5;
  color: var(--color-text-secondary);
  margin-bottom: var(--space-12);
  max-width: 680px;
}

.section-links {
  margin-bottom: var(--space-10);
}

.section-links h2 {
  font-size: var(--text-lg);
  font-weight: 600;
  color: var(--color-text-primary);
  margin-bottom: var(--space-4);
  padding-bottom: var(--space-2);
  border-bottom: 1px solid var(--color-border-subtle);
}

.link-list {
  list-style: none;
  padding: 0;
}

.link-list li {
  padding: var(--space-2) 0;
  border-bottom: 1px solid var(--color-border-subtle);
}

.link-list a {
  color: var(--color-accent);
  text-decoration: none;
  font-size: var(--text-base);
}

.link-list a:hover {
  text-decoration: underline;
  text-underline-offset: 3px;
}

.news-list {
  list-style: none;
  padding: 0;
}

.news-list li {
  padding: var(--space-3) 0;
  border-bottom: 1px solid var(--color-border-subtle);
}

.news-list time {
  display: block;
  font-size: var(--text-xs);
  color: var(--color-text-muted);
  margin-bottom: var(--space-1);
}

.contact-block {
  background: var(--color-bg-alt);
  padding: var(--space-6);
  border-radius: 4px;
  margin-bottom: var(--space-8);
}

.contact-block h2 {
  font-size: var(--text-sm);
  font-weight: 600;
  text-transform: uppercase;
  letter-spacing: 0.05em;
  color: var(--color-text-muted);
  margin-bottom: var(--space-4);
}

.contact-block address {
  font-style: normal;
  font-size: var(--text-sm);
  line-height: 1.6;
  color: var(--color-text-primary);
}

.office-hours {
  font-size: var(--text-xs);
  color: var(--color-text-secondary);
  margin-top: var(--space-3);
}
```

**Why this works:** The page answers "what is this?" (department name + one-sentence description) and "what can I do?" (structured link sections) immediately. Breadcrumbs orient the visitor within the site. The sidebar isolates contact information where visitors expect it. Links to PDFs include file type and size. News items are date-stamped and scannable. The layout is a reusable template — every department page follows this exact structure.

### Bad

```html
<section class="department-hero" style="background-image: url('cs-building-aerial.jpg');">
  <div class="hero-overlay">
    <h1>Department of Computer Science</h1>
    <p>Innovating Tomorrow's Technology Today</p>
    <a href="#explore" class="btn-hero">Explore Our Programs</a>
  </div>
</section>

<section class="about-section">
  <h2>About Our Department</h2>
  <p>The Department of Computer Science at the University has been at the forefront of technological innovation for over 50 years. Our world-class faculty conduct groundbreaking research across multiple disciplines, and our graduates go on to lead at top companies around the globe. We are committed to excellence in education, research, and service to our community...</p>
  <p>Founded in 1969, the department has grown from a small group of pioneering researchers to one of the most respected computer science programs in the nation. Our state-of-the-art facilities include...</p>
</section>

<section class="programs-carousel">
  <h2>Our Programs</h2>
  <div class="carousel">
    <div class="slide"><img src="bs-program.jpg"><h3>B.S. in CS</h3></div>
    <div class="slide"><img src="ms-program.jpg"><h3>M.S. in CS</h3></div>
    <div class="slide"><img src="phd-program.jpg"><h3>Ph.D. in CS</h3></div>
  </div>
  <div class="carousel-dots">...</div>
</section>
```

**Why this fails:** The hero image with aerial photo is atmospheric content that delays task completion. The tagline ("Innovating Tomorrow's Technology Today") is meaningless marketing language. The "About" section is a wall of self-congratulatory prose — no visitor came to read about 50 years of history on their first visit. Programs are hidden in a carousel, requiring interaction to see all three options. No breadcrumbs, no contact information visible, no structured links. A prospective student cannot find "how to apply" without scrolling past marketing content.

---

## 2. Research / Program Page

### Good

```html
<main id="main-content">
  <nav aria-label="Breadcrumb" class="breadcrumb">
    <ol>
      <li><a href="/">Home</a></li>
      <li><a href="/academics">Academics</a></li>
      <li><a href="/academics/cs">Computer Science</a></li>
      <li aria-current="page">M.S. in Computer Science</li>
    </ol>
  </nav>

  <div class="page-layout">
    <div class="page-content">
      <h1>M.S. in Computer Science</h1>
      <p class="page-lede">A two-year graduate program with thesis and non-thesis options, preparing students for careers in research, industry, and doctoral study.</p>

      <section id="key-facts" class="key-facts-inline">
        <h2 class="sr-only">Program at a Glance</h2>
        <dl class="facts-grid">
          <div class="fact">
            <dt>Duration</dt>
            <dd>2 years (full-time)</dd>
          </div>
          <div class="fact">
            <dt>Credits</dt>
            <dd>36 units</dd>
          </div>
          <div class="fact">
            <dt>Format</dt>
            <dd>On-campus</dd>
          </div>
          <div class="fact">
            <dt>Application deadline</dt>
            <dd>January 15, 2025</dd>
          </div>
        </dl>
      </section>

      <nav aria-label="Page sections" class="page-toc">
        <h2>On this page</h2>
        <ol>
          <li><a href="#requirements">Admission requirements</a></li>
          <li><a href="#curriculum">Curriculum</a></li>
          <li><a href="#specializations">Specializations</a></li>
          <li><a href="#funding">Funding and assistantships</a></li>
          <li><a href="#outcomes">Career outcomes</a></li>
        </ol>
      </nav>

      <section id="requirements">
        <h2>Admission requirements</h2>
        <ul>
          <li>Bachelor's degree in computer science or related field</li>
          <li>Minimum 3.0 GPA (on a 4.0 scale)</li>
          <li>GRE scores (optional for 2025 admissions cycle)</li>
          <li>Three letters of recommendation</li>
          <li>Statement of purpose</li>
        </ul>
        <p><a href="/apply/graduate">Apply to this program</a></p>
      </section>

      <!-- Additional sections follow the same pattern -->
    </div>

    <aside class="page-sidebar">
      <div class="sidebar-cta">
        <h2>Ready to apply?</h2>
        <p>Application deadline: January 15, 2025</p>
        <a href="/apply/graduate" class="btn-primary">Start your application</a>
      </div>
      <div class="sidebar-links">
        <h2>Related</h2>
        <ul>
          <li><a href="/academics/cs/faculty">Faculty directory</a></li>
          <li><a href="/academics/cs/research">Research areas</a></li>
          <li><a href="/academics/cs/ms/faq">Frequently asked questions</a></li>
          <li><a href="/academics/cs/ms/handbook.pdf">Graduate Handbook (PDF, 850 KB)</a></li>
        </ul>
      </div>
    </aside>
  </div>
</main>
```

**Why this works:** Key facts (duration, credits, format, deadline) are the first content after the heading — answering the most common questions immediately. The table of contents lets visitors jump to specific sections. Admission requirements are a scannable list, not buried in a paragraph. The sidebar carries the primary CTA (apply) and related links. Related documents indicate file type and size. Every section has a descriptive heading that works as a navigational anchor.

### Bad

```html
<div class="program-page">
  <div class="program-hero">
    <img src="campus-quad.jpg" alt="Students walking on campus quad">
    <div class="hero-content">
      <h1>Master of Science in Computer Science</h1>
      <p>Shape the future of technology with our world-renowned program</p>
    </div>
  </div>

  <div class="program-content">
    <p>Our Master of Science in Computer Science program offers students an unparalleled opportunity to study alongside leading researchers in a vibrant academic community. The program combines rigorous coursework with hands-on research experience, preparing graduates for successful careers in industry and academia. Students benefit from our state-of-the-art facilities, including our recently renovated computing center and collaborative research spaces.</p>

    <p>The program requires 36 units of graduate coursework, which can be completed in approximately two years of full-time study. Students may choose between a thesis option, which involves original research under faculty supervision, and a comprehensive exam option. Both tracks require completion of core courses in algorithms, systems, and theory, as well as elective courses in a chosen specialization area.</p>

    <h2>Why Choose Our Program?</h2>
    <div class="three-col-grid">
      <div class="feature-card">
        <div class="icon">🎓</div>
        <h3>World-Class Faculty</h3>
        <p>Learn from internationally recognized researchers.</p>
      </div>
      <div class="feature-card">
        <div class="icon">🔬</div>
        <h3>Cutting-Edge Research</h3>
        <p>Participate in groundbreaking projects.</p>
      </div>
      <div class="feature-card">
        <div class="icon">💼</div>
        <h3>Career Success</h3>
        <p>96% employment rate within 6 months.</p>
      </div>
    </div>
  </div>
</div>
```

**Why this fails:** The hero image and marketing tagline delay task completion. The critical information — credits, duration, deadline — is buried in the second paragraph of prose. The "Why Choose" section with emoji icons is promotional rather than informational. No breadcrumbs, no table of contents, no sidebar, no structured data. A prospective student cannot determine admission requirements without reading multiple paragraphs of marketing copy. No links to application, faculty, or related resources.

---

## 3. People / Directory Page

### Good

```html
<main id="main-content">
  <nav aria-label="Breadcrumb" class="breadcrumb">
    <ol>
      <li><a href="/">Home</a></li>
      <li><a href="/academics/cs">Computer Science</a></li>
      <li aria-current="page">Faculty</li>
    </ol>
  </nav>

  <h1>Faculty Directory</h1>

  <div class="directory-controls">
    <label for="dept-filter" class="filter-label">Filter by area:</label>
    <select id="dept-filter" class="filter-select">
      <option value="all">All areas</option>
      <option value="ai">Artificial Intelligence</option>
      <option value="systems">Systems</option>
      <option value="theory">Theory</option>
      <option value="hci">Human-Computer Interaction</option>
    </select>
  </div>

  <div class="directory-grid">
    <article class="person-card">
      <a href="/academics/cs/faculty/chen">
        <img
          src="/images/faculty/chen-240.webp"
          srcset="/images/faculty/chen-240.webp 240w, /images/faculty/chen-480.webp 480w"
          sizes="120px"
          alt=""
          width="120"
          height="120"
          loading="lazy"
          class="person-photo"
        >
        <div class="person-info">
          <h2 class="person-name">Dr. Sarah Chen</h2>
          <p class="person-title">Professor</p>
          <p class="person-area">Artificial Intelligence</p>
        </div>
      </a>
    </article>
    <!-- Additional person cards follow identical pattern -->
  </div>
</main>
```

```css
.directory-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
  gap: var(--space-6);
  max-width: var(--max-width);
  margin: 0 auto;
}

.person-card a {
  display: flex;
  align-items: center;
  gap: var(--space-4);
  padding: var(--space-4);
  text-decoration: none;
  color: inherit;
  border: 1px solid var(--color-border-subtle);
  border-radius: 4px;
  transition: border-color 150ms ease;
}

.person-card a:hover {
  border-color: var(--color-border);
}

.person-card a:focus-visible {
  outline: 2px solid var(--color-accent);
  outline-offset: 2px;
}

.person-photo {
  width: 120px;
  height: 120px;
  border-radius: 50%;
  object-fit: cover;
  flex-shrink: 0;
}

.person-name {
  font-size: var(--text-base);
  font-weight: 600;
  color: var(--color-text-primary);
}

.person-title {
  font-size: var(--text-sm);
  color: var(--color-text-secondary);
  margin-top: var(--space-1);
}

.person-area {
  font-size: var(--text-xs);
  color: var(--color-text-muted);
  margin-top: var(--space-1);
}
```

**Why this works:** Clean grid of people with name, title, and research area visible without interaction. Filter by area lets visitors narrow results. Photos are 1:1 (consistent), properly sized, and lazy-loaded. Each card links to a full profile page. The layout is compact — many people visible per viewport. Headshot `alt` is empty because the person's name is in the adjacent text (avoiding redundancy for screen readers). The grid auto-fills, adjusting column count to viewport width.

### Bad

```html
<section class="our-team">
  <h1>Meet Our Amazing Faculty</h1>
  <p class="team-intro">Our brilliant professors are leaders in their fields, passionate about teaching and dedicated to student success.</p>

  <div class="team-carousel">
    <div class="carousel-slide active">
      <img src="chen-hero.jpg" class="faculty-hero-image">
      <div class="faculty-bio">
        <h2>Dr. Sarah Chen</h2>
        <p class="faculty-title">Professor of Computer Science</p>
        <p>Dr. Chen received her Ph.D. from MIT in 2005 and joined the department in 2007. Her research focuses on machine learning and natural language processing. She has published over 150 papers and received the ACM Distinguished Scientist award in 2019. In her free time, she enjoys hiking and playing the piano...</p>
        <div class="social-links">
          <a href="#"><i class="fab fa-twitter"></i></a>
          <a href="#"><i class="fab fa-linkedin"></i></a>
          <a href="#"><i class="fab fa-google-scholar"></i></a>
        </div>
      </div>
    </div>
    <button class="carousel-prev">←</button>
    <button class="carousel-next">→</button>
  </div>
</section>
```

**Why this fails:** A carousel forces visitors to step through faculty one at a time — entirely impractical for a department with 30+ people. Lengthy biography text belongs on individual profile pages, not the directory listing. The "Amazing Faculty" heading is promotional. Social media icons are noise — visitors searching for a professor need office location and email, not their Twitter handle. No filter, no search, no way to scan the full list. The hero-sized image wastes space. A visitor looking for a specific professor has no efficient path to find them.

---

## 4. News / Events Listing

### Good

```html
<main id="main-content">
  <nav aria-label="Breadcrumb" class="breadcrumb">
    <ol>
      <li><a href="/">Home</a></li>
      <li aria-current="page">News</li>
    </ol>
  </nav>

  <h1>News</h1>

  <div class="listing-controls">
    <label for="category-filter" class="filter-label">Category:</label>
    <select id="category-filter" class="filter-select">
      <option value="all">All categories</option>
      <option value="research">Research</option>
      <option value="awards">Awards</option>
      <option value="events">Events</option>
      <option value="announcements">Announcements</option>
    </select>
  </div>

  <ol class="news-listing" role="list">
    <li class="news-item">
      <article>
        <time datetime="2024-11-15" class="news-date">November 15, 2024</time>
        <h2 class="news-title"><a href="/news/cs-grant-2024">Department receives $4.2M NSF grant for AI safety research</a></h2>
        <p class="news-excerpt">A team led by Dr. Sarah Chen has been awarded a four-year grant to study alignment and safety mechanisms in large language models.</p>
        <span class="news-category">Research</span>
      </article>
    </li>
    <li class="news-item">
      <article>
        <time datetime="2024-10-28" class="news-date">October 28, 2024</time>
        <h2 class="news-title"><a href="/news/cs-ranking">CS program ranked #12 nationally by U.S. News</a></h2>
        <p class="news-excerpt">The graduate program rose three spots in the latest U.S. News & World Report rankings, reflecting growth in research output and student outcomes.</p>
        <span class="news-category">Awards</span>
      </article>
    </li>
    <!-- Additional items follow identical structure -->
  </ol>

  <nav aria-label="Pagination" class="pagination">
    <span class="pagination-current" aria-current="page">Page 1</span>
    <a href="/news?page=2">Page 2</a>
    <a href="/news?page=3">Page 3</a>
    <a href="/news?page=2" class="pagination-next">Next page</a>
  </nav>
</main>
```

```css
.news-listing {
  list-style: none;
  padding: 0;
  max-width: var(--max-width);
  margin: 0 auto;
}

.news-item {
  padding: var(--space-6) 0;
  border-bottom: 1px solid var(--color-border-subtle);
}

.news-date {
  display: block;
  font-size: var(--text-xs);
  color: var(--color-text-muted);
  margin-bottom: var(--space-2);
}

.news-title {
  font-size: var(--text-lg);
  font-weight: 600;
  line-height: 1.3;
  margin-bottom: var(--space-2);
}

.news-title a {
  color: var(--color-text-primary);
  text-decoration: none;
}

.news-title a:hover {
  text-decoration: underline;
  text-underline-offset: 3px;
}

.news-excerpt {
  font-size: var(--text-sm);
  color: var(--color-text-secondary);
  line-height: 1.5;
  margin-bottom: var(--space-2);
  max-width: 680px;
}

.news-category {
  display: inline-block;
  font-size: var(--text-xs);
  color: var(--color-accent);
  background: var(--color-accent-muted);
  padding: var(--space-1) var(--space-3);
  border-radius: 3px;
}

.pagination {
  display: flex;
  gap: var(--space-3);
  padding: var(--space-8) 0;
  font-size: var(--text-sm);
}

.pagination a {
  color: var(--color-accent);
  text-decoration: none;
  padding: var(--space-2) var(--space-3);
}

.pagination-current {
  font-weight: 600;
  color: var(--color-text-primary);
  padding: var(--space-2) var(--space-3);
}
```

**Why this works:** Chronological list with date, title, excerpt, and category tag — the four pieces of information visitors need to decide whether to click. Dates are formatted in both human-readable text and machine-readable `datetime` attributes. Category tags support scanning by topic. The list layout is compact — many items per viewport. Pagination is explicit with clear current-page indication. No images in the listing — they add visual weight without informational value for news items.

### Bad

```html
<section class="news-section">
  <h1>Latest News & Updates</h1>
  <div class="news-grid four-col">
    <div class="news-card">
      <img src="ai-research.jpg" class="card-image">
      <div class="card-content">
        <span class="card-tag">Research</span>
        <h3>Department receives $4.2M NSF grant for AI safety research</h3>
        <a href="#" class="read-more">Read More →</a>
      </div>
    </div>
    <div class="news-card">
      <img src="campus-ranking.jpg" class="card-image">
      <div class="card-content">
        <span class="card-tag">Awards</span>
        <h3>CS program ranked #12 nationally</h3>
        <a href="#" class="read-more">Read More →</a>
      </div>
    </div>
    <!-- More cards with large stock images -->
  </div>
  <div class="load-more-container">
    <button class="btn-load-more">Load More Stories</button>
  </div>
</section>
```

**Why this fails:** Four-column card grid with large images makes each item small and hard to scan. Dates are completely absent — the visitor cannot tell if an article is from yesterday or two years ago. No excerpts, so the headline alone must communicate the full story. "Read More" is generic link text that is meaningless to screen readers navigating by links. Infinite scroll (via "Load More") prevents visitors from reaching the footer and makes it impossible to bookmark a position in the list. The stock images (generic "AI research" and "campus" photos) add page weight without informational value. No breadcrumbs, no category filter, no pagination.
