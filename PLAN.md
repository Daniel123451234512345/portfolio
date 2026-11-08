# PLAN: Daniel Ho Portfolio v2, a modern landing page

## Goal
Rebuild the portfolio from scratch as a sleek, modern landing page in the style of Linear, Vercel or Framer, instead of a classic résumé one-pager.

## Build
- **Fresh start:** rewrite `index.html`, `styles.css` and `script.js` completely. Don't reuse the old layout or CSS. Stay with plain HTML/CSS/JS and no build step so it still runs on GitHub Pages. Keep the `#about` id and the `<h1>Daniel Ho</h1>`.
- **Look (dark-first):** near-black background `#0B0B0F`, white text, muted gray `#9A9AA5`. Burnt orange `#BF5700` → amber `#FF8A3D` is the brand gradient on the headline highlight, buttons and glows. Add a faint dot-grid background and a blurred orange "aurora" glow behind the hero, plus glassy cards (`rgba(255,255,255,.04)` fill, 1px `rgba(255,255,255,.08)` border, 16–20px radius). Fonts: **Inter** for body text, **Space Grotesk** for headings. Headings are large and tight: the hero is `clamp(2.75rem, 8vw, 6rem)` with -0.03em letter spacing. Keep a light-mode toggle, remembered in localStorage, with the same layout on a warm off-white.
- **Nav and hero:** a floating pill-shaped nav (blurred glass, centered, sticky) with the DH logo, links and a small "Let's talk" CTA. Hero contents, top to bottom:
  - A small badge reading "● Open to Summer 2027 internships".
  - The headline "I turn messy data into *clear stories*." with the italic part in the gradient.
  - The subline "Daniel Ho · Statistics & Data Science @ UT Austin".
  - Two CTAs: "See my work" (solid) and "Get in touch" (ghost).
  - An animated SVG scatter plot whose regression line draws itself on load.
- **Social-proof strip:** "Tools I work with" above an infinite-scrolling marquee of tool names: Python, R, SQL, pandas, scikit-learn, tidyverse, ggplot2, Jupyter, Git, Docker, Claude Code, Switch. It pauses on hover.
- **Stats row and bento projects:** a row of 3 big-number stats that count up when scrolled into view: "4 projects shipped", "12+ datasets wrangled" and "1 AI crew run from my phone". Then a **bento grid** of projects. Pocket Crew is the large featured tile: a mock chat bubble ("builder → tester → ship it ✅"), tags and a GitHub link to github.com/Daniel123451234512345/pocket-crew. Three smaller tiles cover Austin Bikeshare Demand, Longhorn GPA Explorer and the March Madness Bracket Model, each with a tiny inline SVG chart (line, bars or bracket) and tags. Tiles get a cursor-following glow on hover.
- **About and how I work:** a split section with 2 short paragraphs on the left (same facts as before: first-year at UT Austin, Python/R, AI agents, learning statistical modeling). On the right, a 3-step "How I work" list: *Ask a sharp question → Wrangle & model → Ship a clear story*. Below it is a compact timeline: UT Austin B.S. 2026–2030 and Flip the Switch Hackathon, Nov 2026.
- **Final CTA and footer:** a big gradient-bordered card reading "Let's build something with data." with email, GitHub and LinkedIn buttons and a "Copy email" button that shows a "Copied!" toast. The minimal footer reads "© 2026 Daniel Ho · Built with a Pocket Crew of AI agents."
- **Motion and mobile:** sections fade up on scroll (IntersectionObserver), and all motion is off under `prefers-reduced-motion`. Mobile-first: on screens under 720px the bento grid becomes 1 column, the nav collapses to the logo plus a menu button that opens a full-screen sheet, and the hero headline still fits on 375px screens.

## Done when
- The page looks clearly different from v1: dark-first, with a glass pill nav, an aurora hero with the gradient headline, a tools marquee, a stats row, a bento project grid and a final CTA card.
- The regression line draws on load, the stats count up when scrolled into view, the marquee loops, and with reduced motion turned on, all animation is off and the content is still visible.
- At 375px nothing scrolls sideways, the bento grid is one column, and the menu sheet opens, closes on link tap and closes on Esc.
- The light/dark toggle works, is remembered after a reload, and small text meets WCAG AA contrast (4.5:1) in both themes.
- All nav links scroll to real sections, the Pocket Crew link opens the real repo, "Copy email" copies the address and shows the toast, and there are no console errors or lorem ipsum.

## Assumed
- "From scratch" means a new design and new code. The content stays the same: name, UT Austin, the 4 projects (1 real, 3 placeholders), email ddh2962@eid.utexas.edu and a `#` placeholder for LinkedIn.
- Dark mode is the default look, because that's what reads as "modern landing page". Light mode stays as a toggle.
- The stat numbers are friendly estimates for Daniel to adjust.
- No photo, no resume PDF and no contact form (static site only).
- The approved v1 hasn't shipped (there's no remote yet), so v2 simply replaces it.
