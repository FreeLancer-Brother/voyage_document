# Recommended Tech Stack

Quick links: [Summary](./summary.md) · [User Stories](./user-stories.md) · [Client Feedback](./client-feedback.md)

## Current System Stack (Reuse)

- React 17 (Create React App)
- Ant Design 4
- React Router 6
- Redux Toolkit
- Styled Components + Bootstrap (existing)
- Axios, Moment, CKEditor

Plan: reuse the existing React admin codebase and add new pages/modules (no separate Member Page).

## Time Estimate (Standard Scope)

- Estimated effort: 210–320 hours
- At 3 hours/day (Mon–Fri):
  - Workdays: 70–107 days
  - Calendar duration: ~14–22 weeks (≈ 3.5–5 months)
- Client-friendly single number:
  - 260 hours → 87 workdays → ~18 weeks

## Time Breakdown (Standard Scope)

- Discovery + setup (repo, env, DB/API mapping, auth review): 16–24 hrs → 6–8 days
- Public landing + welcome overlay: 16–24 hrs → 6–8 days
- Member entry flow (QR/serial verify + states): 16–22 hrs → 6–8 days
- User page login + benefits/rank/points: 22–32 hrs → 8–11 days
- User dashboard core sections: 32–48 hrs → 11–16 days
- Admin dashboard (quick overview + members): 34–50 hrs → 12–17 days
- Admin benefits management (edit benefits/prices/next privileges): 18–28 hrs → 6–10 days
- Reports + export (monthly stats, tier upgrades, CSV/Excel): 18–28 hrs → 6–10 days
- Settings (thresholds, language, website link, admin accounts, read-only role): 14–22 hrs → 5–8 days
- API + DB (cards, users, bookings, status, pricing, points/benefits): 40–60 hrs → 14–20 days
- QA + bug fix + feedback rounds: 22–32 hrs → 8–11 days
- Deployment + handoff: 6–10 hrs → 2–4 days

Total: 210–320 hours

## Budget Estimate (Standard Scope)

Rate: 180,000 VND/hour

- 210–320 hours → 37,800,000–57,600,000 VND
- Client-friendly single number: 260 hours → 46,800,000 VND
