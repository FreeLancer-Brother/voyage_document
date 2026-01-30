# Project Requirements Summary (docs)

## Overview

- Project: VOYAGE+ card program and member portal for Tam Son Yachting
- Surfaces: Public landing page (SEO-visible), user landing portal, and admin dashboard
- Platforms: Web, responsive for mobile/desktop
- Languages: VI | EN

## Membership Program & Privileges

- Card levels: Base (default), Gold (after USD 20,000 annual combined trips), Diamond (after USD 30,000)
- Base benefits:
  - 10% discount on standard charter price (VAT excluded)
  - Rates shown only after card serial verification
  - Applies to Owners and Referral guests
- Gold benefits:
  - Private rate 15%
  - Priority booking access (high season/weekend)
  - Invitation-only preview / priority yacht trial
  - Yacht purchase discount up to 3% (budget/model dependent)
- Diamond benefits:
  - All Gold benefits
  - Complimentary onboard service (custom itinerary, +30 mins cruising time)
  - Yacht purchase discount up to 5% (budget/model dependent)
- Rules:
  - Card level based on accumulated spending value
  - No points/loyalty concept; track Voyages logged and Total spending
  - Not combinable with other promotions/discounts/vouchers

## Global Logic

- Valid voyage = booking status Completed
- 1 completed booking = 1 voyage
- Referral voyage = booking created by non-owner user but using valid card serial

## Public Landing Page (SEO-visible)

- URL: tamsonyachting.com/voyageplus
- Not shown in homepage menu; discoverable via search engine
- Default view: Welcome Aboard screen (no sensitive info)
- Must require serial verification before showing private data

## Entry / Welcome Screen (User)

- Purpose: restricted/private access feel; no direct content access
- UI: full-screen overlay / animated popup
- Content:
  - TSY logo, headline “Welcome Aboard”
  - Subheadline: Member Access via Card Serial Number
  - Subheadline: Admin Access
  - Subtext: access only via card serial number
  - CTA: Enter Your Card ID
- Behavior:
  - Valid serial → verify → enter dashboard
  - Invalid serial → keep overlay and show light error message

## User Flow

- Step 1: QR access from Membership card
  - QR opens landing page in browser (mobile/desktop)
- Step 2: Enter card serial number
  - One serial per card; serial can be used by multiple users
  - All bookings are tied to the original card
  - Status indicator: Valid / Invalid / Active
  - If invalid: show contact admin button

## User Dashboard (Card Portal)

### Card Overview
- Card name, Card status (Base/Gold/Diamond)
- Voyages completed (total)
- Booking spending progress toward $20k / $30k
- Last network booking (date + yacht)
- Progress indicator (e.g., “x VND to reach Gold”)

### Charter Price
- Table of yacht prices by card level
- Show pre-discount and post-discount price
- Applies to Owners & Network users

### Card Benefits
- Base: 10% charter rate
- Gold: 15% charter rate, priority booking, invitation-only previews
- Diamond: all Gold + onboard services (+30 mins), partner benefits
- UI checklist by level; lock/greyed future levels

### Voyage History
- Each trip: date, yacht model, route, booking type (Self/Referral), status
- Show savings per completed trip (e.g., “You saved X VND”)

### Progress & Next Level
- Show remaining spending to next tier (avoid “accumulation” wording)
- CTAs: Book next voyage, View next-level benefits

### Future Privileges
- Public teaser content; greyed/labelled “Available at Gold/Diamond”
- Copy about thresholds and evolving benefits

### About TSY
- CTA to visit Tam Son Yachting website

## Admin Dashboard

### Quick Stats
- Total cards, Active cards, Newest bookings (with card ID)
- Taps open card list or booking detail (mobile-friendly)

### Primary Actions
- Update charter pricing
- View/Edit/Update member list (owner + referral guests)
- Card status management (add/edit/delete)
- Post news/notices

### Recent Activity
- List/timeline of last 3 days: new member, new booking, card status updated
- Scrollable, tap to view detail

### Modules Navigation
- Members, Benefits, Reports, Settings
- Grid or sidebar layout; clear consistent icons

## Design Direction

- Mood/Tone: private, calm luxury, confident, not flashy
- Visuals: dark background, neutral/champagne/gold accents
- Motion: subtle water movement and light reflection
- UI priority: highlight private rate, clear status badge (Base/Gold/Diamond)
