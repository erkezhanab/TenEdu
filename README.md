# TenEdu

**A Kazakh-language digital literacy platform for people who are new to computers and the internet.**

TenEdu ("Теңеду" — "to become equal" in Kazakh) teaches basic digital skills in Kazakh, step by step: using a smartphone, staying safe online, government e-services and more. It is built to be accessible and to work on weak connections.

> **Status:** working prototype. Not yet tested with real learners.

<!-- Add 2–4 screenshots here, e.g. docs/screenshots/catalog.png, module.png, certificate.png -->
<!-- ![Course catalog](docs/screenshots/catalog.png) -->

---

## Why

Most digital literacy courses in Kazakhstan are in Russian or English, and many assume the learner already knows how to use a computer. TenEdu starts from zero, in Kazakh.

## Features

- **Learning tracks and modules** — 4 tracks, 12+ modules, with progress tracking <!-- check the numbers against the content -->
- **Three languages** — Kazakh (main), Russian and English (`next-intl`)
- **Accessibility first** — built toward WCAG 2.1 AAA: keyboard navigation, screen-reader labels, high contrast <!-- keep only what is really implemented; see A11Y_IMPROVEMENTS.md -->
- **Works offline** — installable PWA with cached lessons
- **Certificates** — PDF certificate generated after finishing a track
- **Dashboard and profile** — learner progress in one place
- **Admin panel** — content managed by admins

## Tech stack

| Part | Tools |
|---|---|
| Frontend | Next.js (App Router), React, TypeScript, Tailwind CSS |
| Backend and auth | Supabase (Postgres, Auth, Row Level Security) |
| Internationalization | next-intl (kk / ru / en) |
| Offline | PWA (service worker) |
| Certificates | jsPDF, html2canvas |
| Testing | Vitest (unit), Playwright (end-to-end) |

## Getting started

```bash
git clone https://github.com/erkezhanab/TenEdu.git
cd TenEdu
npm install
```

1. Create a free project at [supabase.com](https://supabase.com).
2. In the Supabase **SQL Editor**, run `supabase-setup.sql` to create the tables and access rules.
3. Create `.env.local` in the project root:

   ```
   NEXT_PUBLIC_SUPABASE_URL=https://your-project.supabase.co
   NEXT_PUBLIC_SUPABASE_ANON_KEY=your-anon-key
   ```

4. Start the app:

   ```bash
   npm run dev
   ```

   Open http://localhost:3000.

See `ADMIN_SETUP.md` to create an admin account and `DEPLOYMENT.md` to deploy.

## Tests

```bash
npm test                 # unit tests (Vitest)
npx playwright test      # end-to-end tests
```
<!-- run the tests and write the real number here, e.g. "89 tests passing" -->

## Project structure

```
src/
  app/[locale]/   pages: landing, login, register, catalog, modules, dashboard, profile
  components/     UI: courses, dashboard, onboarding
  hooks/          shared React hooks
supabase/         Supabase config
supabase-setup.sql  database schema and access rules
```

## Roadmap

- [ ] Pilot with real learners
- [ ] More modules <!-- which ones? -->
- [ ] Audio lessons for learners who read slowly <!-- replace with your real plans -->

## Author

**Yerkezhan Abil** — founder and developer · erkezhanabil@gmail.com · [LinkedIn](https://www.linkedin.com/in/erkezhanabil)
