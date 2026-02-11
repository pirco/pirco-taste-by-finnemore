# Artisan Examples

Positive and negative calibration pairs for boutique brands, studios, and curated e-commerce. These show the artisan taste in action.

---

## 1. Product Grid

### Good

```html
<section class="collection">
  <h2 class="collection-heading">Spring Ceramics</h2>
  <div class="product-grid">
    <article class="product-card">
      <a href="/products/celadon-vase">
        <figure class="product-image" style="aspect-ratio: 3/2;">
          <img
            src="/images/celadon-vase-640.webp"
            srcset="/images/celadon-vase-640.webp 640w, /images/celadon-vase-1024.webp 1024w"
            sizes="(max-width: 768px) 100vw, 50vw"
            alt="Celadon vase on a linen cloth beside dried eucalyptus branches"
            width="640" height="427" loading="lazy"
          >
        </figure>
        <div class="product-info">
          <h3>Celadon Vase</h3>
          <p class="product-price">$185</p>
        </div>
      </a>
    </article>
    <article class="product-card">
      <a href="/products/ash-bowl">
        <figure class="product-image" style="aspect-ratio: 2/3;">
          <img
            src="/images/ash-bowl-640.webp"
            srcset="/images/ash-bowl-640.webp 640w, /images/ash-bowl-1024.webp 1024w"
            sizes="(max-width: 768px) 100vw, 50vw"
            alt="Ash-glazed bowl photographed from above on a raw oak surface"
            width="640" height="960" loading="lazy"
          >
        </figure>
        <div class="product-info">
          <h3>Ash Bowl</h3>
          <p class="product-price">$120</p>
        </div>
      </a>
    </article>
  </div>
</section>
```

```css
.collection {
  padding: var(--space-48) var(--space-8);
}

.collection-heading {
  font-size: var(--text-sm);
  font-weight: 400;
  letter-spacing: 0.06em;
  text-transform: uppercase;
  color: var(--color-text-muted);
  margin-bottom: var(--space-16);
}

.product-grid {
  columns: 2;
  column-gap: var(--space-16);
  max-width: 1280px;
  margin: 0 auto;
}

@supports (grid-template-rows: masonry) {
  .product-grid {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    grid-template-rows: masonry;
    gap: var(--space-16);
    columns: unset;
  }
}

.product-card {
  break-inside: avoid;
  margin-bottom: var(--space-16);
}

.product-card a {
  text-decoration: none;
  color: inherit;
  display: block;
}

.product-image {
  margin: 0;
  overflow: hidden;
}

.product-image img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  transition: transform var(--transition-image) cubic-bezier(0.4, 0, 0.2, 1);
}

.product-card a:hover .product-image img {
  transform: scale(1.03);
}

.product-info {
  padding-top: var(--space-4);
}

.product-info h3 {
  font-family: var(--font-display);
  font-size: var(--text-lg);
  font-weight: 400;
  color: var(--color-text-primary);
}

.product-info .product-price {
  font-size: var(--text-sm);
  color: var(--color-text-secondary);
  margin-top: var(--space-1);
}

@media (max-width: 768px) {
  .product-grid {
    columns: 1;
  }

  @supports (grid-template-rows: masonry) {
    .product-grid {
      grid-template-columns: 1fr;
    }
  }
}
```

**Why this works:** Two-column masonry grid with mixed aspect ratios (3:2 landscape paired with 2:3 portrait) creates visual tension and a gallery feel. Each card shows only what matters: the image, the name, the price. Generous 64px column gap gives each product room to breathe. The collection heading is small and muted — the products dominate. Hover effect is a slow, subtle zoom. The entire card is one link with no secondary actions.

### Bad

```html
<section class="products-section">
  <div class="section-header">
    <h2>Our Collection</h2>
    <div class="filter-bar">
      <button class="active">All</button>
      <button>Vases</button>
      <button>Bowls</button>
      <button>Plates</button>
      <button>Mugs</button>
    </div>
    <select class="sort-dropdown">
      <option>Sort by: Featured</option>
      <option>Price: Low to High</option>
      <option>Price: High to Low</option>
      <option>Newest</option>
    </select>
  </div>
  <div class="product-grid four-col">
    <div class="product-card">
      <div class="card-badges">
        <span class="badge badge-sale">SALE</span>
        <span class="badge badge-new">NEW</span>
      </div>
      <img src="vase.jpg" />
      <div class="card-overlay">
        <button class="quick-view-btn">Quick View</button>
        <button class="add-to-cart-btn">Add to Cart</button>
        <button class="wishlist-btn">♡</button>
      </div>
      <div class="card-info">
        <h3>Celadon Vase</h3>
        <div class="rating">★★★★☆ (24 reviews)</div>
        <div class="price">
          <span class="price-was">$220</span>
          <span class="price-now">$185</span>
        </div>
      </div>
    </div>
    <!-- 11 more identical cards -->
  </div>
  <div class="pagination">
    <button>← Previous</button>
    <span>Page 1 of 8</span>
    <button>Next →</button>
  </div>
</section>
```

**Why this fails:** Four-column grid makes each product image too small to appreciate craft and detail. "SALE" and "NEW" badges are mass-market noise — a curated boutique doesn't label products like a department store. Star ratings and review counts transform an artisan product into a commodity. Strikethrough pricing ("was $220") introduces discount-store psychology. Quick-view, add-to-cart, and wishlist hover overlays turn browsing into a transaction from the first touch. Five filter categories in the header assume a catalog-sized inventory. A sort dropdown suggests the curation has no opinion about sequence. Eight pages of pagination reveal a catalog, not a curated selection. The entire experience feels like scrolling Amazon, not visiting an atelier.

---

## 2. Product Detail Page

### Good

```html
<article class="product-detail">
  <figure class="product-hero">
    <img
      src="/images/celadon-vase-hero-1280.webp"
      srcset="/images/celadon-vase-hero-1024.webp 1024w, /images/celadon-vase-hero-1280.webp 1280w, /images/celadon-vase-hero-1920.webp 1920w"
      sizes="100vw"
      alt="Celadon vase in warm afternoon light on a raw wood shelf"
      width="1920" height="1280" loading="eager" fetchpriority="high"
    >
  </figure>

  <div class="product-content">
    <h1>Celadon Vase</h1>
    <p class="product-price">$185</p>
    <div class="product-description">
      <p>Wheel-thrown in our Berlin studio, this vase carries the quiet green of celadon glaze that has been refined across three firings. Each piece varies — the glaze pools and breaks differently every time, leaving traces of the clay body beneath.</p>
    </div>
    <dl class="product-details">
      <dt>Material</dt>
      <dd>Stoneware, celadon glaze</dd>
      <dt>Dimensions</dt>
      <dd>18cm height, 12cm diameter</dd>
      <dt>Care</dt>
      <dd>Hand wash recommended</dd>
    </dl>
    <a href="/cart/add/celadon-vase" class="add-to-bag">Add to bag</a>
  </div>

  <div class="product-gallery">
    <figure>
      <img src="/images/celadon-vase-detail-1.webp" alt="Close-up of celadon glaze showing subtle crackle pattern" width="1280" height="1600" loading="lazy">
    </figure>
    <figure>
      <img src="/images/celadon-vase-context-1.webp" alt="Celadon vase holding dried wildflowers on a kitchen counter" width="1280" height="853" loading="lazy">
    </figure>
    <figure>
      <img src="/images/celadon-vase-process-1.webp" alt="Hands shaping the vase on a potter's wheel" width="1280" height="1280" loading="lazy">
    </figure>
  </div>
</article>
```

```css
.product-hero {
  margin: 0;
  width: 100%;
}

.product-hero img {
  width: 100%;
  height: auto;
  min-height: 60vh;
  object-fit: cover;
}

.product-content {
  max-width: 680px;
  margin: 0 auto;
  padding: var(--space-24) var(--space-6);
}

.product-content h1 {
  font-family: var(--font-display);
  font-size: clamp(2rem, 4vw, 3.75rem);
  font-weight: 400;
  line-height: 1.1;
  letter-spacing: -0.04em;
  color: var(--color-text-primary);
  margin-bottom: var(--space-4);
}

.product-price {
  font-size: var(--text-lg);
  color: var(--color-text-secondary);
  margin-bottom: var(--space-12);
}

.product-description p {
  font-size: var(--text-base);
  line-height: 1.6;
  color: var(--color-text-primary);
  margin-bottom: var(--space-8);
}

.product-details {
  display: grid;
  grid-template-columns: auto 1fr;
  gap: var(--space-2) var(--space-8);
  font-size: var(--text-sm);
  color: var(--color-text-secondary);
  padding: var(--space-8) 0;
  border-top: 1px solid var(--color-border-subtle);
  margin-bottom: var(--space-12);
}

.product-details dt {
  color: var(--color-text-muted);
}

.add-to-bag {
  display: inline-block;
  font-size: var(--text-base);
  font-weight: 500;
  color: var(--color-bg);
  background: var(--color-text-primary);
  padding: var(--space-3) var(--space-8);
  text-decoration: none;
  transition: opacity var(--transition-standard) ease;
}

.add-to-bag:hover {
  opacity: 0.85;
}

.product-gallery {
  max-width: 1280px;
  margin: var(--space-16) auto 0;
  padding: 0 var(--space-8);
  display: grid;
  gap: var(--space-8);
}

.product-gallery figure {
  margin: 0;
}

.product-gallery img {
  width: 100%;
  height: auto;
}
```

**Why this works:** Opens with a full-width hero image that sets the mood before any text. Product name uses the display typeface at generous size with tight letter-spacing — it reads like a title, not a label. Price is secondary, not competing with the name. The description is written as prose — you can hear a human voice. Materials and dimensions use a definition list for semantic clarity without visual heaviness. "Add to bag" is a single, quiet link-styled button. The image gallery below tells a story: glaze detail, product in context, maker at work. No zoom tool, no 360-degree view, no thumbnail strip — just images presented editorially.

### Bad

```html
<div class="product-page">
  <div class="product-layout two-col">
    <div class="image-column">
      <div class="main-image-container">
        <img src="vase-main.jpg" id="zoom-target" />
        <div class="zoom-lens"></div>
        <button class="view-360">360° View</button>
      </div>
      <div class="thumbnail-strip">
        <img src="vase-thumb-1.jpg" class="active" />
        <img src="vase-thumb-2.jpg" />
        <img src="vase-thumb-3.jpg" />
        <img src="vase-thumb-4.jpg" />
        <img src="vase-thumb-5.jpg" />
      </div>
    </div>
    <div class="info-column">
      <div class="breadcrumb">Home > Ceramics > Vases > Celadon Vase</div>
      <h1>Celadon Vase</h1>
      <div class="rating-block">★★★★☆ 4.3 (47 reviews) | 128 sold</div>
      <div class="urgency-banner">🔥 Only 3 left in stock - order soon!</div>
      <div class="price-block">
        <span class="price-original">$220</span>
        <span class="price-sale">$185</span>
        <span class="savings">Save 16%!</span>
      </div>
      <div class="quantity-selector">
        <button>-</button><input value="1"><button>+</button>
      </div>
      <button class="add-to-cart-btn large">ADD TO CART</button>
      <button class="buy-now-btn">BUY IT NOW</button>
      <div class="trust-badges">
        <span>🔒 Secure Checkout</span>
        <span>🚚 Free Shipping</span>
        <span>↩️ Easy Returns</span>
      </div>
      <div class="accordion">
        <details><summary>Description</summary>...</details>
        <details><summary>Size Chart</summary>...</details>
        <details><summary>Shipping & Returns</summary>...</details>
        <details><summary>Reviews (47)</summary>...</details>
      </div>
      <div class="cross-sell">
        <h3>Complete the look</h3>
        <div class="mini-carousel"><!-- 6 related products --></div>
      </div>
    </div>
  </div>
</div>
```

**Why this fails:** The two-column layout crams everything above the fold like a conversion optimization experiment. Zoom lens and 360-degree view are technical features that add complexity without serving the artisan aesthetic. Breadcrumb navigation exposes database taxonomy. Star ratings, review count, and "128 sold" reduce a handmade object to a commodity metric. The urgency banner ("Only 3 left!") is a manipulation tactic unworthy of a craft brand. Strikethrough pricing with "Save 16%!" screams discount store. A quantity selector for a one-of-a-kind ceramic is absurd. Two competing CTAs ("Add to Cart" and "Buy It Now") create decision anxiety. Trust badges assume distrust. Accordion menus hide the information that should be openly presented. A six-item cross-sell carousel turns the product page into a funnel, not a portrait.

---

## 3. Homepage

### Good

```html
<main class="home">
  <section class="home-hero">
    <figure class="home-hero-image">
      <img
        src="/images/studio-hero-1920.webp"
        srcset="/images/studio-hero-1024.webp 1024w, /images/studio-hero-1280.webp 1280w, /images/studio-hero-1920.webp 1920w"
        sizes="100vw"
        alt="Morning light falling across a shelf of unglazed stoneware vessels in the studio"
        width="1920" height="1080" loading="eager" fetchpriority="high"
      >
    </figure>
    <div class="home-hero-content">
      <h1>Maren Keramik</h1>
      <p>Wheel-thrown stoneware from our Berlin studio.</p>
      <a href="/shop" class="home-hero-link">Shop</a>
    </div>
  </section>
</main>
```

```css
.home-hero {
  position: relative;
  min-height: 100vh;
}

.home-hero-image {
  margin: 0;
  position: absolute;
  inset: 0;
}

.home-hero-image img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.home-hero-content {
  position: relative;
  z-index: 1;
  display: flex;
  flex-direction: column;
  justify-content: flex-end;
  min-height: 100vh;
  padding: var(--space-16) var(--space-8);
  color: #faf9f7; /* light text on image — adjust per image */
}

.home-hero-content h1 {
  font-family: var(--font-display);
  font-size: clamp(2.5rem, 5vw, 4.5rem);
  font-weight: 400;
  line-height: 1.05;
  letter-spacing: -0.05em;
}

.home-hero-content p {
  font-size: var(--text-lg);
  margin-top: var(--space-4);
  opacity: 0.85;
}

.home-hero-link {
  font-size: var(--text-base);
  color: inherit;
  text-decoration: underline;
  text-underline-offset: 4px;
  margin-top: var(--space-6);
  width: fit-content;
}
```

**Why this works:** One full-bleed image. Brand name. One line of copy. A single "Shop" link. That's the entire homepage above the fold — and it's everything the visitor needs. The image does the selling. The typography is confident at display scale with tight tracking. The text sits at the bottom of the viewport, leaving the image unobstructed. No slideshow, no product grid, no categories, no promotional content. The visitor feels like they've arrived somewhere with a point of view.

### Bad

```html
<main class="homepage">
  <div class="hero-slideshow">
    <div class="slide active">
      <img src="slide1.jpg" />
      <div class="slide-content">
        <h2>New Spring Collection</h2>
        <button>Shop Now</button>
      </div>
    </div>
    <div class="slide"><!-- slide 2 --></div>
    <div class="slide"><!-- slide 3 --></div>
    <div class="slide"><!-- slide 4 --></div>
    <div class="slide"><!-- slide 5 --></div>
    <div class="slideshow-dots"><!-- 5 dots --></div>
  </div>
  <section class="shop-by-category">
    <h2>Shop by Category</h2>
    <div class="category-grid four-col">
      <a href="/vases"><img src="cat-vases.jpg"><span>Vases</span></a>
      <a href="/bowls"><img src="cat-bowls.jpg"><span>Bowls</span></a>
      <a href="/plates"><img src="cat-plates.jpg"><span>Plates</span></a>
      <a href="/mugs"><img src="cat-mugs.jpg"><span>Mugs</span></a>
    </div>
  </section>
  <section class="featured-products">
    <h2>Best Sellers</h2>
    <div class="product-carousel"><!-- 8 products in a scrolling carousel --></div>
  </section>
  <section class="as-seen-in">
    <h2>As Seen In</h2>
    <div class="logo-bar">
      <img src="vogue.svg" /><img src="elle.svg" /><img src="nyt.svg" /><img src="monocle.svg" />
    </div>
  </section>
  <div class="newsletter-popup" id="popup">
    <h3>Get 10% Off Your First Order!</h3>
    <input placeholder="Enter your email" />
    <button>Subscribe</button>
    <button class="close">✕</button>
  </div>
</main>
```

**Why this fails:** A five-slide hero carousel guarantees that four of five messages go unseen — and the auto-advance steals user control. "Shop by Category" in a four-column grid treats a curated studio like a department store. "Best Sellers" as a product carousel prioritizes algorithm over curation. The "As Seen In" logo bar is self-congratulatory — press mentions belong on an about page, not the homepage. The newsletter popup with a discount code appears before the visitor has seen a single product, poisoning the first impression with a transaction. Every section screams "convert!" when the homepage should whisper "welcome."

---

## 4. Navigation

### Good

```html
<header class="site-header">
  <nav class="nav" aria-label="Main navigation">
    <a href="/" class="nav-logo">Maren Keramik</a>
    <ul class="nav-links" role="list">
      <li><a href="/shop">Shop</a></li>
      <li><a href="/about">About</a></li>
      <li><a href="/contact">Contact</a></li>
    </ul>
    <a href="/cart" class="nav-cart" aria-label="Cart">
      <svg width="20" height="20" viewBox="0 0 20 20" fill="none" stroke="currentColor" stroke-width="1.5">
        <path d="M5 7h10l-1 8H6L5 7z"/>
        <path d="M8 7V5a2 2 0 0 1 4 0v2"/>
      </svg>
    </a>
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
  height: 60px;
}

.nav-logo {
  font-family: var(--font-display);
  font-size: var(--text-lg);
  font-weight: 400;
  letter-spacing: -0.02em;
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
  transition: color 200ms ease;
}

.nav-links a:hover {
  color: var(--color-text-primary);
}

.nav-cart {
  color: var(--color-text-secondary);
  transition: color 200ms ease;
}

.nav-cart:hover {
  color: var(--color-text-primary);
}
```

**Why this works:** Logo left, three text links center-right, cart icon far right. Total nav height: 60px. The logo uses the display typeface at a modest size — it identifies without dominating. Three links (Shop, About, Contact) are everything a boutique needs. The cart icon is a simple SVG outline — no badge, no item count, no color. The entire header is one row with no announcement bar, no search bar, no account icon, no wishlist. It orients the visitor in a glance and then gets out of the way.

### Bad

```html
<header class="mega-header">
  <div class="announcement-bar">
    <p>Free shipping on orders over $150 | Use code SPRING15 for 15% off</p>
  </div>
  <div class="header-top">
    <div class="header-search">
      <input type="search" placeholder="Search products..." />
    </div>
    <a href="/" class="logo">
      <img src="logo-full.svg" width="180" height="50" alt="Maren Keramik" />
    </a>
    <div class="header-icons">
      <button class="icon-btn" aria-label="Search"><svg><!-- search --></svg></button>
      <a href="/account" class="icon-btn" aria-label="Account"><svg><!-- person --></svg></a>
      <button class="icon-btn" aria-label="Wishlist"><svg><!-- heart --></svg> <span class="badge">3</span></button>
      <button class="icon-btn" aria-label="Cart"><svg><!-- cart --></svg> <span class="badge">2</span></button>
    </div>
  </div>
  <nav class="main-nav">
    <ul>
      <li class="has-mega-menu">
        <a href="/shop">Shop All</a>
        <div class="mega-menu">
          <div class="mega-col"><h4>By Type</h4><ul><li>Vases</li><li>Bowls</li><li>Plates</li><li>Mugs</li><li>Planters</li></ul></div>
          <div class="mega-col"><h4>By Collection</h4><ul><li>Spring 2024</li><li>Essentials</li><li>Limited Edition</li></ul></div>
          <div class="mega-col"><h4>By Material</h4><ul><li>Stoneware</li><li>Porcelain</li><li>Earthenware</li></ul></div>
          <div class="mega-col featured"><img src="promo.jpg" /><p>New: Spring Collection</p></div>
        </div>
      </li>
      <li><a href="/about">Our Story</a></li>
      <li><a href="/journal">Journal</a></li>
      <li><a href="/stockists">Stockists</a></li>
      <li><a href="/wholesale">Wholesale</a></li>
      <li><a href="/contact">Contact</a></li>
    </ul>
  </nav>
</header>
```

**Why this fails:** Three rows of header content (announcement bar, logo/icons row, navigation row) consume 150px+ of vertical space before any content appears. The announcement bar leads with a discount code — training visitors to expect markdowns before they see a single product. A persistent search bar assumes a catalog large enough to require search; for a boutique studio, it's premature infrastructure. Account and wishlist icons with numbered badges add marketplace complexity. The mega-menu exposes the entire product taxonomy (by type, collection, and material) — this is catalog logic, not gallery logic. A promotional image inside the mega-menu turns navigation into advertising. Six navigation items (Shop All, Our Story, Journal, Stockists, Wholesale, Contact) force the visitor to parse too many paths. The overall effect: a small studio presenting itself as if it were a department store.
