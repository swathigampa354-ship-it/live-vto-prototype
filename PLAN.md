# Build Plan — Live Virtual Try-On Product

**Goal:** A product that lets users change clothes / try on hairstyles & jewellery live on camera ("live cloths changed"), using any repo tech.

## Recommended stack (from our plan)
- Web app: **Next.js + React**
- Camera: **getUserMedia / WebRTC**
- Face tracking: **MediaPipe Face Landmarker**
- Hand tracking: **MediaPipe Hand Landmarker** (rings)
- Body tracking: **MediaPipe Pose Landmarker** (clothing on torso)
- 3D rendering: **Three.js + react-three-fiber**
- AI try-on: **Perfect Corp YouCam API** (photorealistic fashion/skin)
- Backend: **Node.js**
- Database: **Supabase**

## Repo foundations (don't build tracking from scratch)
- https://github.com/google-ai-edge/mediapipe-samples-web (face/hand/pose tracking)
- https://github.com/JahnaviCheedella/jewellery-ar-try-on (React + MediaPipe jewellery)
- https://github.com/TechAngelX/softwear (3D clothing, Three.js + MediaPipe)
- https://github.com/revatikhopkar-git/salon-hairglow-app (hairstyle previews)
- https://github.com/dhritisxn/VTO-try-on (3D rings, hand tracking)

## Build phases

### Phase 1 — MVP (1 day): what exists in /home/user/vto-prototype/index.html
- Selfie camera + MediaPipe face tracking
- Overlay try-on: earrings, necklace, hairstyle, top
- Colour picker + snapshot capture
- Record demo video → submit to Devpost hackathon

### Phase 2 — Full prototype (3–5 days)
- Next.js + Tailwind frontend
- Pose Landmarker + Three.js 3D garments (drape on torso)
- YouCam API integration for photorealistic AI try-on (you provide API key)
- Supabase: user accounts, saved looks, garment catalogue
- Polished UI, mobile-responsive

### Phase 3 — Production (3–6 weeks)
- Backend API, payments, inventory/catalogue CMS
- Native iOS/Android (camera + ARKit/ARCore)
- QA, accessibility, analytics

## Hackathon deadline (today)
Devpost: **Nov 2, 2026, 11:45am EST** ≈ **10:15 PM IST tonight** (~16 hours left per the page).

**Ship Phase 1 today**, record a 1–3 minute demo, upload to YouTube, and submit on Devpost before the deadline.

## Immediate next step
The standalone prototype is ready at `/home/user/vto-prototype/index.html`. Serve it and test. Then tell me which direction to take: Next.js conversion, Three.js 3D clothing, or YouCam API wiring.