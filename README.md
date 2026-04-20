# CampusPulse 🎓

An AI-powered event organiser platform built for campus communities. Create, discover, and manage events with intelligent assistance — complete with QR-based ticketing, location search, and a real-time backend.

---

## ✨ Features

- **AI Event Generation** — Generate event details automatically using Google Gemini AI via the `/api/generate-event` endpoint
- **Authentication** — Secure sign-in/sign-up flows powered by Clerk
- **Event Management** — Create and manage your own events with rich details (images, location, date, capacity)
- **Event Discovery** — Browse and explore events by location with a dedicated explore page
- **QR Code Ticketing** — Register for events and receive QR code tickets; scan tickets with the built-in QR scanner
- **Real-time Backend** — Live data sync powered by Convex (events, registrations, users, dashboard)
- **Onboarding Flow** — First-time user onboarding modal to personalise the experience
- **Dark/Light Theme** — Full theme support via `next-themes`
- **Responsive UI** — Built with Tailwind CSS v4 and shadcn/ui components

---

## 🛠 Tech Stack

| Layer | Technology |
|---|---|
| Framework | Next.js 16 (App Router) |
| Language | JavaScript (JSX) |
| Styling | Tailwind CSS v4, shadcn/ui (New York style) |
| Auth | Clerk |
| Database / Backend | Convex |
| AI | Google Gemini (`@google/generative-ai`) |
| Forms | React Hook Form + Zod |
| QR Codes | `react-qr-code` + `html5-qrcode` |
| Image Carousel | Embla Carousel |
| Date Handling | `date-fns`, `react-day-picker` |
| Icons | Lucide React |
| Notifications | Sonner |

---

## 📁 Project Structure

```
CampusPulse/
├── app/
│   ├── (auth)/                  # Auth routes (sign-in, sign-up)
│   ├── (main)/                  # Protected routes
│   │   ├── create-event/        # Event creation page
│   │   ├── my-events/           # User's events + [eventId] detail
│   │   └── my-tickets/          # User's registered tickets
│   ├── (public)/                # Public routes
│   │   ├── events/[slug]/       # Event detail + registration modal
│   │   └── explore/             # Browse/search events
│   ├── api/generate-event/      # AI event generation API route
│   ├── globals.css
│   └── layout.js
├── components/
│   ├── ui/                      # shadcn/ui primitives
│   ├── event-card.jsx
│   ├── header.jsx
│   ├── footer.jsx
│   ├── onboarding-modal.jsx
│   ├── search-location-bar.jsx
│   ├── unsplash-image-picker.jsx
│   ├── upgrade-modal.jsx
│   └── convex-client-provider.jsx
├── convex/                      # Convex backend
│   ├── schema.js                # Database schema
│   ├── events.js
│   ├── registrations.js
│   ├── users.js
│   ├── explore.js
│   ├── search.js
│   ├── dashboard.js
│   ├── auth.config.js
│   └── seed.js
├── hooks/
│   ├── use-convex-query.js
│   ├── use-onboarding.jsx
│   └── use-store-user.jsx
├── lib/
│   ├── data.js
│   ├── location-utils.js
│   └── utils.js
├── public/                      # Static assets
├── proxy.js                     # Clerk middleware (route protection)
└── package.json
```

---

## 🚀 Getting Started

### Prerequisites

- Node.js 18+
- A [Convex](https://convex.dev) account
- A [Clerk](https://clerk.com) account
- A [Google AI Studio](https://aistudio.google.com) API key (Gemini)

### Installation

```bash
# Clone the repository
git clone https://github.com/your-username/campuspulse.git
cd campuspulse

# Install dependencies
npm install
```

### Environment Variables

Create a `.env.local` file in the root directory:

```env
# Clerk
NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY=your_clerk_publishable_key
CLERK_SECRET_KEY=your_clerk_secret_key
NEXT_PUBLIC_CLERK_SIGN_IN_URL=/sign-in
NEXT_PUBLIC_CLERK_SIGN_UP_URL=/sign-up

# Convex
NEXT_PUBLIC_CONVEX_URL=your_convex_deployment_url

# Google Gemini AI
GEMINI_API_KEY=your_gemini_api_key
```

### Running the App

```bash
# Start the Convex backend (in a separate terminal)
npx convex dev

# Start the Next.js development server
npm run dev
```

Open [http://localhost:3000](http://localhost:3000) in your browser.

---

## 🔐 Route Protection

Routes are protected via Clerk middleware (`proxy.js`). The following routes require authentication:

- `/my-events` — Manage your created events
- `/create-event` — Create a new event
- `/my-tickets` — View your registered tickets

All other routes (`/explore`, `/events/[slug]`, etc.) are publicly accessible.

---

## 📦 Scripts

```bash
npm run dev      # Start development server
npm run build    # Build for production
npm run start    # Start production server
npm run lint     # Run ESLint
```

---

