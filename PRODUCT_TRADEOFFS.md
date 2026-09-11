# Product Trade-offs — Gudimalkapur Today
### Designing for low-tech wholesale flower market vendors

---

## Guiding Principle

> **We digitize the transaction around the people, not the people themselves.**
> The physical market remains the supply source. Sellers stay independent. Buyers retain seller choice.

Every trade-off below follows from this constraint.

---

## 1. Authentication: Demo Login vs. Secure Phone OTP

| Chose | Over | Why |
|---|---|---|
| Pre-filled demo login | OTP / Aadhaar verification | Vendors operate on basic smartphones at 5 AM with unreliable signal. A frictionless entry point lets us validate the concept before adding auth infrastructure. |

> [!IMPORTANT]
> Production requires secure phone verification, but gating on it now would prevent any vendor from trialling the product.

## 2. Seller-Set Pricing — No Platform Price Override

Each seller publishes their own price per unit. The platform **never normalizes, caps, or suggests** prices.

- **Gained:** Trust. A vendor who sees their number shown exactly as entered will return tomorrow.
- **Lost:** Ability to flag outliers to buyers (e.g., jasmine at ₹720/kg when the morning average is ₹540). Buyer-side price guidance is deferred.

## 3. Multi-Unit Listing (kg / piece / bunch / garland)

Gudimalkapur sellers quote in whichever unit suits the flower — jasmine by kg, roses by piece, lilies by bunch. The product supports **all native units** rather than forcing a standard.

- **Gained:** Listings mirror how the vendor already thinks and quotes at the stall.
- **Lost:** Clean cross-seller price comparison. A buyer comparing ₹540/kg jasmine with ₹8/piece roses has to reason across units themselves.

## 4. Order Coordination: localStorage, Not WhatsApp

Orders fan out to multiple independent sellers, but coordination lives in **browser localStorage** — not real WhatsApp messages or a backend.

- **Gained:** A working multi-seller checkout prototype with zero server cost and instant cross-tab sync.
- **Lost:** Real seller notifications. The "WhatsApp preview" screen is honest labeling of a simulation. Actual integration requires a WhatsApp Business API or SMS gateway.

## 5. AI Customization: Local Deterministic Matching Only

The "Custom Match" feature filters the **existing local catalog** by color, budget, and availability. No external LLM, no image recognition, no generative suggestions.

- **Gained:** Predictable, explainable results a vendor can trust. No hallucinated inventory. Runs offline.
- **Lost:** Sophisticated style matching (e.g., "something like this Pinterest photo"). Real image-based matching requires a production `/api/customize` endpoint with guardrails.

## 6. Delivery: Flat ₹120, Single Morning Window

A single flat delivery fee with a fixed 7:30–9:00 AM window replaces route-optimized, distance-based pricing.

- **Gained:** Simplicity. A vendor or buyer knows the cost before they start.
- **Lost:** Consolidated multi-order routing that could cut per-order delivery cost. Route optimization is flagged as a future capability, not a launch feature.

## 7. Frontend-Only Stack — No Backend, No Database

The entire product is vanilla HTML + CSS + JS served as a static site.

- **Gained:** Runs on any phone browser, loads fast on 3G, deployable on Netlify with zero ops. A vendor's ₹8,000 Android phone is a first-class device.
- **Lost:** Persistent shared state, real multi-user concurrency, seller analytics. Any production launch needs at minimum a lightweight API and database layer.

---

## Summary Matrix

| Trade-off | What we kept | What we deferred |
|---|---|---|
| Auth | Zero-friction demo entry | Secure phone OTP |
| Pricing | Seller-controlled, exact | Buyer-side price guidance |
| Units | Native market units | Normalized comparison |
| Coordination | Working multi-seller cart | Real seller notifications |
| AI matching | Transparent local catalog | Image recognition / LLM |
| Delivery | Flat fee, single window | Route-optimized pricing |
| Stack | Static, fast, offline-ready | Backend, database, analytics |

> [!TIP]
> Each "deferred" column item is a natural Phase 2 feature — and each one can be added **without breaking the trust model** established in Phase 1.
