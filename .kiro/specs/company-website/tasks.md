# Implementation Plan: Company Website

## Overview

Build a minimal static company website for Onidev LLC consisting of 5 files: a shared stylesheet, a home page, a privacy policy page, a support page, and a data deletion page. All files use plain HTML/CSS/JS with no frameworks or build tools. Pages use directory-based routing (`/privacy/index.html` instead of `/privacy.html`) for clean GitHub Pages URLs. Navigation and footer are duplicated in each HTML file with depth-aware relative paths.

## Tasks

- [x] 1. Create the shared stylesheet
  - [x] 1.1 Create `/assets/styles.css` with CSS custom properties, typography, layout, and responsive styles
    - Define CSS custom properties (design tokens): `--bg`, `--text`, `--muted`, `--card`, `--border`, `--accent`
    - Set up system font stack, base `line-height: 1.6`, `box-sizing: border-box` reset
    - Style `<header>`, `<nav>` with flexbox layout, `.brand` link, `.links` container with hover effects
    - Style `<main>` with centered layout, `.card` with white background, border, border-radius, box-shadow
    - Style `.eyebrow`, `.section`, `.updated`, heading sizes with `clamp()` for fluid scaling
    - Style `<footer>` with `.footer-content` and `.footer-links`
    - Style links with `text-decoration-thickness: 2px` and `text-underline-offset: 4px`
    - Add single responsive breakpoint at 640px for card padding and nav alignment adjustments
    - Max content width: 920px centered with `margin: 0 auto`
    - _Requirements: 4.1, 4.2, 4.3, 4.4, 4.5, 4.6, 5.1, 5.2_

- [x] 2. Create the home page
  - [x] 2.1 Create `/index.html` with full page structure
    - HTML5 doctype, `<html lang="en">`, `<head>` with charset, viewport, title ("Onidev LLC"), meta description
    - Link to `./assets/styles.css`
    - `<header>` with shared navigation using `./` relative paths; `aria-label="Main navigation"` on `<nav>`
    - Nav links: Home, Privacy (`./privacy/`), Support (`./support/`), Data Deletion (`./data-deletion/`)
    - `<main>` with `<article class="card">` containing:
      - `.eyebrow` paragraph: "Independent App & Game Publisher"
      - `<h1>`: "Onidev LLC"
      - Introductory paragraph: location (Maryland, USA), general business activity
      - "What We Make" `<section>`: word puzzle games for general audiences, no specific titles
      - "Player Support" `<section>`: link to support page + support email
      - "Privacy" `<section>`: link to privacy page
      - "Data Deletion" `<section>`: link to data deletion page
      - "Contact" `<section>`: support email (support@onidev.io)
    - `<footer>` with copyright, email, links to Privacy/Support/Data Deletion using `./` paths
    - `<script>` for dynamic copyright year
    - No stock photography, hero images, or decorative graphics
    - No owner personal name, no specific app names, no "APP_NAME" token
    - _Requirements: 1.1, 1.2, 1.3, 1.4, 1.5, 1.6, 1.7, 2.1, 2.2, 2.3, 2.4, 3.1, 3.2, 3.3, 3.4, 6.1, 6.2, 6.3, 6.4, 6.5, 6.6, 6.7, 6.8, 5.1, 5.2, 5.3, 5.4, 5.5, 10.1, 10.2, 10.4_

- [x] 3. Create the privacy policy page
  - [x] 3.1 Create `/privacy/index.html` with all 17 privacy policy sections
    - HTML5 doctype, `<html lang="en">`, `<head>` with charset, viewport, title ("Privacy Policy | Onidev LLC"), meta description
    - Link to `../assets/styles.css` (subdirectory depth)
    - `<header>` with shared navigation using `../` relative paths
    - `<main>` with `<article class="card">` containing `<h1>Privacy Policy</h1>` and effective date "May 6, 2026"
    - Section 1 — Introduction
    - Section 2 — Who We Are (company name, Maryland USA, developer and publisher role)
    - Section 3 — Information We Do Not Directly Collect (no account creation, no personal contact info, no payment cards)
    - Section 4 — Information Processed to Operate Our Games and Apps (6 categories: player identifiers, in-game profile, gameplay data, purchase/entitlement, device/technical, advertising/analytics)
    - Section 5 — How We Use Information (operating games, cloud features, ads, performance, support, legal)
    - Section 6 — Service Providers (Unity Gaming Services, Unity LevelPlay, Apple/Google, analytics placeholder, crash reporting placeholder)
    - Section 7 — Advertising
    - Section 8 — Analytics and Game Balancing
    - Section 9 — Cloud Save, Profiles, Leaderboards, and Friends
    - Section 10 — Purchases
    - Section 11 — Data Retention
    - Section 12 — Data Deletion and Account Requests (link to data deletion page + support email)
    - Section 13 — Children (not directed at children under 13)
    - Section 14 — Security
    - Section 15 — International Users
    - Section 16 — Changes to This Policy
    - Section 17 — Contact (company name, location, support email)
    - `<footer>` with `../` relative paths
    - `<script>` for dynamic copyright year
    - Plain, factual tone; no legalese; no excessive boilerplate
    - Describe data at category/service level, not individual SDK names
    - Use "an analytics provider" and "a crash reporting provider" as descriptive placeholders
    - _Requirements: 1.1, 1.5, 1.6, 2.1, 2.3, 3.1, 3.3, 3.4, 7.1, 7.2, 7.3, 7.4, 7.5, 7.6, 7.7, 7.8, 7.9, 7.10, 7.11, 7.12, 7.13, 7.14, 10.1, 10.2, 10.3, 10.4, 10.5_

- [x] 4. Checkpoint — Verify home page and privacy page
  - Ensure the stylesheet loads correctly from both root and subdirectory pages
  - Verify navigation links use correct relative paths for each page depth
  - Ensure all tests pass, ask the user if questions arise.

- [x] 5. Create the support page
  - [x] 5.1 Create `/support/index.html` with all support sections
    - HTML5 doctype, `<html lang="en">`, `<head>` with charset, viewport, title ("Support | Onidev LLC"), meta description
    - Link to `../assets/styles.css` (subdirectory depth)
    - `<header>` with shared navigation using `../` relative paths
    - `<main>` with `<article class="card">` containing:
      - `<h1>`: "Support"
      - Brief introductory statement
      - "Contact Us" section: support email (support@onidev.io) as primary contact method
      - "What to Include" section: app/game name, device, operating system, issue description
      - "Purchases and Refunds" section: purchases processed by Apple/Google, direct to stores for refunds
      - "Privacy and Data Requests" section: links to privacy page (`../privacy/`) and data deletion page (`../data-deletion/`)
      - "Response Time" section: response time expectation
    - `<footer>` with `../` relative paths
    - `<script>` for dynamic copyright year
    - _Requirements: 1.1, 1.5, 1.6, 2.1, 2.3, 3.1, 3.3, 3.4, 8.1, 8.2, 8.3, 8.4, 8.5, 8.6, 10.1, 10.2_

- [x] 6. Create the data deletion page
  - [x] 6.1 Create `/data-deletion/index.html` with all data deletion sections
    - HTML5 doctype, `<html lang="en">`, `<head>` with charset, viewport, title ("Data Deletion | Onidev LLC"), meta description
    - Link to `../assets/styles.css` (subdirectory depth)
    - `<header>` with shared navigation using `../` relative paths
    - `<main>` with `<article class="card">` containing:
      - `<h1>`: "Data Deletion"
      - Brief introduction explaining the purpose of the page
      - "How to Request Data Deletion" section: support email + what info to include
      - "What Data May Be Deleted" section
      - "What Data May Be Retained" section: anonymized analytics, platform purchase records
      - "Purchase History" section: warning that deletion doesn't affect Apple/Google purchase records
      - "Identity Verification" section
      - "Processing Time" section
    - `<footer>` with `../` relative paths
    - `<script>` for dynamic copyright year
    - _Requirements: 1.1, 1.5, 1.6, 2.1, 2.3, 3.1, 3.3, 3.4, 9.1, 9.2, 9.3, 9.4, 9.5, 9.6, 9.7, 10.1, 10.2_

- [x] 7. Final checkpoint — Cross-page verification
  - Verify all 5 files exist: `/index.html`, `/privacy/index.html`, `/support/index.html`, `/data-deletion/index.html`, `/assets/styles.css`
  - Verify all internal links resolve correctly with proper relative paths from each page depth
  - Verify shared navigation and footer are consistent across all 4 HTML pages
  - Verify no `[PLACEHOLDER]` bracket tokens appear in rendered content (all pre-filled)
  - Verify no `APP_NAME` token appears anywhere
  - Verify the owner's personal legal name does not appear
  - Verify all pages use semantic HTML (`<header>`, `<nav>`, `<main>`, `<article>`, `<section>`, `<footer>`)
  - Verify `aria-label` attributes on all `<nav>` elements
  - Ensure all tests pass, ask the user if questions arise.

## Notes

- No property-based tests: this is a static HTML/CSS/JS site with no backend logic or data transformations
- All placeholder values are pre-filled with real values (Onidev LLC, support@onidev.io, May 6 2026, Maryland USA)
- Analytics and crash reporting providers use descriptive text ("an analytics provider") since providers are not finalized
- Each task references specific requirements for traceability
- Checkpoints ensure incremental validation of cross-page consistency
