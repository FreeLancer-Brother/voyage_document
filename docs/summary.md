# Project Requirements Summary (docs)

Quick links: [Summary (VI)](./summary-vi.md) · [Tech Stack](./tech-stack.md) · [User Stories](./user-stories.md) · [Client Feedback](./client-feedback.md)

## Overview

- Project: VOYAGE+ card program and member portal for Tam Son Yachting
- Surfaces: Public landing page (SEO-visible), user landing portal, and admin dashboard
- Platforms: Web, responsive for mobile/desktop
- Languages: VI | EN

## Existing System Context

- There is an existing website (e.g., abc.com) and an admin system for blog/employee management.
- Plan: reuse the existing React admin codebase and add new pages/modules (no new codebase unless backend limits).

## Latest Client Clarifications

- Each physical card has a QR code and a unique Serial ID.
- Access flow:
  - Scan QR → Welcome Aboard page
  - Enter Serial ID → User Dashboard
- User Dashboard purpose: track status, see benefits, and encourage future charter bookings (not a complex booking system).
- Admin focus: keep features essential for card operations (not overly complex).

## Pages to Build

- User Page:
  - Accessed via QR code on customer card with unique ID
  - After scanning, redirect to login page
  - After login, users can view benefits, rank, points
- Admin Page:
  - Used by employees to input score, choose benefit, and CRUD benefits for customers/members

Note: Separate Member Page is removed; use read-only permissions in Admin “Members” module instead.

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

### Core Purpose

- Track card status
- Show current privileges
- Encourage continued charter bookings

### Card Status
- Current tier: Base / Gold / Diamond

### Current Privileges
- Benefits corresponding to current tier

### Charter Price
- Yacht pricing by tier
- Admin can manually edit

### Voyage History
- Past trips (destination, yacht, date, spending)

### Total Spending (to date)
- Current total spending
- Remaining amount to reach next tier

### Next Privileges
- Benefits of next tier (Gold / Diamond)
- Motivational display

### About Tam Son Yachting
- Short introduction and link to main site

## Admin Dashboard

### Dashboard (Quick Overview)
- Total issued cards (serials created in advance)
- Active cards count (cards that have been verified/logged in)
- Bookings/voyages in the last week

### Members (Users & Cards)
- Serial ID
- Current tier (Base / Gold / Diamond)
- Total spending (split owner vs network users)
- Voyage history (destination, yacht, date, booking type)
- Card status: active / inactive
- Admin actions:
  - Create new card
  - Update tier thresholds
  - Edit card spending
  - Deactivate card

### Benefits (Tiered Privileges)
- Admin edits tier benefits without dev changes
- Admin can edit charter prices by tier
- Admin can update “Next privileges” shown to users

### Reports
- Total spending by month
- Total bookings/voyages by month
- Count of members reaching Gold/Diamond
- Top members by spending
- Export data (Excel/CSV)

### Settings
- Tier thresholds: Gold after USD 20,000; Diamond after USD 30,000
- Language (VI / EN)
- Link to Tam Son Yachting website
- Admin accounts (login/password)
- Read-only role for staff (to replace separate Member Page)

## Design Direction

- Mood/Tone: private, calm luxury, confident, not flashy
- Visuals: dark background, neutral/champagne/gold accents
- Motion: subtle water movement and light reflection
- UI priority: highlight private rate, clear status badge (Base/Gold/Diamond)
