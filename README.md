# Macanta dev

Static HTML and CSS for [macanta.dev](https://macanta.dev/).

## Hosting

Cloudflare Pages project: `macanta-dev`

- Preview: https://macanta-dev.pages.dev/
- Source: `macanton/macanta-dev`, production branch `main`
- Framework: None
- Build command: `exit 0`
- Build output directory: `.` (repository root)
- Root directory: leave blank

Pushing to `main` automatically deploys to Cloudflare Pages. The site has no
application build step or runtime dependencies. `_headers` sets the HTTP security
headers; each HTML page also retains its CSP and referrer meta tags.

Add custom domains through the Pages project's Custom domains screen. The
`CNAME` file is retained for the existing GitHub Pages fallback; it does not
configure Cloudflare. Keep GitHub Pages available until the custom domain's
Cloudflare deployment and HTTPS have been verified.

## Local preview

Run `python3 -m http.server 8000` from the repository root. Check `/`, `/about/`,
and `/blog/`, including relative links, shared styles, and the favicon. Python's
server does not apply `_headers`; verify response headers on Cloudflare.

## References

- [Cloudflare static HTML deployment](https://developers.cloudflare.com/pages/framework-guides/deploy-anything/)
- [Cloudflare custom domains](https://developers.cloudflare.com/pages/configuration/custom-domains/)
