# Gudimalkapur Today

A frontend-first digital window into Hyderabad's Gudimalkapur wholesale flower market.

> See today's market. Compare real sellers. Order without the trip.

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
- Seller order progression: accept, ready, sent for delivery, completed
- Customer order timeline synchronized through localStorage across browser tabs
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
- Images are sourced from Wikimedia Commons and loaded remotely.
- Customization matching is local and deterministic in this frontend-only prototype. Connect a secure `/api/customize` endpoint before using a production LLM.
- Seller order actions are prototype coordination controls, not a real WhatsApp or delivery integration.

## Product Principle

**We do not digitize the people. We digitize the transaction around them.**

The physical market remains the source of supply, sellers remain independent, and buyers retain seller choice.
