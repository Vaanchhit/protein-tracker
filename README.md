# Protein Price Atlas

**Every protein powder sold on Amazon India, compared on one fair number: what a 36 g scoop actually costs.**

Brands print different serving sizes (25 g, 33 g, 45 g…), list different pack sizes and run constant discounts, so the sticker price tells you very little. This page rescales all **949 listings from 240 brands** to a standard 36 g scoop. You can see at a glance what is cheap, what is good value and what looks too good to be true.

Prices as of 20 Oct 2026.

---

## Features

### Browse and compare
- **Table view**: sort every listing by price, ₹ per 36 g, ₹ per kg, protein per scoop, protein per ₹100, BCAA, discount or label transparency.
- **Brands view**: open any brand to see each product line with its flavours, ingredients and every pack size.
- **Compare view**: put up to 4 tubs side by side. A green dot marks the winner in each row.
- **Best lifts**: the cheapest scoop and the best value pick in each protein family (whey, plant, yeast, blends, casein/egg).
- **Filters**: protein type, brand, pack size, max ₹ per scoop, min protein per scoop, "protein stated", "BCAA stated", outliers, lab-test claims and red flags.

### Start with a goal
One-tap presets for people who know what they want but not the jargon:

| Goal | What it shows |
|---|---|
| Budget gains | Most protein per ₹100, no red flags |
| Lean & cutting | Isolates and hydrolysates, most protein per scoop |
| Easy on the stomach | Low-lactose isolates, plant, yeast and egg |
| Vegan | Plant and yeast proteins only |
| First tub | Flavoured whey, about 1 kg, clear label, no red flags |
| Bedtime | Slow-digesting casein and casein blends |
| Lab-tested | Cites a third-party lab test, no red flags |
| Try it first | Packs under 600 g, cheapest per scoop |

### Trust and quality signals
Every listing is checked against simple rules applied to its own title and ingredients:

- 🟢 **Lab-test claim**: the listing cites a third-party test (Trustified, Labdoor, Informed Choice/Sport or similar). This is the seller's claim and is not verified here.
- 🔴 **Too cheap?**: a dairy protein giving over 60 g of protein per ₹100, far above the rest of the market.
- 🔴 **Added aminos**: free glycine, taurine, glutamine or arginine in the ingredients, a sign of possible "amino spiking".
- 🔴 **Protein % high**: the label claims over 92% protein per serving.
- 🔴 **Unbranded**: no brand stands behind the listing.
- **Label dots ●●●○**: how many of protein, serving size, BCAA and ingredients the listing states.

Red flags are prompts to check reviews or a lab report, not verdicts.

### Spotter: ask in plain words
A built-in chatbot that matches keywords in your question. Try:

- "cheapest chocolate whey isolate"
- "best value vegan protein under ₹50 a scoop"
- "beginner whey 1kg"
- "compare MuscleBlaze vs Avvatar"
- "what does protein per ₹100 mean?"

It recognises brands (including nicknames like "mb" or "gold standard"), protein types, flavours, budgets, pack sizes, minimum protein, goals and trust terms. "Show all in the table" applies the same filters to the main table.

### Works on laptop and phone
- **Laptop**: the full table, with the product column pinned while you scroll sideways.
- **Phone**: each row becomes a card, the filters fold into one button, and a sort dropdown replaces the column headers.
- Light and dark mode follow your system setting.

---

## How the numbers work

| Metric | Formula |
|---|---|
| ₹ / 36 g | selling price ÷ net weight × 36 |
| Protein / 36 g | protein per label serving, scaled to 36 g |
| Protein per ₹100 | protein per 36 g ÷ ₹ per 36 g × 100. The clearest value-for-money figure; higher is better. |
| Label serving | the scoop size printed by the brand. Marked * when worked out from net weight ÷ servings. |

**Outliers** are sachets, trial packs and imports priced over ₹400 or under ₹15 per scoop. They are hidden by default.
**Protein type** is inferred from each listing's title and ingredients.
Prices change daily, so check the live listing before buying.

---

## Running it

The site is static: no build step, no backend, no dependencies.

```bash
git clone https://github.com/Vaanchhit/protein-tracker.git
cd protein-tracker
python3 -m http.server 8000
# open http://localhost:8000
```

Opening `index.html` directly in a browser also works. It can be hosted on any static host, such as GitHub Pages, Vercel or Netlify.

### Files

| File | What's in it |
|---|---|
| `index.html` | Page layout, styles and all app logic (table, brands, compare, goals, trust signals, Spotter) |
| `data.js` | `window.DATA`: brands → product lines → variants (flavour, size, price, MRP, protein, scoop, BCAA, link) |
| `images.js` | `window.IMG`: product thumbnails embedded as base64, keyed by product ID |

---

## Disclaimer

This is an independent comparison tool. It is not affiliated with Amazon or any brand listed. The trust signals come from simple rules applied to listing text and are not lab results. Always check the product label and a recent lab report before buying a supplement.

---

Created with ♥ by [Vaanchhit](https://www.linkedin.com/in/vaanchhit-agarwal-549036296/)
