# ConsultHUB

ConsultHUB is a React + Vite front-end prototype for discovering experts, booking sessions, managing conversations, saving favorites, and maintaining a personal profile. The app is designed as a mobile-first consultation platform and includes a dark/light theme, responsive navigation, notifications, and reusable expert booking flows.

![ConsultHUB app preview](./public/consulthub-screenshot.svg)

## Features

- Landing page with sign-in / sign-up experience
- Responsive app shell with sidebar on larger screens and bottom navigation on mobile
- Browse experts by category and view key details such as specialty, rating, rate, and bio
- Save and revisit experts in a dedicated saved list
- Book sessions with a time-slot picker and credit-based checkout flow
- View upcoming and completed sessions in a session dashboard
- Message thread conversations with simulated agent replies
- In-app notifications and reminder-style interactions
- Profile management with avatar selection, credits, theme toggle, and preference settings
- Front-end persistence for theme preference using localStorage

## Quick start

```bash
npm install
npm run dev
```

Then open: http://localhost:5173

Production build:

```bash
npm run build
```

## Architecture

See [ARCHITECTURE.md](./ARCHITECTURE.md) for the full app architecture overview and component map.

## Repository structure

```text
ConsultHUB/
├── public/
│   └── consulthub-screenshot.svg
├── src/
│   ├── components/
│   ├── pages/
│   ├── App.jsx
│   ├── AuthCard.jsx
│   ├── Landing.jsx
│   ├── Shell.jsx
│   ├── data.js
│   ├── hooks.js
│   ├── index.css
│   └── main.jsx
├── .env.example
├── .gitignore
├── ARCHITECTURE.md
├── index.html
├── package.json
├── README.md
├── vite.config.js
└── package-lock.json
```

## Key application flow

- `App.jsx` decides whether to render the landing/auth flow or the authenticated shell.
- `Landing.jsx` handles welcome, login, and sign-up views.
- `Shell.jsx` manages app-wide state for sessions, messages, notifications, saved experts, credits, and tab navigation.
- `src/pages/*.jsx` contains the main screens: Home, Sessions, Messages, Saved, and Profile.
- `src/components/*.jsx` contains reusable UI pieces such as avatar, expert cards, sheet modals, notifications, and icons.
- `src/data.js` stores the seed data for experts, sessions, threads, and time helpers.
- `src/hooks.js` handles theme persistence and global color theming.

## Notes

This project is front-end only. Login, bookings, messages, and saved experts are simulated in memory and reset on refresh.
