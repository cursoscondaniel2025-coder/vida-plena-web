# VIDA:PLENA — Design System

Family design system for two sister wellness brands run by the same team out of Cali-area Colombia:

- **Vida Plena — Centro Naturista**: a bricks-and-mortar naturopathic health store (supplements, homeopathy, in-store advisory), orange/leaf-gradient identity. Tagline seen across assets: *"Cuidamos de ti"*, *"Porque todos somos importantes."*
- **Khambú — Mercado Saludable**: a healthy-foods market/delivery brand (kombucha, organic groceries, artisanal snacks) from the same owner, teal/lime identity, WhatsApp-ordering + home delivery.

Both brands post daily social content (Instagram-style square/story graphics) built around the same handful of templates: promo/delivery announcements, inspirational quote cards, product/store photography, and dated/seasonal greeting cards. This system extracts the shared visual system and componentizes those templates.

A third mark, **Naturalia — Clínica Medicina Integral** (teal wordmark), was found alongside the source files with no further brand material; it's kept as a reference asset only (see Guidelines → Brand → "Related Mark: Naturalia") and not built out as its own brand.

**Sources provided:**
- Local folder `VIDAPLENA-LOREN/` — `1. BRANDING/1. LOGOS/` (logo masters, one Illustrator brand-manual PDF per brand), `2. POSTED/` (~280 published social posts/videos, the main source for copy tone and visual patterns).
- Four uploaded images: `LOGO VIDAPLENA 1080(1).png`, `LOGO_KHAMBÚ.jpeg` — the two brand marks used here. Two additional uploads (`WhatsApp Image 2026-08-01…jpeg` ×2) show an unrelated "NeuroBloom" logo with no connection to Vida Plena/Khambú found anywhere else in the source folder — **not used**; flagged for the user below.
- No Figma file, app codebase, or website codebase was attached — this system is built from brand-manual PDFs and published social assets, not product code. There is currently no digital product (app/site) to recreate; the two UI kits below recreate the *social post* templates instead.

## Index
- `styles.css` — root stylesheet, imports everything in `tokens/`
- `tokens/` — `colors.css`, `typography.css`, `spacing.css`, `fonts.css`
- `assets/logos/` — Vida Plena (color + white), Khambú (white-only), Naturalia (reference)
- `assets/backgrounds/` — the two signature page-wash textures
- `assets/photos/` — sample lifestyle/product photography
- `components/core/` — Button, Badge, Divider, Card, ProductCard, QuoteCard, SectionHeading, LogoLockup
- `guidelines/` — specimen cards for colors, type, spacing, brand marks (populates the Design System tab)
- `ui_kits/vida-plena/`, `ui_kits/khambu/` — interactive recreations of each brand's Instagram post templates
- `SKILL.md` — portable skill file for use in Claude Code

## Components
Button, Badge, Divider, Card, ProductCard, QuoteCard, SectionHeading, LogoLockup — see `guidelines` "Components" card and each component's `.prompt.md` for usage.

### Intentional additions
No component library or Figma file was provided, so this is a from-scratch set sized to what the social content actually needs (not a full app component library): a CTA button, label pill, base card, a product tile for market grids, a script-quote panel matching the recurring "Busca … salud …" post format, a heading block matching the recurring eyebrow+title+script pattern, and a brand-aware logo picker (Khambú's only wordmark file is white-on-transparent, so `LogoLockup` auto-chips it onto a dark surface when placed on a light page).

## Content fundamentals
- **Language & person**: Spanish (Colombia), always addressing the reader as **tú** — imperative/second-person copy ("Busca paz…", "No corras más", "Comprar por WhatsApp y recibir a domicilio es tu mejor opción"). Never usted, never "we/nosotros" framing to the customer.
- **Tone**: warm, encouraging, plain-spoken wellness talk — short punchy headline + one calm supporting sentence. Not clinical, not hype-y; reads like a caring local shop owner, not a pharma brand.
- **Structure**: nearly every post follows *hook headline (all caps or bold) → one-line benefit/CTA sentence → product or logo*. Numbers-led list posts are common ("5 Hábitos que benefician a nuestro corazón", "3 pasos").
- **Punctuation & casing**: inverted exclamation marks used correctly (¡No corras más!); headline words are often ALL CAPS for emphasis, body sentences are sentence case; a single word mid-sentence is frequently set in script/cursive for warmth ("obtendrás **salud**").
- **Emoji**: not used in on-brand copy — emphasis comes from color, caps, and the script accent word instead, not emoji.
- **Vibe**: nurturing, natural, accessible neighborhood wellness — leaves, hearts, hand-lettering, warm photography of real staff/product rather than polished stock-model imagery.

## Visual foundations
- **Color**: Vida Plena is warm — orange primary (`#E07E23`) with a green→teal leaf gradient and gold accent, on a white-to-warm-gold vertical page wash. Khambú is cool — teal primary (`#0F9C97`) with lime/green accents, on a white-to-mint-teal vertical page wash with a faint tone-on-tone leaf line pattern. Neutrals are warm off-whites/greys shared by both. Max two backgrounds per brand (solid white, or that brand's gradient wash).
- **Type**: Display/headline face is a bold geometric sans (originals: Nexa Bold / Barlow Black — substituted with **Poppins** 700–900, see note below); body copy is a rounded friendly sans (original: Roboto Medium / Minion — substituted with **Nunito** 500–700); a handwritten script (original: Afterglow / Cunia — substituted with **Caveat**) is reserved for one accent word or short phrase per composition, never full paragraphs.
- **Backgrounds**: vertical gradient washes (light-to-brand-color), occasionally with a very low-contrast tone-on-tone leaf/pattern overlay (Khambú only). No photographic full-bleed hero pattern beyond product/staff photography with a bottom gradient scrim for text legibility.
- **Imagery**: warm, real, unretouched phone/product photography — staff in branded polos, products on real shelves/counters, no studio stock-model gloss. Color grade is natural/warm, no heavy filters or grain.
- **Animation**: none observed — these are static social graphics; components use only simple hover feedback (see below), no motion language to inherit.
- **Hover state**: buttons darken slightly (`brightness(0.92)`) and lift 1px — a soft, subtle press, not a color swap.
- **Press/active state**: same darken, no scale/shrink effects seen in source; kept minimal by design.
- **Borders**: none as a decorative device — brand comes through in fills and gradients, not outlines (secondary buttons use a 2px brand-color outline only where a filled button would compete for attention).
- **Shadows**: a single soft, low-contrast drop shadow (`--shadow-card`) for elevated white panels (quote cards, product tiles); no inner shadows or glow effects.
- **Corner radii**: generously rounded — 16–24px on cards/photos, full pill (999px) on buttons and badges. No sharp corners anywhere in source material.
- **Cards**: white surface, 24px radius, soft shadow, no border — this is the one consistent "container" shape across both brands' quote and product posts.
- **Transparency/blur**: used only as a text-legibility scrim (a bottom-to-transparent black gradient over photography) — no frosted-glass/blur panels anywhere in source.
- **Layout**: content is centered and stacked for square (1:1) social posts; nothing fixed/pinned (no chrome to speak of — these are single static compositions, not scrollable UI).

## Iconography
No icon font, SVG icon set, or icon system was found in the source material — social posts rely on photography, the leaf/heart brandmark, and occasional 3D-rendered clipart (phone/delivery-box/map-pin illustrations used in "no corras más" delivery posts). Emoji are not used. Unicode symbols are not used as icons. If a UI needs functional icons (nav, form affordances) going forward, the nearest CDN match to this brand's soft, rounded illustration style would be **Phosphor Icons (regular weight)** or **Lucide** — flagged here as a substitution since the source defines no icon system at all.

## Fonts — substitution flag ⚠️
The Illustrator brand-manual PDFs list these original fonts: **Afterglow** (script), **Barlow Black**, **Cunia**, **Minion Variable Concept**, **Nexa Bold**, **Roboto Medium** — none of these font files were included in the attached folder (only rendered logo/post images). This system substitutes the nearest free Google Fonts equivalents:
- Nexa Bold / Barlow Black → **Poppins** (700–900) for display/headlines
- Roboto Medium / Minion → **Nunito** (500–700) for body copy
- Afterglow / Cunia → **Caveat** (500–700) for the script accent word

**Please share the real .otf/.ttf files if you have them (or confirm these substitutes are fine)** so headlines and logos match pixel-for-pixel with existing printed/social material.

## Caveats & ask
- No app or website codebase, and no Figma file, was attached for either brand — everything here is reconstructed from brand-manual PDFs and ~280 published social images/videos, so "components" and "UI kits" are original interpretations of the *social content system*, not a recreation of an existing product UI. If Vida Plena or Khambú has a website, ordering app, or Figma file, attach it and this system can be extended with real screens.
- Two of the four uploaded images (the "NeuroBloom" logo) don't match this brand and were not used — please confirm whether those were meant for a different project.
- Fonts are Google Fonts substitutes, not the real brand fonts (see above) — please share the originals if pixel-accuracy matters.
- The Naturalia mark was found in the same folder with no accompanying guidelines; treated as reference-only, not a third built-out brand.

**Please review the palettes, type substitutes, and the two post-kit recreations, and tell me what to refine — more post template variants, real product photography instead of the placeholders used here, the real fonts, or a different treatment for Naturalia if it's actually part of this family.**
