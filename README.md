# Live VTO — Shirt on Body (Pose Tracking)

A browser-based **live virtual try-on** that renders your uploaded t-shirt / polo shirt on a person's torso in real time through the camera. Built for the **YouCam API Skin AI & eCommerce VTO Hackathon**.

## What it does
1. **Camera on** — user grants camera permission, sees themselves live (selfie mode).
2. **Pose tracking** — MediaPipe Pose Landmarker runs in-browser (WASM) and detects 33 body landmarks.
3. **Live shirt render** — the uploaded shirt image (`assets/shirt.png`) is scaled, positioned, and rotated to follow the person's shoulders and torso as they move.

## Files
| File | Purpose |
|------|---------|
| `index.html` | Standalone demo: camera + MediaPipe Pose + live shirt render (no install) |
| `assets/shirt.png` | Your uploaded striped polo shirt asset |
| `README.md` | This file |
| `PLAN.md` | Build phases, stack, timeline |

## Tech used (prototype)
- **Camera**: `getUserMedia` (user-facing / selfie cam)
- **Body tracking**: MediaPipe Pose Landmarker (33 pose landmarks, in-browser WASM)
- **Live render**: HTML5 Canvas `drawImage`, positioned from shoulder (11/12) and hip (23/24) landmarks
- **Asset**: `assets/shirt.png` (your uploaded shirt)
- **Packaging**: none — static HTML/JS, works on any static host

## How to run
1. Serve the folder over HTTP (camera + ES modules require `http://`/`https://`, not `file://`):
   ```bash
   cd vto-prototype
   npx serve .
   # or
   python3 -m http.server 8080
   ```
2. Open `http://localhost:8080`.
3. Allow camera access → click **Start Camera**.
4. Stand facing the camera; the shirt renders on your torso and tracks your movement.
5. Click **Capture** to download a snapshot.

> MediaPipe loads a model from Google storage on first load — allow 5–15 seconds depending on connection.

## How the shirt is placed
Using MediaPipe Pose landmarks:
- **Shoulders** (landmarks 11 & 12) → set shirt width and rotation angle
- **Hips** (landmarks 23 & 24) → set shirt length
- The image is aspect-corrected (not stretched) and centered on the torso, following shoulder tilt as the person moves.

## From prototype to hackathon submission (YouCam API)
To make this a real, prize-worthy entry per Devpost requirements:

1. **Add YouCam API** (Perfect Corp) — photorealistic AI try-on:
   - Sign up at `https://yce.perfectcorp.com/ai-api` (India: `https://yce.makeupar.com/ai-api`)
   - Redeem your free 1,000 API units (code emailed after Devpost registration)
   - Replace the procedural shirt overlay with YouCam Apparel VTO API calls
2. **Use a transparent cutout** of the shirt (PNG with alpha) instead of the full image, so the background doesn't show
3. **Add Three.js + GLB models** for 3D garments that wrap the body properly
4. **Record a 1–3 minute demo video** and upload to YouTube (required for submission)
5. **Submit on Devpost** with: public repo URL, text description, screenshots, demo-video link

## Timeline (honest estimates)

| Scope | What's included | Est. time |
|-------|----------------|-----------|
| **MVP / hackathon-ready** | Camera + pose tracking + shirt overlay + snapshot | **~1 day** (ship tonight) |
| **Full prototype** | Transparent cutouts, Three.js 3D garments, YouCam AI, Supabase gallery | **3–5 days** |
| **Production app** | Backend, catalogue, payments, iOS/Android | **3–6 weeks** |

## Hackathon urgency
The Devpost page shows the **YouCam API VTO Hackathon deadline is today — Nov 2, 2026, 11:45am EST (~10:15 PM IST tonight)**, ~16 hours left. Ship the MVP today, record the demo video, and submit before the deadline.

## Licence note
Before reusing any GitHub repo code commercially (MediaPipe samples, Softwear, Salon Hairglow, etc.), check each repo's licence. This prototype is original code written for you.