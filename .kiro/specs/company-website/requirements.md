# Requirements Document

## Introduction

Onidev LLC needs a minimal static company website to serve as the public web presence for an independent LLC that publishes mobile games and apps on the Apple App Store and Google Play. The website must satisfy Apple Developer Program organization enrollment expectations, provide privacy policy URLs for App Store Connect and Google Play, provide support URLs for both stores, and provide a data deletion web resource for Google Play compliance. The site must present the company professionally without exposing the owner's personal legal name, and without implying the company is a large studio. The site is built as a static website suitable for GitHub Pages with no backend, no cookies, no tracking scripts, and no analytics.

## Glossary

- **Website**: The static company website hosted on GitHub Pages, consisting of HTML, CSS, and JS files served as static routes.
- **Home_Page**: The landing page at `/index.html` that presents the company identity and links to key resources.
- **Privacy_Page**: The privacy policy page at `/privacy/index.html` that describes data practices at a company and service level.
- **Support_Page**: The player/user support page at `/support/index.html` that provides contact information and guidance for support requests.
- **Data_Deletion_Page**: The data deletion request page at `/data-deletion/index.html` that explains how users can request deletion of their data.
- **Stylesheet**: The shared CSS file at `/assets/styles.css` used by all pages.
- **Navigation**: The shared header navigation bar present on all pages, linking to Home, Privacy, Support, and Data Deletion.
- **Footer**: The shared footer present on all pages, displaying company legal name, contact email, copyright year, and links to Privacy, Support, and Data Deletion.
- **Placeholder**: A clearly marked token in source files (e.g., `[COMPANY_LEGAL_NAME]`) intended to be replaced with real values before deployment.
- **EARS_Pattern**: Easy Approach to Requirements Syntax — a structured pattern for writing unambiguous requirements.
- **Apple_Developer_Program**: Apple's program requiring an organization website for company/organization enrollment.
- **App_Store_Connect**: Apple's portal for managing App Store listings, which requires a privacy policy URL and support URL.
- **Google_Play_Console**: Google's portal for managing Play Store listings, which requires a privacy policy URL, support URL, and data deletion URL.
- **Unity_Gaming_Services**: Unity's suite of backend services including authentication, cloud save, leaderboards, and friends.
- **Unity_LevelPlay**: Unity's mediation and advertising platform (formerly ironSource).
- **GitHub_Pages**: GitHub's static site hosting service that serves files from a repository.

## Requirements

### Requirement 1: Site Structure and Static Hosting

**User Story:** As a developer, I want the website to be a set of static HTML/CSS/JS files organized for GitHub Pages, so that I can host it without a backend or build step.

#### Acceptance Criteria

1. THE Website SHALL consist of the following static files: `/index.html`, `/privacy/index.html`, `/support/index.html`, `/data-deletion/index.html`, and `/assets/styles.css`.
2. THE Website SHALL use only plain HTML, CSS, and vanilla JavaScript with no external frameworks, build tools, or server-side dependencies.
3. THE Website SHALL use relative links for all internal navigation so that all pages resolve correctly when served from GitHub_Pages.
4. THE Website SHALL contain no tracking scripts, no cookies, and no analytics code.
5. THE Website SHALL use semantic HTML elements including `<header>`, `<nav>`, `<main>`, `<article>`, `<section>`, and `<footer>`.
6. THE Website SHALL include accessible navigation with appropriate `aria-label` attributes on navigation landmarks.
7. THE Website SHALL render correctly on viewports from 320px to 1440px wide using responsive CSS.

### Requirement 2: Shared Navigation

**User Story:** As a site visitor, I want consistent navigation on every page, so that I can easily move between sections of the website.

#### Acceptance Criteria

1. THE Navigation SHALL appear in the `<header>` of every page and link to Home, Privacy, Support, and Data Deletion.
2. THE Navigation SHALL display the company legal name as a clickable brand link that navigates to the Home_Page.
3. THE Navigation SHALL use relative paths for all links.
4. THE Navigation SHALL wrap gracefully on narrow viewports without content overflow.

### Requirement 3: Shared Footer

**User Story:** As a site visitor, I want a consistent footer on every page, so that I can find contact information and legal links from any page.

#### Acceptance Criteria

1. THE Footer SHALL appear on every page and display the company legal name, contact email, and copyright year.
2. THE Footer SHALL include links to the Privacy_Page, Support_Page, and Data_Deletion_Page.
3. THE Footer SHALL dynamically display the current year using JavaScript.
4. THE Footer SHALL use relative paths for all links.

### Requirement 4: Shared Stylesheet

**User Story:** As a developer, I want a single shared CSS file, so that all pages have a consistent visual style without duplication.

#### Acceptance Criteria

1. THE Stylesheet SHALL be located at `/assets/styles.css` and linked from every HTML page.
2. THE Stylesheet SHALL define a light background, centered content layout with a readable max-width, header navigation styling, footer styling, and card/section styling.
3. THE Stylesheet SHALL use only system fonts with no external font loading.
4. THE Stylesheet SHALL provide readable typography with appropriate line-height, font-size, and contrast.
5. THE Stylesheet SHALL support responsive layouts for viewports from 320px to 1440px using CSS media queries or fluid sizing.
6. THE Stylesheet SHALL not import any external CSS files or resources.

### Requirement 5: Visual Style

**User Story:** As a company owner, I want the website to look professional and understated, so that it presents the LLC credibly without implying it is a large studio.

#### Acceptance Criteria

1. THE Website SHALL use a professional, simple, understated visual style with a light color scheme.
2. THE Website SHALL not include stock photography, hero images, app screenshots, or decorative graphics.
3. THE Website SHALL not reference specific app names, unreleased games, future game concepts, or roadmap details.
4. THE Website SHALL not use the token "APP_NAME" anywhere in rendered content.
5. THE Website SHALL present the company as an independent software and game publisher without implying a large team or studio.

### Requirement 6: Home Page — Company Presence

**User Story:** As a company owner, I want a home page that satisfies Apple Developer Program organization website expectations, so that Apple can verify the LLC is a real business entity with a public web presence.

#### Acceptance Criteria

1. THE Home_Page SHALL display a hero section with the company legal name as the primary heading and a subtitle identifying the company as an independent app and game publisher.
2. THE Home_Page SHALL include a short introductory paragraph stating the company's location and general business activity.
3. THE Home_Page SHALL include a "What We Make" section describing the general category of apps and games published (word puzzle games for general audiences) without naming specific titles.
4. THE Home_Page SHALL include a "Player Support" section with a link to the Support_Page and the support email address.
5. THE Home_Page SHALL include a "Privacy" section with a link to the Privacy_Page.
6. THE Home_Page SHALL include a "Data Deletion" section with a link to the Data_Deletion_Page.
7. THE Home_Page SHALL include a contact line with the support email address.
8. THE Home_Page SHALL not expose the owner's personal legal first and last name.

### Requirement 7: Privacy Page — App Store and Google Play Compliance

**User Story:** As a company owner, I want a company-level privacy policy page, so that I can provide a valid privacy policy URL for App Store Connect and Google Play Console listings.

#### Acceptance Criteria

1. THE Privacy_Page SHALL display a title of "Privacy Policy" and an effective date.
2. THE Privacy_Page SHALL include a "Who We Are" section identifying the company legal name, location, and role as developer and publisher.
3. THE Privacy_Page SHALL include a section titled "Information We Do Not Directly Collect" clarifying that the company does not require account creation, does not collect personal contact information through apps, and does not collect payment card details directly.
4. THE Privacy_Page SHALL include a section describing information processed to operate games and apps, organized into the following categories: player identifiers, in-game profile information, gameplay data, purchase and entitlement information, device and technical data, and advertising and analytics data.
5. WHEN describing data categories, THE Privacy_Page SHALL describe data practices at a category and service level without listing individual SDK package names.
6. THE Privacy_Page SHALL include a "How We Use Information" section listing purposes such as operating games, providing cloud features, serving ads, improving performance, responding to support requests, and complying with legal obligations.
7. THE Privacy_Page SHALL include a "Service Providers" section listing Unity_Gaming_Services, Unity_LevelPlay, Apple and Google platform services, an analytics provider placeholder, and a crash reporting provider placeholder.
8. THE Privacy_Page SHALL include sections for Advertising, Analytics and Game Balancing, Cloud Save/Profiles/Leaderboards/Friends, and Purchases.
9. THE Privacy_Page SHALL include a "Data Retention" section describing general retention practices.
10. THE Privacy_Page SHALL include a "Data Deletion and Account Requests" section with a link to the Data_Deletion_Page and the support email address.
11. THE Privacy_Page SHALL include a "Children" section stating the apps are not directed at children under 13.
12. THE Privacy_Page SHALL include sections for Security, International Users, Changes to This Policy, and Contact.
13. THE Privacy_Page SHALL not include excessive legal boilerplate or disclosures beyond what is expected from a small independent publisher.
14. THE Privacy_Page SHALL use a plain, factual tone without defensive language or legalese.

### Requirement 8: Support Page — App Store and Google Play Support URL

**User Story:** As a player, I want a support page with clear contact information, so that I can get help with issues in apps or games published by this company.

#### Acceptance Criteria

1. THE Support_Page SHALL display a title of "Support" and a brief introductory statement.
2. THE Support_Page SHALL display the support email address as the primary contact method.
3. THE Support_Page SHALL include guidance on what information to include when contacting support (app or game name, device, operating system, description of the issue).
4. THE Support_Page SHALL include a section about purchases explaining that purchases are processed by Apple or Google and directing users to the appropriate store for refund requests.
5. THE Support_Page SHALL include links to the Privacy_Page and Data_Deletion_Page for privacy and data-related requests.
6. THE Support_Page SHALL include a response time expectation.

### Requirement 9: Data Deletion Page — Google Play and Apple Compliance

**User Story:** As a player, I want a data deletion page, so that I can request deletion of my data as expected by Google Play account/data deletion requirements and Apple account deletion guidelines.

#### Acceptance Criteria

1. THE Data_Deletion_Page SHALL display a title of "Data Deletion" and a brief introduction explaining the purpose of the page.
2. THE Data_Deletion_Page SHALL include instructions on how to submit a data deletion request, specifying the support email address and what information to include in the request.
3. THE Data_Deletion_Page SHALL include a section describing what data may be deleted upon request.
4. THE Data_Deletion_Page SHALL include a section describing what data may be retained after a deletion request (e.g., anonymized analytics, purchase records required by platform providers).
5. THE Data_Deletion_Page SHALL include a warning about purchase history, explaining that deletion of game data does not affect purchase records held by Apple or Google.
6. THE Data_Deletion_Page SHALL include information about identity verification for deletion requests.
7. THE Data_Deletion_Page SHALL include information about expected timing for processing deletion requests.

### Requirement 10: Placeholder Values

**User Story:** As a developer, I want clearly marked placeholders in the source files, so that I can find and replace them with real values before deployment.

#### Acceptance Criteria

1. THE Website SHALL use the placeholder `[COMPANY_LEGAL_NAME]` wherever the company legal name appears, pre-filled with "Onidev LLC".
2. THE Website SHALL use the placeholder `[SUPPORT_EMAIL]` wherever the support email appears, pre-filled with "support@onidev.io".
3. THE Website SHALL use the placeholder `[EFFECTIVE_DATE]` for the privacy policy effective date, pre-filled with "May 6, 2026".
4. THE Website SHALL use the placeholder `[COMPANY_COUNTRY_OR_STATE]` for the company location, pre-filled with "Maryland, USA".
5. WHEN analytics or crash reporting providers are referenced, THE Privacy_Page SHALL use descriptive placeholder text such as "an analytics provider" or "a crash reporting provider" rather than naming a specific product, since the provider has not been finalized.

### Requirement 11: Deployment Documentation

**User Story:** As a developer, I want deployment documentation included with the generated files, so that I know how to deploy the site to GitHub Pages and configure DNS.

#### Acceptance Criteria

1. WHEN the website files are generated, THE output SHALL include a summary of all files created.
2. WHEN the website files are generated, THE output SHALL include a list of all placeholder values and their pre-filled defaults.
3. WHEN the website files are generated, THE output SHALL include a GitHub Pages deployment checklist.
4. WHEN the website files are generated, THE output SHALL include a Namecheap DNS configuration checklist.
