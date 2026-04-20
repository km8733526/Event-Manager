# 🛡️ TrueShield — Senior Safety & Health Solution

A modern, full-featured web application for senior safety and health management, built with React, TypeScript, Tailwind CSS, and Supabase.

## 📁 Project Structure

```
├── src/
│   ├── components/       # Reusable UI components (shadcn/ui)
│   ├── hooks/            # Custom React hooks
│   ├── lib/              # Utilities and helpers
│   └── main.tsx          # App entry point
├── index.html
├── vite.config.ts
├── tailwind.config.ts
├── tsconfig.json
└── package.json
```

## ✨ Tech Stack

| Layer | Technology |
|---|---|
| Framework | React 18 + TypeScript |
| Build Tool | Vite |
| Styling | Tailwind CSS + shadcn/ui |
| Backend / DB | Supabase |
| Forms | React Hook Form + Zod |
| Routing | React Router DOM v6 |
| Data Fetching | TanStack Query (React Query) |
| Charts | Recharts |
| Icons | Lucide React |

## 🚀 Getting Started

### Prerequisites

- Node.js 18+
- npm or bun

### Installation

```bash
git clone <your-repo-url>
cd trueshield
npm install
```

### Environment Variables

Create a `.env` file in the root and add your Supabase credentials:

```env
VITE_SUPABASE_URL=your_supabase_project_url
VITE_SUPABASE_ANON_KEY=your_supabase_anon_key
```

### Development

```bash
npm run dev
```

App runs at `http://localhost:8080`

### Build

```bash
npm run build        # Production build
npm run build:dev    # Development build
npm run preview      # Preview production build
```

### Lint

```bash
npm run lint
```

## 🎨 Design System

TrueShield uses a custom color palette built for accessibility and a clean medical feel:

| Token | Color | Usage |
|---|---|---|
| `trueshield.primary` | `#1E88E5` | Main blue — trust & reliability |
| `trueshield.secondary` | `#4CAF50` | Green — health & wellness |
| `trueshield.accent` | `#FF5722` | Orange/red — alerts & emergencies |
| `trueshield.warning` | `#FFA726` | Orange — warnings |
| `trueshield.error` | `#F44336` | Red — errors |
| `trueshield.success` | `#66BB6A` | Green — success states |

## 🧩 UI Components

shadcn/ui components are configured under `src/components/ui/` with the `slate` base color and CSS variables for theming. Add new components using:

```bash
npx shadcn@latest add <component-name>
```

## ⚠️ Notes

- Never commit your `.env` file — it's already in `.gitignore`
- Supabase credentials are required for backend features to work
- Dark mode is supported via the `next-themes` package
