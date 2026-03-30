# Ring OOS Orders Dashboard

An internal operations dashboard for tracking out-of-stock ring exchange orders at Ridge. Built as a single HTML file — no dependencies, no build step, opens directly in any browser.

## What it does

Displays 49 open OOS ring orders categorized into four actionable tabs:

| Tab | Description |
|-----|-------------|
| **Ready to place** | Primary SKU has stock on hand at FTS — place now |
| **Alt SKU** | Original SKU is OOS but an alt SKU can fulfill the order |
| **Inventory arriving** | Linked to PO IS27961 — stock on the way, ETA TBA |
| **Needs ops request** | No stock, no alt, no incoming PO — escalate to ops team |

The **Needs ops request** tab includes a color-coded **Days waiting** badge so aging orders are easy to spot at a glance:

- Gray — under 30 days
- Amber — over 30 days
- Red — over 90 days

## How to update

The order data lives directly in the `index.html` file inside the `const raw = [...]` array. Each row follows this format:

```
["date", "order#", "colorway", "style", "req. size", "SKU", "OOS in Shopify", on hand, "alt SKU", alt on hand, "can use alt", "arriving PO", "notes"]
```

To update:
1. Open `index.html` in any text editor
2. Edit the `raw` array
3. Save and re-upload to GitHub — the live page updates automatically within a minute or two

## Date logic

- Orders placed **January – March** are assumed to be from **2026**
- Orders placed **April – December** are assumed to be from **2025**

## Hosting

Hosted via **GitHub Pages**. Live at:

```
https://<your-username>.github.io/ring-oos-dashboard/
```

No login required — anyone with the link can view it.

---

*Ridge Personalization · Internal Ops Use · Last updated 3/29/2026*
