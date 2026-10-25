# TicketGate

Ticketing and QR check-in for attractions and events, with purchase orders, daily revenue reports and an audit trail.

> **Status: in development.** This repo is the plan and the write-up; the interactive demo is being built next.
> **Demo preview:** https://julynard.github.io/ticketgate/ (becomes the live demo when it ships).

Part of [Julynard Tago-on's portfolio](https://julynardtago-on.netlify.app/#projects). Based on the ticketing system I designed and built for a theme attraction (freelance) and a QR attendance system.
Client code is private, so this is a clean-room demo with fictional data. No client names or real data.

## What the demo will show

- [ ] Buy tickets (simulated payment) and get a **QR code** per ticket
- [ ] **Scanner page**: scan with your phone camera or click "simulate scan"; a valid ticket checks in, a **second scan is blocked** with the time it was used
- [ ] Group purchase orders
- [ ] Daily revenue report with a chart
- [ ] An audit trail of every action

Every key action will have an **"In production"** note explaining how the real system does it.

## How the production system works

The real system runs on Laravel. The demo simulates these behaviours in the browser so it can stay fast and always on.

- Laravel backend with ticket status transitions guarded in one place
- Single-use ticket codes: check-in is an atomic state change, so two gates can't admit the same ticket
- Revenue reports aggregated per day from ticket and purchase-order records
- Every change written to an audit log for the operator's finance team

## Planned stack

- Vue 3 + TypeScript + Vite
- Tailwind CSS v4
- Pinia (state saved in the browser, with a **Reset demo** button)
- Vitest for the domain logic, ESLint + Prettier + `vue-tsc` in CI
- `qrcode` + `html5-qrcode` for generating and scanning
- GitHub Actions → GitHub Pages (free, always on)

## Roadmap

1. Project scaffold, CI (lint, type-check, test, build) and GitHub Pages deploy
2. Domain logic with Vitest tests
3. UI with seeded data, guided steps and "In production" notes
4. Screenshot/GIF in this README and the live demo link

## Author

**Julynard Tago-on**, Laravel / PHP full-stack engineer · [Portfolio](https://julynardtago-on.netlify.app) · [GitHub](https://github.com/Julynard) · [LinkedIn](https://www.linkedin.com/in/julynard-tago-on/)

## License

[MIT](LICENSE)
