# Features and User Stories (Rally-style)

Quick links: [Summary](./summary.md) · [Tech Stack](./tech-stack.md) · [Client Feedback](./client-feedback.md)

## Public Landing (SEO)

- US001 — Access landing page: As a visitor, I can access `/voyageplus` from search without seeing private data.
- US002 — See public welcome: As a visitor, I see a welcome page that explains private access.
- US003 — Switch language: As a visitor, I can switch VI/EN on the landing page.

## Entry / Welcome Overlay

- US004 — Block direct access: As a visitor, a full-screen overlay prevents direct access to content.
- US005 — Display branding: As a visitor, I see logo, headline, subtext, and CTA.
- US006 — Show error state: As a visitor, I see a light error message when access is invalid.

## QR Entry Flow

- US007 — Open from QR: As a member, I can scan QR on my card to open the landing page.

## Serial Verification

- US008 — Verify serial: As a member, I can enter my card serial number to verify access.
- US009 — Show status: As a member, I see status Valid/Invalid/Active after submission.
- US010 — Contact admin: As a member, I can contact admin if my serial is invalid.

## User Page (Login + Benefits)

- US011 — Login after QR: As a user, after scanning QR I am redirected to a login page.
- US012 — View benefits: As a user, I can view my benefits after login.
- US013 — View rank and points: As a user, I can view my rank and points after login.

## User Dashboard – Core Sections

- US014 — View card status: As a user, I can see my current tier (Base/Gold/Diamond).
- US015 — View current privileges: As a user, I can see benefits of my current tier.
- US016 — View charter prices: As a user, I can see yacht pricing by tier.
- US017 — View voyage history: As a user, I can see past trips with destination, yacht, date, spending.
- US018 — View total spending: As a user, I can see total spending and remaining amount to next tier.
- US019 — View next privileges: As a user, I can preview benefits of the next tier.
- US020 — About Tam Son Yachting: As a user, I can read a short intro and open the main website.

## Member Page (Employee Read-only)

- US021 — View member points: As an employee, I can view customer/member points/score.
- US022 — View member benefits: As an employee, I can view customer/member benefits.
- US023 — View member status: As an employee, I can view active status and offline status date.

## Admin Access

- US024 — Admin login: As an admin, I can log in to the admin dashboard.

## Admin Dashboard (Quick Overview)

- US025 — View issued cards: As an admin, I can see total issued cards.
- US026 — View active cards: As an admin, I can see how many cards are active (verified/logged in).
- US027 — View weekly activity: As an admin, I can see bookings/voyages from the last week.

## Admin – Members (Users & Cards)

- US028 — View member list: As an admin, I can view members and their Serial ID, tier, status.
- US029 — View spending split: As an admin, I can see spending split (owner vs network users).
- US030 — View member history: As an admin, I can see trip history with booking type.
- US031 — Create new card: As an admin, I can create new card serials.
- US032 — Edit spending: As an admin, I can edit card spending when needed.
- US033 — Update tier thresholds: As an admin, I can update tier spending requirements.
- US034 — Deactivate card: As an admin, I can deactivate a card.

## Admin – Benefits (Tiered Privileges)

- US035 — Edit benefit content: As an admin, I can edit benefits by tier without dev changes.
- US036 — Edit charter prices: As an admin, I can edit charter prices per tier.
- US037 — Update next privileges: As an admin, I can update “Next privileges” shown to users.

## Admin – Reports

- US038 — Monthly spending: As an admin, I can view total spending by month.
- US039 — Monthly voyages: As an admin, I can view bookings/voyages by month.
- US040 — Tier upgrades: As an admin, I can see how many members reached Gold/Diamond.
- US041 — Top members: As an admin, I can see top members by spending.
- US042 — Export data: As an admin, I can export reports to Excel/CSV.

## Admin – Settings

- US043 — Manage tier thresholds: As an admin, I can set Gold/Diamond thresholds.
- US044 — Manage language: As an admin, I can set VI/EN.
- US045 — Manage website link: As an admin, I can update the Tam Son Yachting site link.
- US046 — Manage admin accounts: As an admin, I can manage admin login/password.
