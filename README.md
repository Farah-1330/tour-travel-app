# Northern Trails PK — Tour & Travel App

A responsive, static tour & travel site built with React + Vite, for the
"React project 0" assignment (component decomposition, props drilling, CSS in React).

Themed around guided treks across **northern Pakistan**: Hunza, Skardu,
Fairy Meadows, Naran-Kaghan, Neelum Valley, and Deosai. Prices shown in PKR (Rs).

## What's inside

**9 components**, all reusable and driven entirely by props (no hardcoded data inside any of them):

| Component      | Role                                                              |
|-----------------|-------------------------------------------------------------------|
| `Header`        | Sticky nav with a working mobile hamburger toggle                 |
| `Hero`          | Landing banner — stats passed down as props                      |
| `StatBadge`     | Tiny reusable stat chip, used 3x inside `Hero`                    |
| `FilterBar`     | Controlled region filter + live search, fully driven by props     |
| `TourList`      | Maps filtered tours → `TourCard`, drills `onSelect` down          |
| `TourCard`      | Reusable card for one tour, reused 6x                             |
| `TripModal`     | Day-by-day itinerary modal, opens/closes via lifted state         |
| `Testimonials`  | Trail-register quote grid                                         |
| `Footer`        | Site footer                                                       |

**Props drilling**: `App.jsx` owns all shared state (`activeRegion`, `searchTerm`,
`selectedTour`) and passes it — plus the setter callbacks — down through
`FilterBar`, `TourList` → `TourCard`, and `TripModal`. No component reaches
outside its own props.

**Interactivity**:
- Region filter chips (Hunza, Skardu, Fairy Meadows, Naran-Kaghan, Neelum Valley, Deosai) + live text search
- Tap/click a tour card → opens an itinerary modal with a day-by-day plan
- Modal closes on backdrop click, close button, or Escape key
- Mobile hamburger menu toggle
- Fully responsive: 3-column grid on desktop → 1 column on mobile

## Run it locally

```bash
npm install
npm run dev
```

Then open the local URL it prints (usually `http://localhost:5173`).

## Build for production

```bash
npm run build
npm run preview   # sanity-check the production build locally
```

This outputs a static site into `dist/` — that's what Vercel/Netlify will deploy.

## Submitting: push to GitHub + deploy

### 1. Push to GitHub
```bash
git init
git add .
git commit -m "Northern Trails PK — React tour & travel app"
git branch -M main
git remote add origin https://github.com/<your-username>/<repo-name>.git
git push -u origin main
```

### 2. Deploy (pick one)

**Vercel** (fastest):
1. Go to vercel.com → New Project → Import your GitHub repo.
2. Framework preset: Vite (auto-detected). Build command `npm run build`, output dir `dist`.
3. Click Deploy — you'll get a live URL like `your-repo.vercel.app`.

**Netlify**:
1. Go to app.netlify.com → Add new site → Import an existing project → pick the repo.
2. Build command: `npm run build`. Publish directory: `dist`.
3. Deploy — you'll get a URL like `your-repo.netlify.app`.

### 3. Submit
Paste the deployed URL + the GitHub repo link into the assignment's deliverable field.

## Notes on the acceptance criteria
- ✅ At least 5 reusable components — 9 provided, all prop-driven
- ✅ Props passed correctly through the component tree — see the drilling note above
- ✅ Responsive across mobile and desktop — grid collapses at 960px and 720px breakpoints, nav becomes a hamburger menu
