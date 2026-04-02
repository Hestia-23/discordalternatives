# discordalternatives.org

A neutral, filterable directory of Discord alternative platforms. No rankings, no reviews, no ads, no tracking. Browse listings and decide for yourself.

Every platform gets the same fields, the same layout, the same treatment. The data structure makes preferential treatment structurally impossible.

---

## Principles

- No rankings or scoring
- No editorial reviews or recommendations
- No voting or rating system
- No ads, affiliate links, or sponsorships
- No analytics, cookies, or tracking of any kind
- No platform manipulation
- Identical schema enforced across all listings

---

## Categories

Listings are organized into four categories. Each category uses the same schema and layout. The category determines where a listing appears on the site, not how it's treated.

| Category | What belongs here | Page |
|----------|-------------------|------|
| **Community Platforms** | Server/channel/role architecture intended as Discord replacements (e.g., Stoat, Fluxer, GameVox, Root) | Main gallery (default landing page) |
| **Voice-Focused** | Platforms primarily focused on voice communication without full community features (e.g., TeamSpeak, Mumble, Ventrilo) | Separate page within the directory |
| **Messaging Apps** | IM-first apps that appear in "Discord alternatives" searches but serve a different purpose (e.g., Signal, SimpleX, Telegram) | Separate page with brief explanation |
| **Enterprise / Workplace** | Team collaboration tools built for business use (e.g., Slack, Teams, Zulip, Rocket.Chat) | Separate page with brief explanation |

Community Platforms and Voice-Focused listings get the full schema, filter system, and gallery/list views. Messaging Apps and Enterprise/Workplace pages are simpler — a brief explanation of why they're categorized separately, plus a card per platform linking to the official website.

---

## Tech Stack

| Component | Choice |
|-----------|--------|
| Framework | Astro |
| Hosting | Cloudflare Pages |
| DNS/Registrar | Cloudflare |
| Data storage | JSON flat files (one per listing) |
| Screenshots | Committed to repo |
| Submissions | GitHub issue templates |
| Analytics | None |

---

## Data Schema

Every field below applies identically to every platform. Fields marked **Filter** power the gallery's filter system.

### Tri-State Values

Many fields use a standardized tri-state:

- **Available** — shipped and usable
- **In Development** — confirmed in progress, not yet shipped
- **Not Available** — the platform does not offer this

### Identity

| Field | Type | Notes |
|-------|------|-------|
| Platform name | Text | |
| Category | Community Platform / Voice-Focused / Messaging App / Enterprise | Determines which page the listing appears on |
| Tagline | Text | One sentence, max 120 characters |
| Website URL | URL | |
| Logo/icon | Image | High-res, not favicon |
| App screenshots | Image(s) | Up to 5 for product showcase |
| Verification screenshot | Image | Must display `discordalt-verify-[platform-name]` (submitted by owner, not displayed on site) |
| Owner/developer alias | Text | Internet alias for attribution |
| Description | Text | 2-3 sentences max |

### Platform Availability

| Field | Type | Filter |
|-------|------|--------|
| Windows | Tri-state | Yes |
| macOS | Tri-state | Yes |
| Linux | Tri-state | Yes |
| iOS | Tri-state | Yes |
| Android | Tri-state | Yes |
| Web | Tri-state | Yes |
| Xbox | Tri-state | Yes |
| PlayStation | Tri-state | Yes |

### Pricing

| Field | Type | Filter |
|-------|------|--------|
| Pricing model | Free / Freemium / Paid only / Donation-funded | Yes |
| Free tier available | Yes / No | Yes |
| Pricing URL | URL | No |
| Pricing notes | Text | Brief explanation of what costs money |

### Architecture & Trust

| Field | Type | Filter |
|-------|------|--------|
| Open source | Yes / No | Yes |
| License type | Text (e.g., AGPLv3, MIT, BSD-3) | Yes |
| Repository URL | URL | No |
| Self-hosting available | Yes / No | Yes |
| Federated | Yes / No | Yes |
| Centralized | Yes / No | Yes |
| Development stage | Stable / Beta / Alpha / Pre-launch | Yes |
| Funding model | Self-funded / VC-funded / Donation-funded / Corporate | Yes |
| Country/jurisdiction | Country name | Yes |

### Privacy & Security

| Field | Type | Filter |
|-------|------|--------|
| Voice E2EE | Tri-state | Yes |
| Text E2EE | Tri-state | Yes |
| Account signup requires email | Yes / No / Optional | Yes |
| Account signup requires phone | Yes / No | Yes |
| Account signup requires ID/verification | Yes / No | Yes |
| Anonymous signup available | Yes / No | Yes |
| Privacy policy URL | URL | No |
| Data collection notes | Text | Brief summary of what is/isn't collected |
| AI training on user data | Yes / No / Unknown | Yes |

### Voice Features

| Field | Type | Filter |
|-------|------|--------|
| Voice chat | Tri-state | Yes |
| Spatial audio | Tri-state | Yes |
| Noise suppression | Tri-state | Yes |
| Push-to-talk | Tri-state | Yes |
| Voice activation | Tri-state | Yes |
| Soundboard | Tri-state | Yes |
| Voice effects | Tri-state | Yes |
| DJ / music bot | Available / In Development / Not Available / Third-party | Yes |

### Video Features

| Field | Type | Filter |
|-------|------|--------|
| Video calls | Tri-state | Yes |
| Screen sharing | Tri-state | Yes |
| Max video resolution | Text (e.g., 1080p 30fps, 1440p 60fps) | No |
| Screen share includes audio | Yes / No | Yes |

### Text & Community Features

| Field | Type | Filter |
|-------|------|--------|
| Markdown support | Full / Partial / None | Yes |
| Tables in markdown | Yes / No | Yes |
| File uploads | Tri-state | Yes |
| Max file upload size | Text (e.g., 500 MB, 10 GB) | No |
| Forums / threads | Tri-state | Yes |
| Polls | Tri-state | Yes |
| Events / scheduling | Tri-state | Yes |
| Custom emoji | Tri-state | Yes |
| Stickers | Tri-state | Yes |
| Server discovery / directory | Tri-state | Yes |
| Discord server import | Tri-state | Yes |

### Moderation

| Field | Type | Filter |
|-------|------|--------|
| Roles and permissions | Tri-state | Yes |
| Per-channel permissions | Tri-state | Yes |
| AutoMod | Tri-state | Yes |
| Audit log | Tri-state | Yes |
| Raid protection | Tri-state | Yes |
| Ban with expiry | Tri-state | Yes |

### Bot & API Support

| Field | Type | Filter |
|-------|------|--------|
| Bot support | Tri-state | Yes |
| Public API | Tri-state | Yes |
| API documentation URL | URL | No |

### NSFW Policy

| Field | Type | Filter |
|-------|------|--------|
| NSFW content allowed | Yes / No / Age-gated | Yes |
| NSFW policy notes | Text | Brief explanation |

---

## Filter System

Users combine filters to narrow the gallery. Every field marked **Filter: Yes** above is filterable.

- **AND logic** — every active filter must match for a listing to appear
- **Multi-select** within categories (e.g., select Windows AND Linux to find platforms on both)
- **Toggle** for boolean fields (e.g., Self-hosting available: Yes)
- **Dropdown** for enum fields (e.g., Development stage: Beta)
- **Clear all** button resets to full gallery
- **URL-shareable** — filter state encoded in the URL for sharing filtered views

---

## UI

### Gallery View (Default)
- Card grid layout
- Each card shows: platform name, logo, primary screenshot, tagline, badges
- Card badges: Free/Freemium/Paid, Stable/Beta/Alpha, platform icons, Encrypted, Open Source
- Clicking a card opens the detail modal

### List View
- Compact row layout showing more listings at a glance
- Each row shows: platform name, logo, tagline, key badges
- Toggle between Gallery and List view; preference preserved in URL params

### Detail Modal
- Opens as a large overlay/pop-out over the gallery (not a separate page)
- All schema fields displayed in organized sections
- Screenshot gallery (up to 5 images)
- Direct link to platform website
- URL updates when modal opens so direct links to a listing work
- Back button or overlay click closes the modal, returns to gallery with scroll position preserved
- No comments, no reviews, no ratings

### Filter Bar
- Sticky sidebar or top bar with collapsible filter categories
- Active filter count visible
- Mobile: filter bar collapses to drawer/modal, card grid to single column

### Color Scheme
- Dark base theme
- Warm accent palette (anti-Discord branding — no blurple, no GameVox orange)
- Neutral, directory-appropriate aesthetic

---

## Data Population

All listings are pre-populated by the maintainer using accurate, factual, up-to-date information from public sources. Platform owners can submit corrections or request new listings — see [CONTRIBUTING.md](CONTRIBUTING.md).

---

## Project Structure

```
discordalternatives/
├── src/
│   ├── pages/            # Astro pages (index, voice-focused, messaging, enterprise)
│   ├── components/       # UI components (cards, filters, badges, detail modal)
│   ├── layouts/          # Page layouts
│   └── styles/           # Global styles, CSS variables
├── data/
│   └── listings/         # One JSON file per platform (category field determines page)
├── public/
│   └── screenshots/      # Platform screenshots (organized by platform slug)
├── .github/
│   └── ISSUE_TEMPLATE/   # Correction and new listing templates
├── astro.config.mjs
├── package.json
└── README.md
```

---

## Seed Data

All listings are populated by the maintainer from publicly available information. Initial platforms include:

**Community Platforms:** Fluxer, Stoat, Valour, Commet, Sable, Root, Osmium, Echoed, Kloak, GameVox (and others as identified)

**Voice-Focused:** TeamSpeak, Mumble, Ventrilo

**Messaging Apps:** Signal, SimpleX, Telegram (and others as identified)

**Enterprise / Workplace:** Slack, Teams, Zulip, Rocket.Chat (and others as identified)

Platform owners can submit corrections and updates through the GitHub issue templates.

---

## Development

```bash
# Install dependencies
npm install

# Start dev server
npm run dev

# Build for production
npm run build

# Preview production build
npm run preview
```

---

## Deployment

Cloudflare Pages builds from the `main` branch. Push to `main` triggers a production deploy.

---

## License

MIT
