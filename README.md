# CampusLoop

**CampusLoop** is a campus-friendly notes and book exchange app. Students can browse study resources, publish listings, save resources locally, and use an AI reviewer to get feedback on note clarity and structure.

## Features in this MVP

- Browse and search study notes and book exchange listings
- Add new resource listings
- Save/unsave resources
- Local persistence using `localStorage`
- Basic PWA service worker for caching the app shell
- Sarvam AI note-review endpoint (API key stays on the backend)
- Demo review fallback if no Sarvam API key is configured

## Tech stack

- React + Vite
- Node.js + Express
- Sarvam AI API
- Browser localStorage and service worker

## Run locally

Requires Node.js 18 or newer.

1. Download/clone this repository.
2. Open a terminal in the project folder.
3. Install dependencies:

   ```bash
   npm install
   ```

4. Create your local environment file by copying `.env.example` to `.env`.
5. Add your Sarvam API key to `.env`:

   ```env
   SARVAM_API_KEY=your_real_key_here
   PORT=3001
   ```

6. Start frontend and backend:

   ```bash
   npm run dev
   ```

7. Open `http://localhost:5173`.

Without a key, the reviewer uses a clearly labelled demo response. For real AI review, obtain an API key from Sarvam's official developer platform and confirm the current endpoint, model name, and request format in its documentation.

## GitHub security

- Never commit `.env` or paste an API key into frontend code.
- `.env` is included in `.gitignore`.
- `.env.example` is safe to commit because it contains only a placeholder.
- If a real API key is accidentally published, revoke/rotate it immediately.

## Current limitations / next steps

This is a buildathon MVP, not a production marketplace. Listings are stored in the browser on the current device and are not shared across users. To support a real campus community, add a hosted database/authentication (for example Supabase), file uploads, moderation, and contact flows. Offline support currently focuses on cached app assets and locally saved listings.

UPI/NPCI payments are not implemented. Real payment collection requires an appropriate payment provider and onboarding; do not simulate a successful payment or store payment credentials in this app.

## Suggested buildathon demo

1. Browse notes and books.
2. Search for a subject.
3. Save a resource and refresh to show it persists.
4. Add a resource.
5. Open **AI note review** and paste a short sample.
6. Explain that the API key is protected on the Express backend.
