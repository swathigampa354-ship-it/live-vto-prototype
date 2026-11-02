# Build Plan — Live Virtual Try-On (Shirt on Body)

**Goal:** Render the user's uploaded shirt live on their body through the camera ("live cloths changed").

## Tech stack (from chat plan + this build)
- Web app: **Next.js + React** (recommended for production)
- Camera: **getUserMedia / WebRTC**
- Body tracking: **MediaPipe Pose Landmarker** (this prototype)
- Hand tracking: **MediaPipe Hand Landmarker** (rings/jewellery)
- Face tracking: **MediaPipe Face Landmarker** (hairstyles)
- 3D rendering: **Three.js + react-three-fiber**
- AI try-on: **Perfect Corp YouCam API** (photorealistic)
- Backend: **Node.js**
- Database: **Supabase**

## Repo foundations (don't build tracking from scratch)
- https://github.com/google-ai-edge/mediapipe-samples-web
- https://github.com/JahnaviCheedella/jewellery-ar-try-on
- https://github.com/TechAngelX/softwear
- https://github.com/revatikhopkar-git/salon-hairglow-app
- https://github.com/dhritisxn/VTO-try-on

## Build phases

### Phase 1 — MVP (1 day): what's in /home/user/vto-prototype/index.html
- Selfie camera + MediaPipe Pose tracking
- Live shirt image render on torso, follows shoulders/hips
- Snapshot capture
- Record demo video → submit to Devpost hackathon

### Phase 2 — Full prototype (3–5 days)
- Next.js + Tailwind frontend
- Transparent PNG cutout of the shirt (no background)
- Three.js 3D garment draped on torso via Pose Landmarker
- YouCam API integration for photorealistic AI try-on (you supply API key)
- Supabase: user accounts, saved looks, garment catalogue

### Phase 3 — Production (3–6 weeks)
- Backend API, payments, inventory/catalogue CMS
- Native iOS/Android (camera + ARKit/ARCore)
- QA, accessibility, analytics

## Hackathon deadline (today)
Devpost: **Nov 2, 2026, 11:45am EST** ≈ **10:15 PM IST tonight** (~16 hours left).

**Ship Phase 1 today**, record a 1–3 minute demo, upload to YouTube, submit on Devpost before the deadline.

## Immediate next step
Prototype is ready. Push to GitHub, test the live render, then decide: Next.js conversion, transparent cutout + Three.js, or YouCam API wiring.