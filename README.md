# Live VTO — Virtual Try-On Prototype

A browser-based **live virtual try-on** prototype: hairstyles, jewellery (earrings, necklaces), and tops on your live camera feed. Built for the **YouCam API Skin AI & eCommerce VTO Hackathon**.

## What's inside
- `index.html` — single-file standalone demo (MediaPipe Face Landmarker + Canvas). Opens directly in a browser — install nothing.
- `PLAN.md` — build plan, tech stack options, timeline, and hackathon submission checklist.

## Tech used (prototype)
- **Camera**: `getUserMedia` (user-facing / selfie cam)
- **Face tracking**: MediaPipe Face Landmarker (478 face landmarks, runs in-browser via WASM)
- **Rendering**: HTML5 Canvas (procedural overlays — no external asset files needed)
- **Packaging**: none — static HTML/JS, works on any host (Netlify, Vercel, GitHub Pages, Firebase Hosting)

## How to run
1. Serve the folder over HTTP (camera + ES modules require `http://` or `https://`, not `file://`):
   ```bash
   cd vto-prototype
   # option A
   npx serve .
   # option B
   python3 -m http.server 8080
   ```
2. Open `http://localhost:8080` (or the serve URL).
3. Allow camera access → pick a category → choose a colour.
4. Position your face in the frame; the item tracks in real time.
5. Click **Capture** to download a snapshot.

> Note: MediaPipe loads a ~model from Google storage on first load — allow 5–15 seconds depending on connection.

## What's drawn where (prototype heuristics)
| Item | Anchor | Placement logic |
|------|--------|-----------------|
| Earrings | cheek landmarks (234, 454) | Stud + dangling bead on each side |
| Necklace | cheek + chin (152) | Chain between cheeks, pendant at chin |
| Hairstyle | forehead (10) + face outline | Hair shape above head, fringe across brow |
| Top / Tee | chin + face width | Torso block scaled to face size, crew neckline |

## From prototype to hackathon submission (YouCam API)
To make this a real, prize-worthy entry per the Devpost requirements:

1. **Add YouCam API** (Perfect Corp) — photorealistic AI try-on:
   - Sign up at `https://yce.perfectcorp.com/ai-api` (India: `https://yce.makeupar.com/ai-api`)
   - Redeem your free 1,000 API units (code emailed after Devpost registration)
   - Replace procedural overlays with YouCam Apparel VTO / Skin AI API calls
2. **Swap canvas drawings for real assets** — PNG cutouts or Three.js GLB models (rings, necklaces, hair cards, garments)
3. **Add body tracking** — MediaPipe Pose Landmarker + Three.js for 3D clothing that follows the torso/arms
4. **Record a 1–3 minute demo video** and upload to YouTube/Vimeo (required for submission)
5. **Submit on Devpost** with: public repo URL, text description, screenshots, demo-video link

## Timeline (honest estimates)

| Scope | What's included | Est. time |
|-------|----------------|-----------|
| **MVP / hackathon-ready** | Camera + face tracking + 4 item categories + colour picker + snapshot + demo video | **~1 day** (can ship tonight before the 11:45am EST deadline) |
| **Full prototype** | Pose/body tracking, Three.js 3D assets, YouCam AI integration, Supabase gallery + auth, polished UI | **3–5 days** |
| **Production app** | Backend, product catalogue, payments, iOS/Android, QA | **3–6 weeks** |

## Hackathon urgency
The Devpost page shows **16 hours left** and a deadline of **Nov 2, 2026, 11:45am EST** (≈ **10:15 PM IST tonight**). If you want to enter, scope an MVP, finish it today, record the demo video, and submit before the deadline.

## Licence note
Before reusing any GitHub repo code commercially (MediaPipe samples, jewellery-AR, Softwear, Salon Hairglow, VTO-try-on), check each repo's licence. This prototype is original code written for you.

## Next steps I can do for you
1. Convert this into a Next.js + Tailwind app (recommended stack from our earlier plan).
2. Add MediaPipe Pose + Three.js for real 3D clothing.
3. Wire the YouCam API (you supply the API key).
4. Add Supabase backend + user gallery.

Want me to proceed with the Next.js version or the YouCam API integration next?