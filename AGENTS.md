# Repository guidance

## Purpose

This repository is the static GitHub Pages site for Macanta dev. Keep the implementation lightweight: plain semantic HTML, one shared stylesheet, and no build step or runtime dependency unless the user explicitly expands the scope.

## Site contract

- Keep Apps at `index.html`, About at `about/index.html`, and Blog at `blog/index.html`.
- Use relative navigation and asset paths that work under the `/macanta-dev/` GitHub Pages project path.
- Reuse the shared header, footer, favicon, color tokens, spacing, and responsive patterns across pages.
- Give each page one descriptive `h1`, a unique title and description, its own canonical URL, and the correct `aria-current="page"` navigation item.
- Preserve keyboard-visible focus, the skip link, semantic landmarks, reduced-motion handling, readable contrast, and 320px reflow without horizontal scrolling.

## Content and privacy

- Publicly identify the developer as **Anton** and the publisher as **Macanta dev**.
- Use `Anton <4217692+macanton@users.noreply.github.com>` for author and committer metadata. Keep the surname, physical address, private email, and other private details out of repository history, source, and rendered content unless the user explicitly supplies and approves them for publication.
- Treat DzenPhone and LearnMyWords as placeholders. Use “Details coming soon” until verified product details are provided.
- Keep the Blog page in its current coming-soon state until real post content is supplied; do not invent posts, dates, product claims, platforms, or release information.

## Security

- Keep the site free of JavaScript and third-party resources unless the user explicitly expands the scope and the additions receive a security review.
- Keep the restrictive Content Security Policy and `no-referrer` policy in every HTML page. Any new resource must be granted only the minimum CSP permission it needs.
- GitHub Pages controls HTTP response headers. If response-level anti-framing, MIME-sniffing, or permissions policies become requirements, move to a host that supports custom security headers instead of adding ineffective meta equivalents.

## Verification

Before handing off a change:

1. Serve the repository root with a local static server.
2. Load `/`, `/about/`, and `/blog/` directly and through navigation.
3. Check desktop and 320px layouts for clipping or horizontal overflow.
4. Walk the navigation with a keyboard and confirm visible focus and the active-page state.
5. Confirm shared CSS and the favicon load from every route.
6. Confirm every HTML page enforces the CSP and referrer policy without browser console violations.
7. Run `git diff --check`, search changed public files for unintended personal data, and inspect every outgoing commit’s author and committer metadata.

GitHub Pages deploys from the root of `main`. Push and verify the public routes only when publishing is part of the request.
