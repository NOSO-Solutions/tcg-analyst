# TCG Analyst

> AI-powered Pokémon TCG collection and meta advisor for TCG Live and physical play

![Status](https://img.shields.io/badge/status-in%20development-yellow)
![License](https://img.shields.io/badge/license-MIT-blue)
![Format](https://img.shields.io/badge/format-Standard%20%7C%20Expanded-green)

---

## What Is TCG Analyst?

TCG Analyst is an AI-powered strategy tool for Pokémon TCG players who want to do more than copy the top meta decks. It combines your personal card collection with live metagame data to help you make smarter decisions — what to build, what to craft, what to play, and how to beat what everyone else is running.

Most deck-building tools tell you what the best decks are. TCG Analyst tells you **what the best deck is for *you*, right now, with what you actually own.**

---

## Who Is It For?

- Players on **Pokémon TCG Live** who want to spend Trade Credits wisely
- **Physical players** who want to know what they can build from their collection before buying cards
- Competitive players who want to **understand and counter the meta**, not just copy it
- Anyone who wants to build something **outside the meta** that can still compete

---

## Features

### Phase 1 — TCG Live Core *(current build)*
- [ ] Paste your TCG Live deck exports to build your working collection
- [ ] Manual card search and collection entry
- [ ] AI advisor: suggests decks from cards you own
- [ ] Meta awareness: knows the current top decks and why they win
- [ ] Counter-strategy mode: builds against the meta, not with it
- [ ] Craft priority queue: tells you what to craft next and why
- [ ] Format legality checker (Standard — Regulation Marks H, I, J)
- [ ] W/L tracker: log games and spot patterns over time

### Phase 2 — Physical Mode *(roadmap)*
- [ ] Physical vs. TCG Live mode toggle
- [ ] Energy cards treated as a real resource (not free like in Live)
- [ ] Dollar cost instead of Trade Credits
- [ ] Shopping list output: here's what to buy and what it costs

### Phase 3 — Expanded Format *(roadmap)*
- [ ] Full Expanded card pool support
- [ ] Cross-format analysis: cards weak in Standard but strong in Expanded
- [ ] Expanded meta context and counter-strategy

### Phase 4 — Card Scanner *(roadmap)*
- [ ] Mobile camera card recognition
- [ ] Bulk photo mode: scan multiple cards at once
- [ ] Automatic collection building from physical cards

### Phase 5 — Third-Party Import *(roadmap)*
- [ ] Import from pkmn.gg collection exports
- [ ] Import from Limitless TCG format
- [ ] One-paste full collection sync

---

## Why TCG Analyst Is Different

| Feature | TCG Analyst | Limitless TCG | pkmn.gg | TCG Live |
|---|---|---|---|---|
| AI strategy advice | ✅ | ❌ | ❌ | ❌ |
| Knows your collection | ✅ | ❌ | ✅ | ✅ |
| Counter-meta builds | ✅ | ❌ | ❌ | ❌ |
| Craft priority guidance | ✅ | ❌ | ❌ | ❌ |
| Physical + Live modes | ✅ | ❌ | Partial | ❌ |
| Card scanner (roadmap) | ✅ | ❌ | ❌ | ❌ |
| Free & open source | ✅ | ❌ | ❌ | ❌ |

---

## Tech Stack

| Layer | Technology | Purpose |
|---|---|---|
| Frontend | React (Vite) | User interface |
| Backend | Node.js + Express | API layer, keeps keys secure |
| AI — Primary | Anthropic Claude API | Strategy analysis and advice |
| AI — Alternative | AWS Bedrock (Nova Pro) | Cost-efficient alternative (~4x cheaper) |
| Card Data | PokémonTCG.io API | Card search, images, legality |
| Styling | Tailwind CSS | UI design |
| Hosting | TBD (Vercel / Railway) | Deployment |

### AI Provider Abstraction

TCG Analyst is built with a swappable AI backend. Set your provider in `.env`:

```env
AI_PROVIDER=claude        # Use Anthropic Claude (default)
AI_PROVIDER=bedrock       # Use AWS Bedrock Nova Pro
```

This architecture decision is documented in [`docs/architecture.md`](docs/architecture.md).

---

## Getting Started

### Prerequisites
- Node.js v18 or higher
- An Anthropic API key **or** AWS credentials with Bedrock access

### Installation

```bash
# Clone the repository
git clone https://github.com/NOSO-Solutions/tcg-analyst.git
cd tcg-analyst

# Install dependencies
npm install

# Set up environment variables
cp .env.example .env
# Add your API keys to .env

# Start the development server
npm run dev
```

The app will be running at `http://localhost:5173`

---

## Project Structure

```
tcg-analyst/
├── frontend/          # React app
│   ├── src/
│   │   ├── components/    # UI components
│   │   ├── pages/         # App pages/views
│   │   └── hooks/         # Custom React hooks
├── backend/           # Node.js + Express API
│   ├── routes/
│   │   ├── cards.js       # PokémonTCG API proxy
│   │   └── analyze.js     # AI strategy endpoint
│   └── providers/
│       ├── claude.js      # Anthropic Claude integration
│       └── bedrock.js     # AWS Bedrock Nova integration
├── docs/
│   └── architecture.md    # Technical decisions and tradeoffs
└── .env.example       # Environment variable template
```

---

## Roadmap

- [x] Project scaffolding and architecture
- [ ] Phase 1: TCG Live core (collection input + AI advisor)
- [ ] Phase 2: Physical mode
- [ ] Phase 3: Expanded format support
- [ ] Phase 4: Card scanner (mobile)
- [ ] Phase 5: Third-party collection import

---

## Contributing

TCG Analyst is open source and welcomes contributions. If you play Pokémon TCG and want to help build something the community actually needs:

1. Fork the repo
2. Create a feature branch: `git checkout -b feature/your-feature-name`
3. Commit your changes: `git commit -m 'Add some feature'`
4. Push to the branch: `git push origin feature/your-feature-name`
5. Open a Pull Request

---

## License

MIT License — free to use, fork, and build on. See [`LICENSE`](LICENSE) for details.

---

## About

Built by [NOSO Solutions](https://github.com/NOSO-Solutions) — a solo developer learning in public.

*TCG Analyst is an independent community tool and is not affiliated with or endorsed by The Pokémon Company International.*

---

*If this tool helps your game, leave a ⭐ on the repo.*
