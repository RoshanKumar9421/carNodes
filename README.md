# carNodes

**carNodes** is a modern, trusted used‑vehicle marketplace built on a Real‑World Asset (RWA) protocol. The front‑end provides an immersive 3‑D car carousel, a glass‑morphic navigation bar, and seamless authentication via Supabase. The UI is powered by React, Vite, and Tailwind CSS, with blockchain interactions through ethers.js and Alchemy.

---

## Table of Contents

- [Features](#features)
- [Tech Stack](#tech-stack)
- [Project Structure](#project-structure)
- [Setup & Development](#setup--development)
- [Build & Deployment](#build--deployment)
- [Asset Changes](#asset-changes)
- [Tailwind Customizations](#tailwind-customizations)
- [Contributing](#contributing)
- [License](#license)

---

## Features

- **3‑D CarouselOrbit** – CSS‑based rotating showcase of car silhouettes.
- **Glass‑morphic Navbar** – Responsive navigation with a custom brand logo (`car.svg`).
- **Supabase Authentication** – Secure sign‑in/out flow with JWT‑based anonymous key.
- **Blockchain Integration** – Connects to Sepolia via Alchemy and interacts with deployed contracts (Passport, Registry, Escrow, MockInR).
- **Responsive Layout** – Tailwind utilities ensure a fluid experience across mobile, tablet, and desktop.
- **Dark/Light Theme** – Configurable via Tailwind and CSS variables.

---

## Tech Stack

| Category | Technology |
|----------|------------|
| Front‑end | React 18, Vite, Tailwind CSS |
| UI Icons | Lucide‑React |
| Authentication | Supabase (URL & anon key configured via `.env` ) |
| Blockchain | ethers.js, Alchemy (Sepolia) |
| Smart Contracts | Solidity contracts deployed on Sepolia (Passport, Registry, Escrow, MockInR) |
| Build & Lint | Vite, oxlint |

---

## Project Structure

```
carNodes/
├─ frontend/                     # React/Vite front‑end
│   ├─ public/                    # Static assets (car.svg, index.html, …)
│   ├─ src/
│   │   ├─ components/            # UI components
│   │   │   ├─ Navbar.jsx
│   │   │   ├─ LoginModal.jsx
│   │   │   ├─ DashboardSidebar.jsx
│   │   │   ├─ CarouselOrbit.jsx
│   │   │   └─ …
│   │   ├─ pages/                # Page‑level components
│   │   ├─ hooks/                 # Custom React hooks
│   │   └─ index.css
│   ├─ tailwind.config.js        # Tailwind configuration (defaults restored)
│   ├─ vite.config.ts            # Vite configuration (environment variables)
│   └─ package.json              # Dependencies & scripts
├─ contracts/                    # Solidity contracts (outside repo scope)
└─ README.md                     # ← **This file**
```

---

## Setup & Development

### Prerequisites

- **Node.js** (v18 or later) – `node -v`
- **npm** (comes with Node) – `npm -v`
- **Git** – for version control

### Installation

```bash
# Clone the repository (if you haven't already)
git clone https://github.com/your‑org/carNodes.git
cd carNodes/frontend

# Install dependencies using a clean install
npm ci
```

### Environment Variables

Create a `.env` file in `frontend/` (or edit `frontend/.env.example`) with the following keys (values are already set in the repo for development):

```dotenv
VITE_USE_MOCK=false
VITE_SUPABASE_URL=https://afcdfdxihvhqrrksibkp.supabase.co
VITE_SUPABASE_ANON_KEY=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJzdXBhYmFzZSIsInJlZiI6ImFmY2RmZHhpaHZocXJya3NpYmtwIiwicm9sZSI6ImFub24iLCJpYXQiOjE3ODkyMTgxMjMsImV4cCI6MjEwNDc5NDEyM30.3fcvXfrVw2iOqDbTwqGpXkLolE-KK2P6NnUSwXNibWs
VITE_ALCHEMY_URL=https://eth-sepolia.g.alchemy.com/v2/alch_UmfNXLrC8t4Fz7wg8zIa1
VITE_IPFS_GATEWAY=https://gateway.pinata.cloud/ipfs/
VITE_PASSPORT_CONTRACT_ADDRESS=0xec5b401ECe64d130B6Cc83c4916137990009Eaf5
VITE_REGISTRY_CONTRACT_ADDRESS=0xD585f8daDdB3F438aCE2A5b4e86f47e11825fF30
VITE_ESCROW_CONTRACT_ADDRESS=0xB9d64e71bc01C8b09F19fF258dE21E0ebDb78EE2
VITE_MOCKINR_CONTRACT_ADDRESS=0x1aE2E1190f4e026f125111fA80882cCFE50EEC1C
```

> **Note** – The logo `car.svg` replaces the original `carnodes-logo.svg`. All components now reference `/car.svg`.

### Running the Development Server

```bash
npm run dev
```

Open `http://localhost:5173` in your browser. The app should load with the new logo and the carousel without the central `cN` emblem.

---

## Build & Deployment

```bash
# Create an optimized production build
npm run build
```

The build output is placed in `frontend/dist/`. Deploy the contents of `dist/` to any static‑hosting provider (e.g., Vercel, Netlify, Firebase Hosting). Ensure that the same environment variables are supplied at runtime (via Vite's `import.meta.env`).

---

## Asset Changes

- **Logo Replacement** – `carnodes-logo.svg` was removed from all UI components. A new `car.svg` (high‑resolution vector) now resides in `frontend/public/` and is referenced via `<img src="/car.svg">` in `Navbar.jsx`, `LoginModal.jsx`, and `DashboardSidebar.jsx`.
- **Carousel Center Emblem** – The decorative central "cN" badge and its "RWA NODE" label have been removed from `CarouselOrbit.jsx` to simplify the visual focus on surrounding cars.

---

## Tailwind Customizations

The previous Tailwind overrides that forced `borderRadius: 0px` and `boxShadow: none` were removed. The project now uses Tailwind’s default radius and shadow utilities, enabling modern UI styling (e.g., `rounded-lg`, `shadow-md`).

---

## Contributing

1. Fork the repository.
2. Create a feature branch (`git checkout -b feature/awesome‑feature`).
3. Install dependencies with `npm ci`.
4. Follow the linting conventions:
   ```bash
   npx oxlint src/**/*.jsx
   ```
5. Submit a pull request with a clear description of changes.

All contributions should adhere to the existing code style (Prettier + Tailwind class ordering) and pass the CI lint step.

---

## License

This project is licensed under the **MIT License** – see the `LICENSE` file for details. If a license is not present, please add one appropriate for your organization.

---

*Generated by Antigravity AI assistant.*

