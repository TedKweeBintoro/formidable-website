# AGENTS: Adding a New Practice Page

Use this guide to add another anonymized practice area page and surface it on the homepage.

## Page skeleton
- Base from an existing practice page such as `epidemiology-cancer-research.html` (matches the anonymous tone and layout).
- Keep the top-of-file head block intact: Google Tag (`gtag.js`), charset/viewport, `<title>` as `Topic - Formidable Partners`, favicon, `styles.css`, Google Fonts, Font Awesome.
- Leave the fallback header/footer wrappers in place (`<div id="header-container">` and `<div id="footer-container">`); `script.js` swaps them with `includes/header.html` and `includes/footer.html`.
- Hero structure: `.expertise-hero` section with breadcrumb, `<h1>` title, intro paragraph, and a `contact-us-btn` linking to `contact`.
- Core content sections: repeat the `.content-section` + `.container` pattern with a `.section-header` and grids such as `.services-grid`, `.approach-steps`, `.case-list`, and finish with an `.expertise-cta` block pointing back to `/#expertise`.

## Build a new page
1) **Create the file**: duplicate an existing practice page or `practice-template.html`, rename with a short kebab-case slug (e.g., `perioperative-nursing.html`), and update the `<title>`/`<h1>`/breadcrumb text.
2) **Inline styles**: keep the standard gradient `linear-gradient(135deg, #1e3a8a 0%, #2563eb 100%)` for `.expertise-hero` and `.expertise-cta` to match other pages. Adjust grid min widths if needed; keep shared rules (body padding, `scroll-margin-top`, card hover styles).
3) **Content**: write anonymous role-driven copy (e.g., “Senior [Discipline] Expert”), use general credentials (MD, PhD, years of experience) and topic lists—no real names, employers, or client details.
4) **CTAs and links**: keep primary CTA to `contact`; secondary CTA back to `/#expertise`. Internal links omit `.html` (match `index.html` cards such as `href="epidemiology-cancer-research"`).
5) **Header/footer**: do not change the markup inside the fallback header/footer blocks; they must match `includes/header.html` and `includes/footer.html` so the dynamic loader can replace them cleanly.

## Wire it into the homepage
- **Areas of Expertise card**: in `index.html`, add an `.expertise-card` inside the `.expertise-grid` with icon, heading, short description, 3–4 bullets, and a `Learn More →` link that points to the new slug (no `.html`).
- **Footer services list**: optional but recommended—add the new link in `includes/footer.html` (and mirror in the fallback footer inside your new page if you keep that list up to date).
- **Team/case studies**: only add related entries if you have anonymous summaries that fit the existing pattern (generic titles, short blurbs, credential tags).

## Quick checks
- Open the new page in a browser: confirm header/footer render correctly (meaning `script.js` loaded them), hero gradient displays, grids stack cleanly on mobile, and all internal links resolve.
- Skim for any accidental real names or sensitive details; adjust to generic titles before publishing.

## Template
- Use `practice-template.html` as a starting point. It already includes the standard gradient, section scaffold (hero, expert profile, services, approach, case types, CTA), and fallback header/footer wrappers for the dynamic loader.

## Page tree (subject/topics)
```
Main pages:
  index.html
  contact.html
  thank-you.html
  404.html

Practice areas:
  accident-reconstruction.html
  acoustical-engineering-audiology.html
  analytical-chemistry-air-quality.html
  bankruptcy-restructuring.html
  defamation-media-impact.html
  economic-financial-analysis.html
  education-policy-leadership.html
  epidemiology-cancer-research.html
  fire-chemical-combustion-analysis.html
  life-care-planning.html
  ophthalmology.html
  orthopedic-surgery.html
  pathology.html
  perioperative-nursing.html
  perioperative-nursing-legal-nurse-consulting.html
  plastic-surgery.html
  radiology.html
  toxicology.html
  wage-hour-litigation.html
  neurology.html

Case studies:
  case-study-bankruptcy-analysis.html
  case-study-defamation.html
  case-study-epidemiology.html
  case-study-fire-and-chemical-reaction-analysis.html
  case-study-pediatric-ophthalmology.html
  case-study-solvency-analysis.html

Template:
  practice-template.html
```
