# Berel's Herring Co. — Project Guidelines

This file is read automatically by Claude Code at the start of every session in this repo.
It defines the brand, design, and platform rules for this project. Follow it on every task
unless explicitly told otherwise in a specific prompt.

---

## Project Overview

**Brand:** Berel's Herring Co.
**Product:** Cured herring and cured fish (classic, cream, spicy, in oil, etc.), sold primarily
for Shabbat, holidays (yom tov), simchas, and catered events.
**Market:** Israel — English-language site only (no Hebrew/bilingual support needed).
**Platform:** Shopify (Liquid theme).

---

## Brand Voice & Tone

- **Confident and witty.** Punchy, clever copy with light personality. Wordplay/fish puns are
  welcome but used sparingly — never cartoonish or overdone.
- **Not folksy or "grandma's kitchen."** This is a modern, design-forward specialty food brand —
  closer to the energy of brands like Graza or Fishwife than an old-world deli.
- Still warm and approachable, and must feel trustworthy for ordering food for holidays/events.
- Sample tone reference (for copywriting consistency):
  - "Cured the right way. Since forever."
  - "We take the fish seriously. Ourselves? Less so."
  - "Bringing the herring to the party — literally."
  - "Friday's busy. We make this part easy."
  - CTA buttons: prefer phrases like "Get Curing" over generic "Shop Now" where it fits naturally.

---

## Visual Identity

### Color Palette
- **Primary:** Bright cyan / turquoise (brand color, matches logo) — dominant brand color
- **Secondary:** Deep cobalt navy — used for contrast sections/backgrounds
- **Accent:** Warm amber/orange — reserved for CTAs ("Order Now," "Add to Cart")
- **White:** Clean space, labels, breathing room

> Do not introduce additional brand colors without explicit approval. Do not soften the palette
> into pastels — the brand is bold and saturated, not muted.

### Typography
- Headlines: bold, rounded, geometric sans-serif (energy similar to Circular, Poppins Bold, or Söhne)
- Body copy: clean, simple sans-serif, high legibility
- Avoid serif fonts, script fonts, or anything that reads "traditional deli" — this brand is modern

### Photography Style
- Product shots: solid seamless color backgrounds (cyan or navy), studio-lit, high-contrast —
  this is the dominant visual language across the site
- Lifestyle/occasion shots: used selectively, only in Catering/Events and Shabbat & Holiday
  sections, to convey social/celebratory use
- **Stock photography rule:** Any supplemental stock images (e.g., cured/raw salmon) must match
  the bold-background, high-contrast studio style. Do NOT use soft, natural-light, or lifestyle-
  blog-style stock photos — they will visually clash with existing brand photography. Always flag
  in your response which images are brand-owned vs. suggested stock.

---

## Site Structure

1. **Homepage** — hero (logo + confident headline), featured products, freshness story
2. **About / Our Story** — heritage, curing tradition, brand personality
3. **Products** (e-commerce) — herring varieties, other cured fish, add-to-cart/checkout
4. **Catering / Events** — bulk/custom orders via WhatsApp button
5. **Shabbat & Holiday Specials** — seasonal ordering, weekly cutoff time messaging
6. **Order / Contact** — pickup vs. delivery toggle, scheduled time slots, WhatsApp + checkout entry points
7. **Gallery** — product and event photos

---

## Shopify Technical Conventions

- This is a **Shopify theme** project — implement using Liquid templates, sections, and JSON
  section schema. Do not build a custom non-Shopify framework.
- Base theme: **[fill in: e.g., Dawn / Refresh / purchased theme name]**. Reuse and restyle
  existing sections/components (product grid, cart drawer, etc.) where possible rather than
  rebuilding from scratch.
- Expose editable content (text, images, colors) via `settings_schema.json` / section schema so
  changes can be made later in the Shopify theme editor without touching code.
- **Checkout:** Use Shopify's native cart and checkout. Do not build a custom checkout flow.
- **WhatsApp ordering:** Implement as a button/section linking to a `wa.me` URL (with a pre-filled
  message where possible), not a third-party app, unless a specific app is explicitly approved.
- **Pickup/delivery scheduling:** Flag tradeoffs between a Shopify app (for date/time slot
  selection) vs. a native Liquid-built solution before implementing — don't assume either by default.
- Use metafields for variant-heavy products (herring varieties, sizes) rather than hardcoding
  variant logic.
- Always work from the local theme repo (pulled via `shopify theme pull`) — edit actual
  `.liquid` / `.json` / `.css` files, not generic HTML that won't drop into Shopify.

---

## Things to Never Do

- Don't deviate from the cyan / navy / amber palette without explicit approval
- Don't add a third-party checkout app — native Shopify checkout only
- Don't use soft/natural-light stock photography that clashes with the bold studio aesthetic
- Don't make the copy folksy, "heritage deli," or overly sentimental — keep it witty and modern
- Don't build a sprawling mega-catalog navigation — keep the site tight and product-forward,
  not a general fish-market catalog
- Don't push directly to the live/published theme — always create or push to an unpublished
  theme for review first

---

## Conversion Optimization Requirements

Every page and component built for this site must incorporate high-converting
e-commerce patterns. The following are non-negotiable unless explicitly told
otherwise in a specific prompt.

### Trust & Social Proof
- Display review counts and star ratings prominently near every product and CTA
- Show real customer photos/UGC alongside reviews where possible
- Display trust badges near checkout (secure payment, money-back guarantee, SSL)
- Show a "X people ordered this week" 
  product pages — use Berel's brand voice, not generic copy
- Display any press mentions or community endorsements ("As featured in...")

### Urgency & Scarcity
- Show low stock warnings when inventory is limited ("Only 3 left!")
- Display Shabbat/holiday order cutoff countdowns prominently on the homepage
  and product pages (e.g. "Order by Thursday 3PM for Shabbat delivery")
- Highlight limited-edition or seasonal products with a badge

### Friction Reduction
- Sticky add-to-cart bar that follows the user as they scroll down a product page
- One-click reorder for returning customers
- Guest checkout must always be available — never force account creation before
  purchase
- Autofill-friendly address and payment fields
- Show total cost (including delivery fee) as early as possible — never surprise
  with fees at the final checkout step
- Progress indicator on all multi-step checkout flows

### Cart & Checkout
- Slide-out cart drawer (not a separate cart page) so users never lose their place
- Upsell/cross-sell inside the cart drawer — e.g. "Customers also add..." with
  1–2 complementary products, never more than 2
- Free shipping or free delivery threshold bar in cart
  ("Add ₪X more for free delivery")
- Ensure email is captured before checkout completion so abandoned carts can
  be recovered via Shopify's built-in flows

### Product Pages
- Above the fold: product image, name, price, star rating, and add-to-cart
  button — no scrolling required to purchase on desktop or mobile
- Minimum 3 product photos per variant (flat-lay, close-up, lifestyle)
- Short punchy benefit bullets above the fold; full description below
- Clear variant selector (flavor/size/quantity) with visual labels
- Delivery date estimate on every product page
  ("Order today — arrives by Shabbat" or "Ready for pickup Thursday")
- Sticky CTA button on mobile at all times

### Homepage
- Hero section must have a single focused CTA — no competing buttons
- Social proof number in or immediately below the hero
  ("Trusted by 2,000+ families every Shabbat")
- Featured bestsellers visible without scrolling on desktop
- Announcement bar at the very top for cutoff times, free delivery threshold,
  or seasonal promotions

### Mobile
- All tap targets minimum 48px height
- Mobile checkout must be completable with one thumb
- Use Shopify's native CDN and lazy loading for all below-fold images
- No full-screen popups on mobile within the first 3 seconds
  (Google ranking penalty + bad UX)

### Email & Retention
- Exit-intent popup on desktop only (not mobile) — offer a discount or Shabbat
  reminder email signup
- Post-purchase upsell page before the order confirmation screen
- Shopify abandoned cart emails must be configured at 1hr, 24hr, and 72hr

### Conversion Copy Rules
- Never use generic button text ("Submit," "Click Here," "Buy")
- Always use action-specific, brand-voiced CTA copy:
  ("Add to Cart," "Order for Shabbat," "Get Curing," "Send My Order")
- Every section headline should answer "what's in it for me" for the customer

### Things to Never Do (Conversion)
- Never show a blank or empty cart — always suggest products
- Never use more than one primary CTA per section
- Never hide pricing or require login to see prices
- Never let a page load slower than 3 seconds — flag any component that risks
  this before building it

---

## Open Items / To Confirm

- [ ] Base Shopify theme name
- [ ] Delivery zones / areas served
- [ ] Payment processor (Shopify Payments vs. other)
- [ ] Final hex codes for cyan / navy / amber (pull exact values from logo file)
- [ ] Pickup/delivery scheduling: app vs. native build decision
