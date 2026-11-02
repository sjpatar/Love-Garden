# Garden of Love — Project Specification

**Status:** Single source of truth for requirements and implementation tracking  
**Project type:** Premium interactive romantic digital gift website  
**Last reviewed:** 2026-11-01

## 1. Product vision

Create an enchanted, lovingly art-directed flower garden that opens from a premium digital gift card. The experience should communicate affection, warmth, intimacy, elegance and fantasy. It must feel like a place to explore—not a conventional webpage, generic Valentine's template, emoji composition, or collection of disconnected cards.

The finished experience should be romantic without being cheesy, magical without looking childish, and sophisticated without losing its sweetness. Every flower should feel part of the environment, every interaction should feel rewarding, and the recipient should want to explore, screenshot and remember it.

## 2. Technology and architecture

- HTML5, CSS3 and vanilla JavaScript (ES6+); no React, Vue, Angular or comparable framework.
- Separate, maintainable `index.html`, `style.css` and `script.js` files.
- CSS custom properties for theme values and reusable classes/functions.
- CSS keyframes for lightweight decorative motion; `requestAnimationFrame` only where continuous scripted motion is justified.
- HTML Audio API for music and optional sound effects.
- Google Fonts may be used for typography.
- Transparent PNG/WebP assets; SVG only for appropriate decorative elements.
- One clearly identifiable JavaScript personalization/configuration object containing:
  - `HER_NAME`
  - `HER_NICKNAME`
  - `YOUR_NAME`
  - `OPENING_GREETING`
  - `FLOWER_MESSAGES`
  - `FINAL_LOVE_LETTER`
  - `BACKGROUND_MUSIC_PATH`
- Keep personal details as editable placeholders; do not invent personal information.
- Use local assets only in the finished site. Never hotlink unstable third-party image URLs.

## 3. Visual direction

### Palette

| Token | Value | Use |
|---|---|---|
| Blush pink | `#F8DCE7` | Primary atmosphere |
| Baby pink | `#FCEAF1` | Light surfaces |
| Rose pink | `#E9A4BE` | Interactive accents |
| Soft lavender | `#E9DDF5` | Fantasy highlights |
| Warm ivory | `#FFF9F2` | Cards and readable surfaces |
| Sage green | `#B6CBB0` | Foliage |
| Muted gold | `#D8B779` | Borders, seal and details |
| Deep rose | `#A95778` | Contrast and headings |

Use soft cinematic lighting, layered depth, natural shadows, delicate gold accents, subtle gradients, atmospheric particles, editorial typography and intentional composition. Use botanical framing and vintage botanical details where appropriate.

Avoid excessive neon, flat or cheap-looking gradients, overly bright backgrounds, generic Bootstrap-style cards, excessive rounded UI, cartoonish default graphics, emoji flowers/butterflies, clutter and animation without purpose.

### Typography

Prefer a restrained combination of:

- Cormorant Garamond for romantic headings.
- Playfair Display for editorial accents.
- DM Sans for body copy and controls.
- Great Vibes or Parisienne for handwritten signatures.

Maintain hierarchy, readable contrast, comfortable line spacing and responsive text sizing.

## 4. Experience structure and scenes

### Scene 1 — Romantic gift card

Full-screen introductory invitation on a dreamy blush-pink background. Include a delicate floral frame, floating sparkles, softly animated petals, layered shadows/depth, an elegant envelope or invitation composition, and a heart-shaped wax seal.

Required copy and editable placeholders:

- Greeting: `To My Favourite Person...` (or configurable `OPENING_GREETING`)
- Subheading: `I made a little world for you. Every flower has something to tell you.`
- Personalization: `[HER_NAME]`, `[YOUR_NICKNAME_FOR_HER]`
- Primary action: `Open Your Little Garden` (the master brief also refers to a `Let's Go` label; choose one consistent final label)

The button is a rounded muted-rose control with refined hover, glow and press states. On activation: animate the envelope/card opening, reveal glowing light, transition cinematically into the garden, start music after the user gesture where permitted, and trigger the garden entrance animation. Use an in-page scene transition; do not reload.

### Scene 2 — Enchanted garden

Full-screen fantasy environment that feels like a real illustrated garden. Use layered depth:

1. Dreamy pink sky and soft warm light.
2. Distant garden/landscape and optional moving clouds.
3. Middle-ground vegetation and distant flowers.
4. Main interactive flowers.
5. Foreground leaves and flowers.
6. Butterflies, petals, particles and atmospheric effects.

Include natural greenery, layered shadows, atmospheric perspective, subtle desktop pointer parallax where it does not interfere with clicks, floating pollen/dust, occasional falling petals, gentle light rays, sparkles and restrained foliage movement. Keep the composition balanced and uncluttered.

### Scene 3 — Living butterflies

Use actual transparent animated butterfly assets wherever suitable. Minimum target: five visually compatible animations covering pink, blue, yellow, white and monarch-style butterflies. Prefer transparent GIF, animated WebP or APNG with genuine looping wing motion, no rectangular background, no watermark and reasonable file size.

Butterflies must fly independently with varied size, depth, speed, altitude, rotation, curved trajectories, direction changes, vertical float, hovering and occasional flower landing. Use CSS transforms and JavaScript-generated motion paths/independent loops; do not use simple straight-line sliding. Do not recreate wing animation when a downloaded asset already has proper animated wings. If suitable animated files cannot be sourced, use transparent static PNGs with independently animated wing layers as a documented fallback.

Keep butterflies away from important text and interaction targets. Pause or reduce animation when the tab is hidden and honor `prefers-reduced-motion`.

### Scene 4 — Interactive flowers and messages

Every flower is independently clickable and touch-friendly. On hover, enlarge slightly, glow, lift and expose an intentional interactive cursor. On click, trigger bloom emphasis plus small sparkles/petals and open a message popup.

Each flower has a unique configurable romantic message. Use a JavaScript data object rather than scattered hardcoded popup content. Message categories should include love, missing you, “Hi wifey”, kisses, virtual hugs, beauty, favorite person, wishing you were here, and forever/always.

Seed messages from the brief:

- Sunflower: “Whenever I think of happiness, I somehow end up thinking of you. 🌻”
- Pink rose: “I love you more than words could ever explain.”
- Red rose: “If I had to choose again, I'd still choose you. Every single time.”
- White rose: “You make even the simplest moments feel beautiful.”
- Tulip: “Just a little reminder that someone is completely crazy about you.”
- Daisy: “Hi, wifey! Sending you the biggest hug ever.”
- Peony: “I wish I could pause time whenever I'm with you.”
- Lavender: “Close your eyes for a second. Imagine me holding you close.”
- Lily: “You make my world softer, warmer and happier.”
- Orchid: “You're my favourite kind of beautiful.”
- Lotus: “No matter what happens, you will always have a special place in my heart.”
- Cherry blossom: “I wish I could collect every beautiful moment with you.”

Add unique messages for every remaining variety; do not repeat messages.

Popups are miniature luxury love letters: ivory or frosted-glass surface, delicate floral border, soft pink shadow, refined typography, subtle texture, small heart, corresponding flower illustration, polished entrance/exit animation, and an accessible close control.

### Scene 5 — Secret surprises

Include a small number of discoverable but unobtrusive secrets:

- Hidden heart: `Psst... I love you more than you know.`
- Special flower: `Sending you a million kisses!`
- Glowing star with a surprise message.
- Floating envelope opening a longer love letter.

Do not overwhelm the garden with hidden controls.

### Scene 6 — Final love letter

Provide a discoverable floating envelope or glowing heart that opens a large/full-screen elegant letter. Include:

- Heading: `A Little Something From My Heart`
- Body placeholder: `[YOUR_PERSONAL_LOVE_LETTER]`
- Closing: `With all my love,` and `[YOUR_NAME]`
- Floral decorations, handwritten-style signature, and final animated heart or bouquet reveal.

This is the emotional highlight of the experience.

## 5. Flower collection and asset requirements

Use high-quality isolated transparent PNG or WebP botanical artwork—not emojis or basic CSS shapes. Prefer 1024px+ source dimensions, consistent watercolor or semi-realistic illustration style, no watermarks, no unwanted white backgrounds, no borders/artifacts, and no incompatible mixing of styles. Use stems/leaves for some assets and individual heads for others; vary scale, orientation and placement so flowers grow from the garden rather than appear as stickers.

Required varieties:

1. Pink roses
2. Red roses
3. White roses
4. Yellow sunflowers
5. Pink tulips
6. Yellow tulips
7. White tulips
8. White daisies
9. Pink peonies
10. White lilies
11. Purple lavender
12. Pink orchids
13. Hibiscus
14. Lotus flowers
15. Cherry blossoms
16. Bluebells
17. Hydrangeas
18. Carnations
19. Magnolias
20. Poppies
21. Jasmine
22. Cosmos flowers
23. Forget-me-nots
24. Baby's breath
25. Mixed floral bouquets

Flowers sway independently with varied duration/delay and species-specific movement. Where practical, animate stems and heads separately, add subtle rotation/scaling and occasional bloom effects. Keep motion elegant and restrained.

## 6. Asset acquisition, structure and manifest

Inspect assets before acquiring anything. Prefer sources with clear royalty-free/usage permissions, including the supplied flower and butterfly sources (InfyPNG, UsefulPix, CleanPNG, PurePNG, Vecteezy, Giphy, Tenor, Pixabay, Heritage Type) and other suitable sources where licensing is clear. Do not bypass logins, paywalls or anti-bot controls. Do not silently replace missing artwork with emojis.

Record every asset in `assets/asset-manifest.json` with filename, category, source website, original source page, format, dimensions, transparency, animation status, licence/usage information and attribution requirements.

Required/recorded directory structure:

```text
assets/
├── flowers/
│   ├── roses/
│   ├── tulips/
│   ├── sunflowers/
│   ├── daisies/
│   ├── peonies/
│   ├── lilies/
│   ├── lavender/
│   ├── orchids/
│   ├── hibiscus/
│   ├── cherry-blossoms/
│   └── other/
├── butterflies/
│   ├── animated/
│   └── static/
├── petals/
├── leaves/
├── backgrounds/
├── decorations/
├── music/
└── sounds/
```

Use descriptive local filenames such as `pink_rose_01.png` and `monarch_butterfly_01.webp`. Verify file existence, corruption, dimensions, transparency, animation frame count, file size and local loading. Optimize dimensions/formats, preload critical visuals, and lazy-load non-critical images.

## 7. Audio

Use `assets/music/background.mp3` as the configurable default path. It must be a permitted soft romantic instrumental with gentle piano, music-box tones, ambient textures and/or delicate strings; no copyrighted commercial recording without permission.

Start only after the first user interaction and handle autoplay restrictions gracefully. Provide a persistent floating music control with play/pause and subtle volume control, gentle fade-in/fade-out, comfortable volume, state persistence across scenes and no restart when opening popups. Gracefully handle a missing audio file. Optional quiet sound effects may accompany envelope opening, flower clicks, popup opening and secrets.

## 8. Responsive design and accessibility

Support desktop, laptop, tablet, Android and iPhone layouts intentionally—not merely a shrunken desktop.

- No horizontal overflow.
- Reposition flowers intelligently and avoid overlapping targets.
- Preserve butterflies and depth composition.
- Fit popups to the viewport.
- Use touch-friendly buttons and flower hit areas.
- Maintain readable text and scalable background layers.
- Reduce particle counts and expensive effects on weaker/mobile devices.
- Use semantic HTML, meaningful alt text, keyboard navigation and visible focus states.
- Dialogs must manage focus, close via a clear button and `Escape`, and return focus appropriately.
- Respect reduced-motion preferences and provide a usable non-motion experience.
- All controls and interactive elements must have accessible names and sufficient contrast.

## 9. Performance and quality engineering

- Animate primarily `transform` and `opacity`.
- Avoid unnecessary DOM manipulation, layout recalculation, duplicate listeners and memory leaks.
- Use event delegation where appropriate.
- Pause/reduce scripted animation when the page is hidden.
- Handle missing image/audio assets gracefully.
- Preload important assets and lazy-load non-critical ones.
- Keep animation lightweight and smooth on mid-range phones.
- Ensure all visible controls work; no dead buttons, broken paths, accidental reloads or console errors.
- Preserve useful existing architecture and make related changes together.

## 10. Quality assurance and acceptance criteria

Test the actual rendered website in a browser at desktop and narrow mobile sizes. Inspect and correct:

- Premium opening card, envelope/wax-seal sequence and cinematic transition.
- Layered, immersive garden composition and depth.
- Botanical artwork quality, transparency and local paths.
- Independent flower sway and click/bloom behavior.
- At least five compatible butterfly assets or the documented static fallback; genuine wing motion where available; natural varied flight.
- Petals, pollen, dust, light rays, clouds, foliage and sparkles remaining subtle.
- Elegant message popup content and close behavior for every flower.
- Music toggle, volume, fade behavior, interaction restrictions and missing-file handling.
- Secret heart/star/flower/envelope interactions.
- Final love letter and closing animation.
- Responsive mobile layout, touch targets, popup fit and no overflow.
- Keyboard navigation, focus management, `Escape`, reduced motion and readable contrast.
- No broken images, missing asset paths, console errors or unfinished placeholder behavior except intentionally editable personal fields.

## 11. Implementation checklist

### Completed

- [x] Consolidated the supplied project brief, refinement directives, asset task and master command into this specification.
- [x] Recorded the required visual direction, scenes, flower varieties, butterfly requirements, audio, responsiveness, architecture, performance, accessibility and QA criteria.
- [x] Recorded the required asset directory structure.
- [x] Marked personal information as editable placeholders.
- [x] Implemented 18 individually clickable flowers, including pink, yellow and ivory tulips.
- [x] Implemented the local two-scene experience, responsive styling, personalization configuration, flower notes, secrets, love letter, music control and reduced-motion handling.
- [x] Implemented a fully local visual fallback with transparent inline botanical SVG artwork, CSS wing-flapping butterflies, petals, particles and layered garden atmosphere.
- [x] Added `assets/asset-manifest.json` documenting the fallback and planned licensed asset replacements.
- [x] Added the complete empty asset directory tree so licensed replacements can be dropped into stable paths.
- [x] Browser-tested the opening transition, flower message popups, popup closing, final love letter, hidden heart, music fallback notification, and corrected a background-layer hit-area bug.
- [x] Added the user-provided audio file as `assets/music/background.mp3` and wired the existing music controls to it.
- [x] Set the public copy to universal recipient wording (`You`) and address the apology letter to `Love`; personal copy remains editable in the configuration.
- [x] Reworked butterfly visuals with layered wings, markings, antennae and varied flight; added a clickable flying apology butterfly and apology letter signed `Samar`.
- [x] Removed the garden signature footer at the user's request.
- [x] Refined welcome-card spacing/footer alignment and tightened butterfly centerlines after rendered visual inspection.
- [x] Refined tulip SVG shape to share the garden’s stem and foliage styling, moved the tulips into the visible portrait flower rows, and staggered them into a separate desktop meadow row.
- [x] Added asset cache versioning after the tulip update so deployed phones fetch the current script and responsive stylesheet.
- [x] Added 48 gently swaying grass tufts clipped across the full hillside; aligned the portrait header and anchored the action dock to the phone viewport.
- [x] Raised the green mountain meadow behind the complete flower bed so the flowers grow from the hillside rather than the pink sky.
- [x] Moved the interactive star beside the moon and added a brighter, reduced-motion-aware shine.

### Unfinished

- [ ] Replace fallback inline artwork with acquired/licensed transparent botanical PNG/WebP files where available.
- [ ] Create the asset directory tree and acquire/verify permitted local botanical, butterfly, decorative, background and audio assets.
- [ ] Expand `assets/asset-manifest.json` with provenance and verification metadata for any acquired files.
- [ ] Verify all garden interactions and accessibility behavior on current phone browsers.
- [ ] Implement the animated-asset-first butterfly strategy if compatible licensed animation assets are acquired.
- [ ] Replace inline fallback artwork with locally acquired/licensed botanical assets where available.
- [ ] Complete a separate narrow-mobile visual screenshot pass and replace fallback artwork with licensed PNG/WebP assets where desired.

Future development should read and update this file only when requirements or implementation status meaningfully change. Progress reports should remain concise and prioritize implementation.
