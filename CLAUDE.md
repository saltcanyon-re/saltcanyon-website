# SaltCanyon website (saltcanyon.com)

The public website for SaltCanyon, a Draper, Utah commercial real estate firm with three divisions: Investments, Property Management, and Brokerage. Read this whole file before making changes.

## How the site works

- It is one static page: `site/index.html`, with images in `site/img/`. No framework, no build step. All CSS and JavaScript are inside `index.html`.
- Hosting is Netlify (team "SaltCanyon", project `saltcanyon`). `netlify.toml` publishes only the `site/` folder.
- **Every push to `main` publishes to saltcanyon.com automatically.** Each publish costs 15 Netlify credits (free plan: 300 per month). Batch related edits into one commit and push once, not after every small change.
- Preview locally before pushing: run `python3 -m http.server 8765` from the `site/` folder and open http://localhost:8765. Check desktop (1440px wide) and phone (375px wide).
- To undo a bad publish, revert the commit and push. Netlify also keeps every past deploy and can roll back from its dashboard.

## Do not touch

- DNS lives in GoDaddy (not in this repo). Never change DNS records. The MX, SPF, DKIM (`google._domainkey`), and DMARC (`_dmarc`) records protect company email.
- The contact form uses Netlify Forms. Keep `name="contact"`, `data-netlify="true"`, `netlify-honeypot="bot-field"`, the hidden `form-name` input, and the existing field names (`name`, `company`, `email`, `phone`, `topic`, `message`). Submissions are emailed to management@saltcanyon.com. Adding a new `<option>` to the topic list is fine.
- Tenant and investor portal links go to AppFolio: `https://saltcanyon.appfolio.com/connect/users/sign_in?portfolio_uuid=`.

## Design rules (the owners have been specific)

- Look: modern, high-end, masculine, boutique-firm. Monochrome: black `#0b0b0c`, off-white `#f5f5f3`, greys. No accent color.
- Type: Geist for everything, Geist Mono for small uppercase labels. Large, tight headlines. Square buttons and cards, thin lines, no shadows, no rounded corners.
- Photos are full color. The only black-and-white effect is the hover on the property-type cards.
- Logo: the black-and-white SaltCanyon logo (`img/logo-bw-white.png`). Browser-tab icon: black canyon mark on transparent (`img/favicon-*.png`).
- Rejected before, do not bring back: tan, brown, or cream colors; serif fonts; orange striped bands; the colored division logos; photo captions under images; a "plain-language leasing" table.
- Division order everywhere (menu, cards, sections, footer, contact topics): **Investments, Brokerage, Property Management**.
- Copy speaks to the customer's benefit (investors, owners, tenants, buyers, sellers). Short, plain sentences. No invented statistics, testimonials, or client counts.
- The 1031 exchange copy must keep the line that SaltCanyon does not provide tax or legal advice.

## Photos and what they show

| File | Property | Where used |
|---|---|---|
| `hero-74-building.jpg` | SaltCanyon's own Draper office building (74 E 13065 S), which SaltCanyon built | Slideshow 1, "We know these streets" |
| `invest-land-wasatch.jpg` | Industrial land, Draper | Slideshow 2 |
| `hero-hurricane-park.jpg` | Northridge Industrial, Hurricane, Utah (not St. George) | Slideshow 3, Commercial condos card |
| `invest-bluffdale-condos.jpg` | Bluffdale, 6,000 sq. ft. industrial condo units | Investments |
| `brokerage-flex-aerial.jpg` | Murray, 1,500 to 5,000 sq. ft. units (orange trim) | Property Management |
| `type-flex-aerial.jpg` | Logan, 70,000+ sq. ft. | Brokerage |
| `pm-brick-flex.jpg` | Draper Cove (red brick "5" building) | Flex industrial card |
| `development-framing.jpg` | Construction framing | New development card |
| `type-single-tenant-udk.jpg` | UDK building front (billboard cropped out) | Single-tenant card |
| `contact-saltcanyon-entrance.jpg` | SaltCanyon sign at the Draper office entrance | Contact |

New photos: export around 1,600 to 2,200 px wide, JPEG quality about 78, into `site/img/`. Location captions on photos use the `media-cap` style ("City, Utah • detail").

## Accessibility and quality

- Every image needs real `alt` text. Keep text contrast at WCAG AA or better.
- No horizontal scrolling at phone width.
- Respect `prefers-reduced-motion` (already handled in the CSS and slideshow script).
