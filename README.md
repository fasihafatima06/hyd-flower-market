# Gudimalkapur Today

A frontend-first digital window into Hyderabad's Gudimalkapur wholesale flower market.

> See today's market. Compare real sellers. Order without the trip.

---

## The Problem

Gudimalkapur is Hyderabad's largest wholesale flower market. Every morning before dawn, **hundreds of buyers** — wedding decorators, temple committees, event planners, retail florists — travel to the market in person to source fresh flowers.

**What they face:**

- **4–5 AM trips** in the dark, often across the city, just to see what's available and at what price.
- **No price visibility** until they arrive. Each seller sets their own rate and there's no way to compare without walking stall to stall.
- **Wasted trips** when a specific flower is out of stock or overpriced that morning — the buyer only finds out after reaching the market.
- **No structured ordering.** Everything runs on verbal agreements, hand-written notes, and WhatsApp voice messages. Miscommunication leads to wrong quantities, missed deliveries, and disputes.
- **Time pressure.** Flowers are perishable. Buying, transporting, and arranging must happen within a 4–5 hour window before events start.

**On the seller side:**

- Vendors are locked to foot traffic. Their customer base is limited to whoever physically walks past their stall that morning.
- Most sellers operate on basic smartphones with limited data plans. Complex apps don't work for them.
- They have no digital catalog, no way to publish prices, and no order management beyond memory and phone calls.

---

## How We Solve It

Gudimalkapur Today gives both sides a **simple, organized digital window** into the same physical market — without replacing the market itself.

### For Buyers

- **Browse today's market from anywhere.** See every flower available this morning with real prices, updated by 5:30 AM.
- **Compare sellers side by side.** Pick a flower, then see which sellers have it, at what price, in what quantity, and with what minimum order.
- **Order from multiple sellers in one cart.** One checkout fans out to each independent seller — no middleman, no markup.
- **Request a custom match.** Describe what you need ("something pink for a birthday, under ₹500") and the system finds available market listings that fit.
- **Track your order.** See when sellers accept, when flowers are collected, and when the driver is on the way with an estimated arrival time.

### For Sellers

- **Publish your own prices.** Set per-kg, per-piece, or per-bunch prices exactly as you quote at the stall. The platform never changes your number.
- **Reach customers beyond foot traffic.** Your listing is visible to every buyer browsing the market that morning.
- **Receive and manage orders.** Accept incoming orders, mark them ready, and send them to the driver — all from your phone browser.
- **Zero app install required.** The entire product runs in a mobile browser. No Play Store download, no storage, no updates.

### Product Principle

> **We do not digitize the people. We digitize the transaction around them.**

The physical market remains the source of supply, sellers remain independent, and buyers retain seller choice.

---

## What Impact This Could Have

| Problem | Current Reality | With Gudimalkapur Today |
|---|---|---|
| **Wasted buyer trips** | 30–60 min travel to discover stock/prices | Browse the full market from home by 5:30 AM |
| **No price transparency** | Walk stall-to-stall to compare | Compare every seller for a flower in one screen |
| **Seller reach** | Limited to physical foot traffic | Every morning buyer in the city can see your listing |
| **Order errors** | Verbal agreements, memory-based | Structured cart with quantities, units, and seller names |
| **Delivery coordination** | Buyer arranges own transport | Scheduled morning delivery with driver tracking |
| **Flower waste** | Unsold stock spoils by afternoon | Better demand visibility helps sellers stock accurately |
| **Time pressure** | 4–5 hour window, mostly spent travelling | Ordering done remotely; time goes to setup and arrangement |

---

## What It Includes

- Customer and seller role entry with separate demo login screens
- Flower-first market browsing with seller-specific prices
- 20+ flower listings with kg, piece, bunch, bundle, stem, and garland units
- Seller comparison with minimum-order and stock validation
- Customer cart, multi-seller checkout, and scheduled morning delivery details
- Customization Request with local catalog matching and reference-image upload
- Pre-made arrangements catalog
- Seller dashboard with incoming customer orders
- Seller listing creation with photo upload and kg, piece, and bunch prices
- Seller order progression: accept, ready, sent to driver, completed
- Customer delivery tracking with driver ETA notifications
- Customer order timeline synchronized through localStorage across browser tabs
- Optimized image loading with Wikimedia thumbnail conversion
- Reset Demo control for interviews and walkthroughs
- Responsive pastel botanical interface built with vanilla HTML, CSS, and JavaScript

## Run Locally

No build step is required.

```powershell
python -m http.server 8000
```

Open <http://localhost:8000>.

## Deploy On Netlify

This is a static site. In Netlify:

1. Choose **Add new site** and **Import an existing project**.
2. Select this GitHub repository.
3. Use these build settings:
   - Build command: leave blank
   - Publish directory: `.`
4. Deploy the site.

`netlify.toml` is included with the same settings.

## Prototype Notes

- Data is stored in local JavaScript objects and browser `localStorage`.
- Login is intentionally a demo flow; production authentication needs secure phone verification.
- Images are sourced from Wikimedia Commons and loaded as optimized thumbnails.
- Customization matching is local and deterministic in this frontend-only prototype. Connect a secure `/api/customize` endpoint before using a production LLM.
- Seller order actions are prototype coordination controls, not a real WhatsApp or delivery integration.
