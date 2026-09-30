# LeadLeak Calculator

A 60-second, single-page web prototype for Indian local businesses (clinics, hotels, real estate) that estimates how much money is lost to missed/unanswered calls — and how much a 24/7 AI answering agent could recover.

## How to run

No build step, no dependencies. Either:

1. **Double-click** `index.html` — it works directly from `file://`
2. Or serve it locally:
   ```bash
   cd ~/workspace/inventions/lead-leak-calculator && python3 -m http.server 8000
   ```
   then open http://localhost:8000 in a browser.

## Demo steps (60 seconds)

1. Pick a **vertical tab**: Clinic, Hotel, or Real Estate — each loads sensible preset numbers.
2. Drag the **Missed calls per day** slider (or type a number). Watch the headline leak amount re-calculate live with an animated count-up.
3. Adjust **average deal value (₹)**, **close rate %**, and **working days/month** to match the business.
4. Read the **before/after panel** (currently leaking vs. with 24/7 AI answering, assuming 80% of missed calls captured), then hit **Copy summary** on the result card — screenshot it and share on WhatsApp.

## What's real and what isn't

**Real / computed client-side:**
- All the math. The formula is simply:
  `missed calls/day × avg deal value × close rate × working days/month`
- Number formatting uses Indian numbering (`toLocaleString('en-IN')`) with lakh/crore wording.

**Assumptions, not data:**
- The tab **presets** (missed calls, deal values, close rates) are rough guesses to make the demo feel real — they are not measured from any actual business.
- The **80% capture rate** for the AI agent is an illustrative assumption, stated on the page. Real capture rates vary.
- The results are estimates based on *your* inputs. They are not a promise of revenue.

**Privacy:**
- No external CDNs, no ES modules, no `fetch` calls, no API keys.
- No network calls at all — nothing leaves the browser. The clipboard copy uses the local Clipboard API only.

## Files

- `index.html` — the whole app (inline CSS + JS)
- `README.md` — this file

*Demo prototype by VisionQuantech.*
