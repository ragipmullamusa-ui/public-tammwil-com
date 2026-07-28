# Tammwil

Institutional capital access platform for governed private-market deal review, originator submissions, investor access requests, and administrative oversight.

## Project Overview

Tammwil is a full-stack web platform designed to organize how private-market and corporate transaction opportunities are presented, reviewed, and accessed. It provides a public bilingual website for platform discovery and deal browsing, plus protected role-based workspaces for administrators, originators, and investors.

The product is built around controlled information release. Public users can view high-level opportunity summaries, while sensitive deal information and documents are available only through authenticated workflows and approved access states.

## Product Type

- Full-stack web application
- Public-facing platform
- Role-based dashboard system
- Server-rendered PHP and MySQL business application
- Private-market workflow and deal-access platform

No mobile application, desktop application, standalone REST API, payment system, or package-managed build pipeline was found in the reviewed project files.

## Main Capabilities

### Public Website

- Bilingual public experience for English and Arabic.
- Public pages for platform overview, originators, investors, sectors, about, how-we-work, news, contact, applications, authentication, and deals.
- Published deal browsing with filtering and search.
- Public deal cards and detail pages using slug-based URLs.
- Contact form and investor/originator application intake.
- Public news and content pages with metadata support.
- SEO helpers for canonical URLs, sitemap generation, and robots rules.

### Authentication and Account Access

- Email and password login.
- Session-based authenticated user state.
- Role-aware redirects after login.
- Logout flow with session regeneration.
- Active account checks.
- Password reset OTP storage and verification workflow.
- Separate protected workspaces for administrators, investors, and originators.

### Administrative Management

- Admin overview with platform activity and operational summaries.
- Application review for investor and originator onboarding.
- User creation and user management.
- Deal creation, editing, review, publishing, rejection, and change-request workflows.
- Investor access-request review.
- Contact message status management.
- CMS-style page metadata/content management.
- Translation and public settings management.
- Activity log review.

### Originator Workspace

- Originator dashboard with deal statistics and recent activity.
- Multi-step deal submission workflow.
- Bilingual deal content fields.
- Deal classification, location, ticket-size, currency, structure, and visibility inputs.
- Supporting document upload during deal submission.
- My-deals list with filtering and search.
- Deal detail view with workflow status, review notes, documents, status history, and activity.
- Profile and organization summary.

### Investor Workspace

- Investor dashboard with deal and access-request summaries.
- Published deal browsing with filtering.
- Locked and approved deal states.
- NDA-based access request workflow with signature capture.
- Approved-deal listing.
- Access-request tracking.
- Profile and mandate summary views.
- Document visibility based on approved access level.

### Content, Files, and SEO

- Database-backed language, translation, page, taxonomy, country, currency, deal, and news content.
- Deal images and document uploads.
- Document access levels for public, NDA-approved, and admin-only material.
- Randomized stored upload filenames with validation checks.
- Dynamic XML sitemap for public pages, deal pages, and news pages.
- Robots rules that exclude private workspaces and sensitive upload areas.

## User Roles

### Public Visitor

Can learn about the platform, browse public opportunity summaries, read public content, submit contact messages, and apply for platform access.

### Originator

Can submit opportunities, provide bilingual deal information, upload supporting documents, track review progress, and view admin-visible feedback where permitted.

### Investor

Can browse published opportunities, review anonymized summaries, request NDA-governed access, track access-request status, and view approved deal materials.

### Administrator

Can manage applications, users, deals, access requests, contacts, pages, translations, settings, and operational activity from a protected admin workspace.

## Technical Architecture

Tammwil is organized as a server-rendered PHP application with shared helper modules and role-specific workspaces.

The public website and dashboards share core services for configuration, database access, authentication, authorization, localization, translations, settings, SEO metadata, CSRF protection, validation, uploads, flash messages, and page rendering.

Public pages are rendered from PHP entry files and shared partials. Protected dashboard areas load role-specific wrappers, enforce authorization, process relevant POST actions, and render dashboard views inside shared layouts.

## Project Structure

The private production repository is organized conceptually as follows:

```text
Tammwil Platform
├── Public website
├── Admin workspace
├── Investor workspace
├── Originator workspace
├── Shared application layer
├── MySQL data model
├── Public assets and upload handling
└── Apache routing, SEO, robots, and sitemap support
```

This public repository is intentionally limited to a professional overview and does not include the private source tree.

## Technology Stack

### Frontend

- HTML5 rendered through PHP templates.
- CSS3 with design tokens and responsive layouts.
- Separate LTR and RTL stylesheets.
- Dark and light theme variables.
- Vanilla JavaScript for theme persistence, mobile drawers, dropdowns, filters, tabs, modals, steppers, upload rows, reveal behavior, and signature capture.
- SVG and WebP visual assets.
- Google Fonts used by public and dashboard interfaces.

### Backend

- Native PHP with strict typing in core helpers.
- Procedural, helper-oriented application structure.
- Server-side rendering.
- PDO-based MySQL access.
- Prepared SQL statements through shared database helpers.
- Session-based authentication.
- Role-based access control.
- CSRF token generation and verification.
- Password hashing and verification through PHP password APIs.
- Input validation and workflow-specific checks.
- File upload handling for images, documents, and signatures.

### Database

- MySQL/MariaDB relational database.
- InnoDB tables with `utf8mb4` character support.
- User, role, profile, application, deal, document, access request, activity, CMS, translation, taxonomy, geography, currency, team, and news data domains.
- Multilingual content model using language-specific records.
- Workflow status fields for applications, deals, access requests, documents, and related records.

### Server and Deployment

- Apache `.htaccess` routing for clean public deal and news URLs.
- Internal routing for the dynamic sitemap.
- Directory index protection.
- Internal application-folder blocking.
- Public robots and sitemap files.
- Configurable base URL and base path support.

## Security and Access

The project includes several security-oriented controls at the application and server-routing levels:

- Password hashing and password verification.
- Session regeneration on login and logout.
- Role-based authorization for protected workspaces.
- Account status checks.
- CSRF protection for POST workflows.
- Output escaping for rendered content.
- Prepared database statements.
- Form validation helpers.
- Upload validation and randomized upload filenames.
- Document access levels for restricted deal materials.
- Apache rules that block internal application folders and dotfiles.
- Activity logging for important administrative and workflow actions.

## Localization and Accessibility

- English LTR and Arabic RTL interfaces.
- Database-backed translation keys.
- Localized public pages, dashboard labels, taxonomies, countries, currencies, deals, and news content.
- Language switchers across public and dashboard layouts.
- Direction-aware styling for public pages and dashboards.
- Responsive layouts for desktop and mobile.
- Dark and light theme support with persisted user preference.
- Accessibility-oriented interface details such as `lang`, `dir`, `aria-label`, `aria-expanded`, `aria-current`, hidden states, and screen-reader labels in key navigation and control areas.

## Implementation Notes

The reviewed project files support a production-style server-rendered web platform. Some concepts exist only as schema, UI placeholders, or future-ready stubs, including standalone notification delivery, transactional email integration, and a separate API layer. These are not represented here as fully implemented production services.

## Live Project

- Live website: [https://tammwil.com/](https://tammwil.com/)

## Source Code Access

This repository is a public technical overview created for portfolio and professional presentation purposes. The production source code is maintained in a private repository and is not publicly distributed.

Access to the private source-code architecture may be considered when appropriate and formally authorized. For business, recruitment, partnership, or technical-review inquiries, please use the contact details below.

## Contact

- Email: [info@ideabat.com](mailto:info@ideabat.com)
- LinkedIn: [https://linkedin.com/in/ragipmullamusa](https://linkedin.com/in/ragipmullamusa)
- Portfolio: [https://ceo.ideabat.com](https://ceo.ideabat.com)

## Developed By

**Ragip Mullamusa**  
Full-Stack Software Engineer & Mobile Applications Developer

[Ideabat](https://ideabat.com)
