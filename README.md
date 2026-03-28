<div align="center">

# ✦ Persona Synthesis

### A unified personality analysis app

**Astrology Birth Chart** · **MBTI** · **Enneagram** · **Big Five (OCEAN)**

[![SvelteKit](https://img.shields.io/badge/SvelteKit-5-FF3E00?style=flat-square&logo=svelte&logoColor=white)](https://kit.svelte.dev)
[![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-v4-06B6D4?style=flat-square&logo=tailwindcss&logoColor=white)](https://tailwindcss.com)
[![Supabase](https://img.shields.io/badge/Supabase-Cloud_Sync-3FCF8E?style=flat-square&logo=supabase&logoColor=white)](https://supabase.com)
[![License](https://img.shields.io/badge/License-MIT-A78BFA?style=flat-square)](LICENSE)
[![PRs Welcome](https://img.shields.io/badge/PRs-Welcome-FF6B6B?style=flat-square)](CONTRIBUTING.md)

*Discover who you are through four powerful personality frameworks — individually or as one merged profile.*

[**Live Demo**](https://persona-synthesis.vercel.app) · [**Documentation**](docs/) · [**Report Bug**](../../issues/new?template=bug_report.md) · [**Request Feature**](../../issues/new?template=feature_request.md)

---

</div>

<br>

## 🌌 What is Persona Synthesis?

Persona Synthesis brings together **four of the most popular personality frameworks** into a single, beautifully designed app. Take the tests (or enter your known types), explore individual results, and generate a **unified personality narrative** that synthesizes insights across all systems.

<br>

<div align="center">

| Framework | What It Reveals | Input Options |
|:---------:|:----------------|:--------------|
| ☉ **Birth Chart** | Celestial blueprint at the moment of your birth | Auto-calculate via API *or* manual Big Three entry |
| ◈ **MBTI** | Cognitive preferences across 4 dichotomies | 48-question test *or* select your known type |
| ⬡ **Enneagram** | Core motivations, fears, and growth paths | 54/108-question test *or* select type + wing |
| ◐ **Big Five** | Scientific personality dimensions (OCEAN) | 50/120-item IPIP-NEO *or* set dimension sliders |

</div>

<br>

## ✨ Key Features

### 🧪 Four Personality Frameworks
- **Astrology Birth Chart** — Full natal chart with planet positions, houses, aspects, elemental/modal balance. Powered by AstrologyAPI with OpenCage geocoding.
- **MBTI (Myers-Briggs)** — 48-item forced-choice questionnaire based on the Open Extended Jungian Type Scales with cognitive function stack.
- **Enneagram** — 54-item quick mode or 108-item deep mode. Determines type, wing, growth/stress directions.
- **Big Five (OCEAN)** — Scientifically validated IPIP-NEO (50 or 120 items) with domain and facet-level scoring.

### 🔀 Take Tests OR Select Known Types
Every framework offers a **"I know my type"** shortcut:
- MBTI → Pick from 16 types
- Big Five → Adjust five OCEAN dimension sliders (0–100)
- Enneagram → Select type (1–9), wing, and instinctual variant
- Birth Chart → Enter Sun, Moon, Rising signs manually

### 🧬 Unified Personality Synthesis
Generate a **merged personality narrative** powered by AI (Claude API) that:
- Finds **convergences** across systems (where frameworks agree)
- Identifies **tensions** (where frameworks reveal complexity)
- Produces insights on core identity, strengths, challenges, communication style, relationships, and career fit

### 💾 Local-First with Optional Cloud Sync
- **Client-side by default** — All data stored in IndexedDB, works offline
- **Optional Supabase cloud** — Sign in to sync across devices
- **Privacy-first** — Data never leaves your device unless you choose to sync

### 🎨 Sleek Minimalistic UI
- Dark-mode-first design inspired by Co-Star and The Pattern
- Smooth card transitions and micro-animations
- Radar/spider charts for Big Five, SVG birth chart wheel
- Responsive mobile-first layout with bottom navigation
- Light mode available via settings toggle

<br>

## 🛠 Tech Stack

| Layer | Technology | Why |
|:------|:-----------|:----|
| **Framework** | SvelteKit 2 + Svelte 5 (Runes) | Compiled reactivity, tiny bundles, built-in transitions |
| **Styling** | Tailwind CSS v4 + shadcn-svelte | Utility-first with beautiful accessible components |
| **State** | Svelte 5 `$state` runes + XState | Elegant reactive state + robust test flow machines |
| **Local DB** | IndexedDB via `idb` | Structured offline storage with sync queue |
| **Cloud** | Supabase (Postgres + Auth + Edge Functions) | Open-source BaaS with generous free tier |
| **Astrology** | AstrologyAPI + OpenCage Geocoding | Accurate natal chart calculation + location search |
| **Big Five** | `@bigfive-org/questions` + `@bigfive-org/score` | Validated IPIP-NEO items in 26 languages |
| **AI Synthesis** | Anthropic Claude API (via Edge Functions) | Nuanced personality narrative generation |
| **Charts** | Chart.js + Custom SVG | Radar charts for OCEAN, SVG wheel for birth chart |
| **Deployment** | Vercel / Netlify / Cloudflare Pages | Edge-first, instant deploys |

<br>

## 📦 Quick Start

### Prerequisites
- **Node.js** 20+ and **pnpm** 9+
- **API Keys** (optional — app works with manual entry without keys):
  - [AstrologyAPI](https://astrologyapi.com) — birth chart calculation
  - [OpenCage](https://opencagedata.com/api) — location geocoding (2,500 free/day)
  - [Anthropic Claude](https://console.anthropic.com) — AI personality synthesis
  - [Supabase](https://supabase.com) — optional cloud sync

### Installation

```bash
# Clone the repository
git clone https://github.com/yourusername/persona-synthesis.git
cd persona-synthesis

# Install dependencies
pnpm install

# Copy environment variables
cp .env.example .env.local

# Start development server
pnpm dev
```

### Environment Variables

```env
# .env.local

# Astrology API (optional)
VITE_ASTRO_USER_ID=your_user_id
VITE_ASTRO_API_KEY=your_api_key

# OpenCage Geocoding (optional)
VITE_OPENCAGE_API_KEY=your_api_key

# Supabase (optional)
VITE_SUPABASE_URL=https://your-project.supabase.co
VITE_SUPABASE_ANON_KEY=your_anon_key

# Anthropic Claude (server-side only)
ANTHROPIC_API_KEY=your_api_key
```

Open [http://localhost:5173](http://localhost:5173) and start exploring! 🚀

<br>

## 📁 Project Structure

```
persona-synthesis/
├── src/
│   ├── lib/
│   │   ├── components/
│   │   │   ├── layout/          # NavBar, BottomNav, Shell
│   │   │   ├── tests/           # QuestionFlow, TestCard, ManualEntry
│   │   │   ├── charts/          # BirthChartWheel, RadarChart, TypeBadge
│   │   │   ├── profile/         # ProfileCard, SynthesisView, InsightCard
│   │   │   ├── shared/          # AnimatedCounter, GradientText
│   │   │   └── ui/              # shadcn-svelte components
│   │   ├── data/                # Cognitive stacks, Enneagram descriptions
│   │   ├── db/                  # IndexedDB layer
│   │   ├── machines/            # XState test flow state machines
│   │   ├── services/            # API integrations
│   │   ├── stores/              # Svelte 5 rune stores
│   │   ├── tests/               # Scoring algorithms
│   │   ├── types/               # TypeScript schemas
│   │   └── utils/               # Helpers
│   └── routes/
│       ├── +layout.svelte       # App shell
│       ├── +page.svelte         # Home / dashboard
│       ├── tests/               # Test hub + 4 test routes
│       ├── profile/             # Profile + synthesis
│       ├── chart/               # Birth chart explorer
│       └── settings/            # Theme, sync, export
├── static/                      # Fonts, icons, OG images
├── supabase/                    # Migrations + Edge Functions
├── .env.example
├── svelte.config.js
├── package.json
└── README.md
```

<br>

## 🗺 Roadmap

- [x] Project architecture & data models
- [x] TypeScript type system for all 4 frameworks
- [x] IndexedDB local storage with sync queue
- [x] XState test flow state machines
- [x] MBTI 48-item test with scoring
- [x] Big Five IPIP-NEO integration (50 & 120 items)
- [x] Enneagram 54/108-item test with wing determination
- [x] AstrologyAPI + OpenCage integration
- [x] Manual entry flows for all frameworks
- [x] Sleek dark-mode UI with shadcn-svelte
- [ ] Birth chart SVG wheel renderer
- [ ] Radar chart visualization for Big Five
- [ ] Enneagram symbol with type highlighting
- [ ] AI-powered personality synthesis (Claude)
- [ ] Supabase cloud sync with auth
- [ ] PWA support (offline, installable)
- [ ] Profile sharing & comparison
- [ ] PDF/image export
- [ ] Relationship compatibility analysis
- [ ] Multi-language support
- [ ] Cognitive functions deep-dive
- [ ] Instinctual variant sub-test

<br>

## 🤝 Contributing

Contributions are greatly appreciated!

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/amazing-feature`)
3. Commit your Changes (`git commit -m 'Add amazing feature'`)
4. Push to the Branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

See [CONTRIBUTING.md](CONTRIBUTING.md) for detailed guidelines.

<br>

## 📄 License

Distributed under the **MIT License**. See [LICENSE](LICENSE) for details.

**Questionnaire Licenses:**
- IPIP-NEO items — **public domain** ([ipip.ori.org](https://ipip.ori.org))
- OEJTS-inspired MBTI items — **open license**
- Enneagram questions — adapted from Apache 2.0 sources

<br>

## 🙏 Acknowledgments

- [IPIP](https://ipip.ori.org) — International Personality Item Pool
- [bigfive-web](https://github.com/rubynor/bigfive-web) — Open-source Big Five
- [AstrologyAPI](https://astrologyapi.com) — Natal chart engine
- [OpenCage](https://opencagedata.com) — Geocoding API
- [shadcn-svelte](https://www.shadcn-svelte.com) — UI components
- [Anthropic Claude](https://anthropic.com) — AI synthesis

---

<div align="center">

**Built with ✦ by the Persona Synthesis community**

[⬆ Back to Top](#-persona-synthesis)

</div>

