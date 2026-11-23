# SCALE Business Consultancy website

A lightweight, static website built with HTML, CSS, and JavaScript. The four main pages are Home, About, Services, and Contact. A fifth page contains a provisional privacy notice.

## Preview

Run `npm run build`, then `npm run preview`. Open `http://localhost:5500/`.

You can also open `index.html` directly, though a local server better reflects deployment.

## How to Customize Your SCALE Website

All business details, services, draft projects, optional sections, social links, and form settings live in `config.mjs`. Edit it, then run `npm run build` to regenerate the HTML pages. The visual system is in `style.css`; interaction and form logic are in `script.js`.

1. **Logo:** Place the official logo in `assets/` and set `site.logo` to its relative path. The current wordmark is explicitly a temporary placeholder. Replace the favicon with an approved brand asset too.
2. **Colors and typography:** Change the CSS variables and font stacks at the top of `style.css`. The current restrained green and neutral treatment is a design draft; compare it with the final brand guide before launch.
3. **Page content:** Update the page copy in `build.mjs`, then rebuild.
4. **Services:** Update `site.services` in `config.mjs`. They appear on Home and Services.
5. **Projects:** Verify each relationship, contribution, permission, and image. Add an authentic image path, set its `approved` field to `true`, then enable `site.features.portfolio`.
6. **Contact:** Enter verified email and phone details in `config.mjs`. Social links are already configured. A WhatsApp CTA requires a confirmed number and its feature flag.
7. **Enquiry form:** Set `site.formEndpoint` to a secure POST endpoint that accepts JSON and returns a successful HTTP status after storing or delivering the enquiry. The form remains disabled until configured. Review the privacy notice and service terms before enabling submissions.
8. **SEO:** Set `site.siteUrl` to the final absolute site URL ending in `/`, then rebuild. This enables canonical URLs and generates `sitemap.xml`. Add a verified social preview image and replace the provisional favicon before launch.
9. **Optional sections:** Feature flags default to off. Only enable sections when approved real content is present. Client claims, metrics, testimonials, team titles, and pricing are intentionally unpublished.
10. **Deploy:** Run `npm run build`, then upload the generated HTML, `style.css`, `script.js`, `assets/`, `robots.txt`, and `sitemap.xml` (once generated) to any static host. On GitHub Pages, set `site.siteUrl` to the published base URL including the repository path and trailing slash.

## Launch checklist

- Supply the official SCALE logo, approved photography, and final brand guide.
- Confirm the business URL, email, phone/WhatsApp, and legal privacy wording.
- Configure and verify a secure enquiry endpoint before enabling the form.
- Review service descriptions and any portfolio publication approvals.
- Check the final deployment on mobile and desktop, including navigation, form delivery, and social previews.

No third-party JavaScript dependency is required. Google Fonts are loaded through CSS; host licensed font files locally if complete independence from external requests is needed.
