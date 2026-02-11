# Hospitality Examples

Positive and negative calibration pairs for hospitality-specific patterns. These extend the foundation examples with hotel, resort, and venue contexts.

---

## 1. Hotel Hero Section

### Good

```html
<section class="hero" aria-label="Welcome to The Linden">
  <div class="hero-image">
    <picture>
      <source
        srcset="/images/hero-lobby-evening-640.webp 640w, /images/hero-lobby-evening-1024.webp 1024w, /images/hero-lobby-evening-1920.webp 1920w"
        sizes="100vw"
        type="image/webp"
      >
      <img
        src="/images/hero-lobby-evening-1920.jpg"
        alt="The Linden hotel lobby at dusk — warm lamplight reflecting off polished stone floors, floor-to-ceiling windows framing a garden courtyard"
        width="1920"
        height="823"
        loading="eager"
        fetchpriority="high"
      >
    </picture>
  </div>
  <div class="hero-content">
    <h1>The Linden</h1>
    <p>A quiet address on the lake</p>
  </div>
</section>
```

```css
.hero {
  position: relative;
  height: 100vh;
  min-height: 600px;
  overflow: hidden;
}

.hero-image {
  position: absolute;
  inset: 0;
}

.hero-image img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  animation: ken-burns 20s ease-in-out forwards;
}

@keyframes ken-burns {
  from { transform: scale(1); }
  to { transform: scale(1.05); }
}

@media (prefers-reduced-motion: reduce) {
  .hero-image img {
    animation: none;
  }
}

.hero-content {
  position: absolute;
  bottom: var(--space-16);
  left: var(--space-8);
  z-index: 2;
}

.hero::after {
  content: '';
  position: absolute;
  bottom: 0;
  left: 0;
  right: 0;
  height: 50%;
  background: linear-gradient(to top, rgba(26,21,18,0.6), transparent);
  z-index: 1;
}

.hero-content {
  position: relative;
  z-index: 2;
}

.hero h1 {
  font-family: var(--font-display);
  font-size: clamp(2.5rem, 5vw, 4.5rem);
  font-weight: 400;
  line-height: 1.1;
  letter-spacing: -0.02em;
  color: #f5f0eb;
  margin-bottom: var(--space-3);
}

.hero p {
  font-family: var(--font-display);
  font-size: var(--text-lg);
  font-style: italic;
  font-weight: 400;
  color: rgba(245, 240, 235, 0.85);
}
```

**Why this works:** The image fills the viewport — the guest is immersed in the space before reading a word. The property name is set in the serif display font at a confident but not shouting scale. The tagline is a single quiet phrase, set in italic for editorial warmth. The gradient overlay is bottom-only, letting the sky and upper portions of the image remain untouched. Ken Burns animation gives the image a living quality — so subtle the guest may not consciously notice it. No booking button competes with the first impression. The image `alt` text describes the scene atmospherically, not generically.

### Bad

```html
<section class="hero-slider">
  <div class="slide active">
    <img src="hero1.jpg" />
    <div class="slide-overlay">
      <h1>WELCOME TO THE LINDEN HOTEL & RESORT</h1>
      <p>Experience luxury like never before at our award-winning property</p>
      <div class="hero-cta-group">
        <button class="btn-book-now pulse">BOOK NOW — SAVE 20%</button>
        <button class="btn-secondary">View Rooms</button>
        <button class="btn-tertiary">Watch Video ▶</button>
      </div>
    </div>
  </div>
  <div class="slide">...</div>
  <div class="slide">...</div>
  <div class="slider-dots">
    <span class="dot active"></span>
    <span class="dot"></span>
    <span class="dot"></span>
  </div>
  <button class="slider-prev">‹</button>
  <button class="slider-next">›</button>
  <div class="booking-widget-hero">
    <input type="date" placeholder="Check In">
    <input type="date" placeholder="Check Out">
    <select><option>2 Guests</option></select>
    <button class="btn-search">SEARCH RATES</button>
  </div>
</section>
```

**Why this fails:** The carousel with three slides, dots, and arrows is the most common hospitality web cliche — it introduces complexity, slows load time, and research consistently shows that users rarely engage past the first slide. The full-caps headline with ampersand-heavy name feels like a conference banner, not an arrival experience. "Experience luxury like never before" is meaningless — every luxury hotel says this. Three competing CTAs create decision paralysis. The pulsing "BOOK NOW" with a discount percentage turns the hero into a billboard. The booking widget overlaid on the hero image adds a transactional layer to what should be an emotional first impression. The image has no `alt`, no `srcset`, and no dimensions.

---

## 2. Room / Suite Presentation

### Good

```html
<article class="room-narrative">
  <section class="room-hero">
    <picture>
      <source
        srcset="/images/garden-suite-morning-640.webp 640w, /images/garden-suite-morning-1280.webp 1280w, /images/garden-suite-morning-1920.webp 1920w"
        sizes="100vw"
        type="image/webp"
      >
      <img
        src="/images/garden-suite-morning-1920.jpg"
        alt="Garden Suite — morning light filtering through linen curtains, a reading chair angled toward the private terrace"
        width="1920" height="823" loading="eager" fetchpriority="high"
      >
    </picture>
  </section>

  <section class="room-intro">
    <header class="room-header">
      <h1>Garden Suite</h1>
      <p class="room-atmosphere">Ground-floor quiet, with a private terrace that opens to the olive grove. Morning coffee here is the best hour of the day.</p>
    </header>
  </section>

  <section class="room-editorial">
    <div class="editorial-grid">
      <figure class="editorial-image editorial-large">
        <img src="/images/garden-suite-terrace.webp" alt="Private terrace with a small table set for breakfast, olive trees beyond" width="960" height="640" loading="lazy">
      </figure>
      <figure class="editorial-image editorial-portrait">
        <img src="/images/garden-suite-detail.webp" alt="Linen bedding detail with hand-thrown ceramic vase on the nightstand" width="480" height="720" loading="lazy">
      </figure>
      <figure class="editorial-image editorial-landscape">
        <img src="/images/garden-suite-bath.webp" alt="Freestanding stone bath with brass fixtures, natural light from a high window" width="640" height="427" loading="lazy">
      </figure>
    </div>
  </section>

  <section class="room-details">
    <div class="details-prose">
      <p>The suite opens directly onto the garden through sliding oak-framed doors. Inside, the materials are simple — lime-washed walls, reclaimed oak floors, hand-woven textiles from the region. The bath, carved from a single block of local stone, is the room's quiet centerpiece.</p>
    </div>
    <aside class="room-specs">
      <dl>
        <dt>Size</dt><dd>62 m²</dd>
        <dt>Bed</dt><dd>King</dd>
        <dt>Occupancy</dt><dd>2 guests</dd>
        <dt>View</dt><dd>Garden & olive grove</dd>
      </dl>
      <p class="room-rate">From €420 per night</p>
    </aside>
  </section>

  <footer class="room-action">
    <a href="/reserve?room=garden-suite" class="room-reserve-link">Reserve this suite</a>
  </footer>
</article>
```

```css
.room-narrative {
  --room-gap: var(--space-48);
}

.room-hero img {
  width: 100%;
  height: 85vh;
  min-height: 500px;
  object-fit: cover;
}

.room-intro {
  max-width: 680px;
  margin: 0 auto;
  padding: var(--space-48) var(--space-6);
  text-align: center;
}

.room-header h1 {
  font-family: var(--font-display);
  font-size: clamp(2rem, 4vw, 3.75rem);
  font-weight: 400;
  letter-spacing: -0.02em;
  color: var(--color-text-primary);
  margin-bottom: var(--space-6);
}

.room-atmosphere {
  font-size: var(--text-lg);
  line-height: 1.6;
  color: var(--color-text-secondary);
  font-style: italic;
  font-family: var(--font-display);
}

.editorial-grid {
  display: grid;
  grid-template-columns: 1.5fr 1fr;
  grid-template-rows: auto auto;
  gap: var(--space-6);
  padding: 0 var(--space-8);
  max-width: 1440px;
  margin: 0 auto;
}

.editorial-large {
  grid-row: 1 / 3;
}

.editorial-image {
  margin: 0;
  overflow: hidden;
}

.editorial-image img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.room-specs {
  font-size: var(--text-sm);
  color: var(--color-text-muted);
}

.room-specs dl {
  display: grid;
  grid-template-columns: auto 1fr;
  gap: var(--space-2) var(--space-6);
}

.room-specs dt {
  font-weight: 500;
  color: var(--color-text-secondary);
}

.room-rate {
  margin-top: var(--space-6);
  font-size: var(--text-sm);
  color: var(--color-text-secondary);
}

.room-reserve-link {
  font-size: var(--text-base);
  color: var(--color-accent);
  text-decoration: underline;
  text-underline-offset: 4px;
  text-decoration-color: var(--color-accent-muted);
  transition: text-decoration-color 400ms ease;
}

.room-reserve-link:hover {
  text-decoration-color: var(--color-accent);
}
```

**Why this works:** The room is presented as a story, not a spec sheet. It opens with an atmospheric full-bleed image — morning light, not a real estate wide-angle. The room name in serif display type at centered layout creates an editorial pause. The descriptive text is written in first person with sensory detail ("Morning coffee here is the best hour of the day") — the guest is already imagining themselves there. The editorial image grid mixes aspect ratios (landscape, portrait, landscape) creating visual rhythm. Specifications are tucked into a quiet aside with muted styling — they are findable but do not lead. The rate is understated. The reservation link uses the accent color with a soft underline — present, patient, refined.

### Bad

```html
<div class="room-card-detail">
  <div class="room-image-carousel">
    <img src="room1.jpg" class="active" />
    <img src="room2.jpg" />
    <img src="room3.jpg" />
    <img src="room4.jpg" />
    <div class="carousel-count">1/4</div>
    <button class="prev">‹</button>
    <button class="next">›</button>
  </div>
  <div class="room-info-panel">
    <div class="room-badge">Best Seller</div>
    <h2>GARDEN SUITE</h2>
    <div class="room-features">
      <div class="feature"><i class="icon-bed"></i> King Bed</div>
      <div class="feature"><i class="icon-size"></i> 62 m²</div>
      <div class="feature"><i class="icon-guests"></i> 2 Guests</div>
      <div class="feature"><i class="icon-wifi"></i> Free WiFi</div>
      <div class="feature"><i class="icon-ac"></i> Air Conditioning</div>
      <div class="feature"><i class="icon-tv"></i> Smart TV</div>
      <div class="feature"><i class="icon-minibar"></i> Minibar</div>
      <div class="feature"><i class="icon-safe"></i> In-Room Safe</div>
    </div>
    <div class="room-price-box">
      <span class="strikethrough">€520</span>
      <span class="sale-price">€420/night</span>
      <span class="savings-badge">Save 19%!</span>
    </div>
    <button class="btn-book-room">BOOK THIS ROOM</button>
    <p class="urgency-text">Only 2 rooms left at this price!</p>
  </div>
</div>
```

**Why this fails:** This is a product listing, not hospitality. The image carousel with a counter ("1/4") treats photography like inventory documentation. "Best Seller" badge belongs on Amazon. All-caps room name strips the name of its character. The icon grid (WiFi, AC, Smart TV, minibar, safe) lists commodities that every hotel provides — they are undifferentiating and dehumanizing. The strikethrough pricing with savings percentage and urgency text ("Only 2 rooms left!") are retail pressure tactics that undermine the trust a luxury property needs to build. The large "BOOK THIS ROOM" button turns the reservation into a transaction rather than an invitation.

---

## 3. Restaurant / Amenity Section

### Good

```html
<section class="dining-section">
  <div class="dining-layout">
    <figure class="dining-image">
      <img
        src="/images/terrazza-evening.webp"
        srcset="/images/terrazza-evening-640.webp 640w, /images/terrazza-evening-1280.webp 1280w"
        sizes="(max-width: 1024px) 100vw, 60vw"
        alt="Terrazza dining room at evening service — candlelit tables, vineyard visible through arched windows"
        width="1280" height="854" loading="lazy"
      >
    </figure>
    <div class="dining-content">
      <h2>Terrazza</h2>
      <p>Seasonal cooking drawn from the surrounding farms and the sea beyond them. The menu changes weekly; the view does not.</p>
      <div class="dining-details">
        <p class="dining-hours">Dinner, Wednesday through Sunday</p>
        <a href="/dining/terrazza" class="dining-link">View the menu</a>
      </div>
    </div>
  </div>
</section>
```

```css
.dining-layout {
  display: grid;
  grid-template-columns: 3fr 2fr;
  gap: var(--space-16);
  align-items: center;
  max-width: 1440px;
  margin: 0 auto;
  padding: var(--space-48) var(--space-8);
}

.dining-image {
  margin: 0;
  overflow: hidden;
}

.dining-image img {
  width: 100%;
  height: auto;
  aspect-ratio: 3 / 2;
  object-fit: cover;
}

.dining-content h2 {
  font-family: var(--font-display);
  font-size: clamp(2rem, 3.5vw, 3rem);
  font-weight: 400;
  letter-spacing: -0.01em;
  color: var(--color-text-primary);
  margin-bottom: var(--space-6);
}

.dining-content p {
  font-size: var(--text-lg);
  line-height: 1.6;
  color: var(--color-text-secondary);
  max-width: 480px;
  margin-bottom: var(--space-8);
}

.dining-hours {
  font-size: var(--text-sm);
  color: var(--color-text-muted);
  margin-bottom: var(--space-4);
}

.dining-link {
  font-size: var(--text-base);
  color: var(--color-accent);
  text-decoration: underline;
  text-underline-offset: 4px;
}
```

**Why this works:** One photograph does the atmospheric work. The restaurant name in serif display type is the only heading. The description is two sentences — one about the food philosophy, one poetic detail about the setting. Hours are quiet metadata. The menu link is a simple text link. The asymmetric grid (3:2 ratio) gives the image generous space while keeping text in a comfortable column. There is nothing here that does not need to be here.

### Bad

```html
<section class="amenities-grid">
  <h2>Hotel Amenities & Services</h2>
  <div class="amenity-cards">
    <div class="amenity-card">
      <div class="amenity-icon">🍽️</div>
      <h3>Fine Dining</h3>
      <p>Award-winning restaurant serving international cuisine</p>
    </div>
    <div class="amenity-card">
      <div class="amenity-icon">🏊</div>
      <h3>Infinity Pool</h3>
      <p>Heated outdoor pool with panoramic views</p>
    </div>
    <div class="amenity-card">
      <div class="amenity-icon">💆</div>
      <h3>Luxury Spa</h3>
      <p>Full-service spa with sauna and treatment rooms</p>
    </div>
    <div class="amenity-card">
      <div class="amenity-icon">🏋️</div>
      <h3>Fitness Center</h3>
      <p>State-of-the-art equipment, open 24/7</p>
    </div>
    <div class="amenity-card">
      <div class="amenity-icon">🚗</div>
      <h3>Valet Parking</h3>
      <p>Complimentary valet service for all guests</p>
    </div>
    <div class="amenity-card">
      <div class="amenity-icon">📶</div>
      <h3>Free WiFi</h3>
      <p>High-speed internet throughout the property</p>
    </div>
  </div>
</section>
```

**Why this fails:** The icon-and-card grid is the single most overused pattern in hotel websites. It reduces unique experiences to commodity checklists. Emoji icons look amateurish; custom icons are marginally better but still communicate "feature list" rather than "experience." Each card's single-sentence description is generic enough to apply to any hotel in the category. "Award-winning," "state-of-the-art," and "luxury" are empty words that every competitor also uses. No photograph means no atmosphere — the guest cannot feel any of these spaces. WiFi and parking are operational details, not experiences worth featuring alongside dining and spa.

---

## 4. Gallery Section

### Good

```html
<section class="gallery-editorial" aria-label="Gallery">
  <header class="gallery-header">
    <h2>The Property</h2>
  </header>
  <div class="gallery-grid">
    <figure class="gallery-item gallery-wide">
      <img src="/images/gallery-arrival.webp" alt="Stone-paved drive approaching the main house at golden hour" width="1280" height="548" loading="lazy">
    </figure>
    <figure class="gallery-item gallery-portrait">
      <img src="/images/gallery-staircase.webp" alt="Curved staircase with wrought-iron railing, skylight above" width="480" height="720" loading="lazy">
    </figure>
    <figure class="gallery-item gallery-standard">
      <img src="/images/gallery-courtyard.webp" alt="Interior courtyard with a single olive tree and a stone fountain" width="640" height="427" loading="lazy">
    </figure>
    <figure class="gallery-item gallery-standard">
      <img src="/images/gallery-library.webp" alt="Library corner with leather armchairs and afternoon light through tall windows" width="640" height="427" loading="lazy">
    </figure>
    <figure class="gallery-item gallery-wide">
      <img src="/images/gallery-pool-evening.webp" alt="Infinity pool at dusk, warm light from the terrace bar reflected in still water" width="1280" height="548" loading="lazy">
    </figure>
  </div>
</section>
```

```css
.gallery-editorial {
  padding: var(--space-48) 0;
}

.gallery-header {
  text-align: center;
  margin-bottom: var(--space-16);
}

.gallery-header h2 {
  font-family: var(--font-display);
  font-size: clamp(1.75rem, 3vw, 2.5rem);
  font-weight: 400;
  color: var(--color-text-primary);
}

.gallery-grid {
  display: grid;
  grid-template-columns: repeat(12, 1fr);
  gap: var(--space-4);
  max-width: 1440px;
  margin: 0 auto;
  padding: 0 var(--space-8);
}

.gallery-item {
  margin: 0;
  overflow: hidden;
}

.gallery-item img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  transition: transform 800ms cubic-bezier(0.25, 0.1, 0.25, 1);
}

.gallery-item:hover img {
  transform: scale(1.03);
}

/* Wide images span full width */
.gallery-wide {
  grid-column: span 12;
  aspect-ratio: 21 / 9;
}

/* Portrait takes 4 columns */
.gallery-portrait {
  grid-column: span 4;
  aspect-ratio: 2 / 3;
}

/* Standard landscape takes 8 or 6 columns */
.gallery-standard {
  grid-column: span 4;
  aspect-ratio: 3 / 2;
}

/* Stagger the middle row */
.gallery-portrait + .gallery-standard {
  grid-column: 5 / span 8;
}

@media (max-width: 768px) {
  .gallery-grid {
    grid-template-columns: 1fr;
    gap: var(--space-3);
  }

  .gallery-wide,
  .gallery-portrait,
  .gallery-standard {
    grid-column: span 1;
    aspect-ratio: 3 / 2;
  }
}
```

**Why this works:** The gallery tells a spatial story — arrival, interior details, outdoor spaces — in a deliberate sequence, not a random dump. Image sizes vary: wide cinematic shots span the full width, while portraits and landscapes are arranged asymmetrically in the interior rows. The heading is minimal (just "The Property" in the display serif). Hover is a slow, subtle zoom (800ms). No dots, no arrows, no lightbox thumbnails, no "View all 47 photos" link. Each image is large enough to be appreciated at scroll pace. The `alt` text describes scenes with sensory detail. On mobile, images stack simply — the editorial grid adapts gracefully rather than fighting the viewport.

### Bad

```html
<section class="photo-gallery">
  <h2>Photo Gallery</h2>
  <div class="gallery-filters">
    <button class="filter active">All</button>
    <button class="filter">Rooms</button>
    <button class="filter">Dining</button>
    <button class="filter">Pool</button>
    <button class="filter">Spa</button>
    <button class="filter">Events</button>
  </div>
  <div class="thumbnail-grid">
    <div class="thumb" onclick="openLightbox(0)"><img src="thumb-01.jpg" /></div>
    <div class="thumb" onclick="openLightbox(1)"><img src="thumb-02.jpg" /></div>
    <div class="thumb" onclick="openLightbox(2)"><img src="thumb-03.jpg" /></div>
    <div class="thumb" onclick="openLightbox(3)"><img src="thumb-04.jpg" /></div>
    <div class="thumb" onclick="openLightbox(4)"><img src="thumb-05.jpg" /></div>
    <div class="thumb" onclick="openLightbox(5)"><img src="thumb-06.jpg" /></div>
    <div class="thumb" onclick="openLightbox(6)"><img src="thumb-07.jpg" /></div>
    <div class="thumb" onclick="openLightbox(7)"><img src="thumb-08.jpg" /></div>
    <div class="thumb" onclick="openLightbox(8)"><img src="thumb-09.jpg" /></div>
    <div class="thumb" onclick="openLightbox(9)"><img src="thumb-10.jpg" /></div>
    <div class="thumb" onclick="openLightbox(10)"><img src="thumb-11.jpg" /></div>
    <div class="thumb" onclick="openLightbox(11)"><img src="thumb-12.jpg" /></div>
  </div>
  <button class="load-more">Load More Photos</button>
</section>
```

**Why this fails:** This is a file browser, not a visual experience. The uniform thumbnail grid (twelve identical squares) strips every image of its compositional power — a sweeping landscape and a bathroom detail are given identical weight and size. Filter tabs assume the guest wants to browse by category rather than experience a curated narrative; they add UI complexity without adding value for most visitors. Inline `onclick` handlers are an accessibility failure — keyboard users and screen readers cannot interact meaningfully. Thumbnail-to-lightbox is a pattern from 2008 that asks the guest to click to see each image at a useful size. "Load More" implies there are so many photos that curation was abandoned. None of the images have `alt` text, `srcset`, or dimensions.
