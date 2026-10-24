---
# Design tokens for michaelweihrouch.com and everything built alongside it.
# Source of truth: the live WordPress site (Radiate theme, wp-content/themes/radiate/style.css,
# no Customizer color overrides and no Additional CSS as of 2026-10-24).
# Each key below becomes a CSS variable --mw-<key>; the deployment build (michaelweihrouch-com/daemon)
# applies them to this dashboard. Keep values plain CSS.

color-background: "#ffffff"       # page background (body.custom-background, #content)
color-surface: "#ffffff"          # panels and cards
color-surface-hover: "#f3f6fc"    # row hover: a faint tint of the daemon accent
color-text-strong: "#333333"      # headings, names, the active item
color-text: "#444444"             # body text, titles, nav (Radiate default text color)
color-text-muted: "#767676"       # meta, timestamps, labels (Radiate uses #999999; darkened to pass WCAG AA)
color-accent: "#632E9B"           # links, hover, buttons, active states (Radiate primary purple)
color-accent-soft: "#632E9B33"    # accent-tinted borders and focus glows
color-daemon-accent: "#0a4bc4"    # the dashboard's accent: Daemon's brand blue, used for text, hover and fills
color-daemon-accent-soft: "#0a4bc433"
color-on-accent: "#ffffff"        # text on an accent background (buttons, active nav)
color-border: "#EAEAEA"           # dividers, panel borders (Radiate blockquote/table borders)
color-border-strong: "#E1E4E6"    # hovered borders
color-ok: "#0e8a6b"               # "live" and success states

font-body: "'Merriweather', Georgia, serif"
font-body-weight: "300"
font-heading: "'Roboto', 'Helvetica Neue', Arial, sans-serif"
radius: "4px"                     # Radiate buttons and the more-link

google-fonts-url: "https://fonts.googleapis.com/css2?family=Merriweather:wght@300;400;700&family=Roboto:wght@400;500;700&display=swap"
---

# Design — michaelweihrouch.com

The look of www.michaelweihrouch.com, written down so other surfaces can match it. The values
above are the contract; this text explains how to use them. Today the WordPress theme is the
source of truth: when the site's look changes, update this file to match.

## Character

- **Light and quiet.** White page, dark-gray text, no textures, gradients, glows or animated
  backgrounds.
- **One accent.** Purple `#632E9B` is the only color with meaning: links, hover, buttons,
  the active item. Everything else is grayscale.
- **Gray until touched.** Titles and navigation sit in body gray and turn purple on hover
  (Radiate: `.entry-title a`, `.site-title a`). Navigation items fill purple with white text
  on hover. Inline body links are purple at rest.
- **Serif to read, sans to scan.** Merriweather Light for running text; Roboto for headings,
  navigation, labels, buttons and small meta text.

## Rules

- Text on white uses `color-text` or darker. `color-text-muted` is the lightest text allowed.
- Text on the accent background is always `color-on-accent` (white).
- Borders are 1px `color-border`; rounded corners are `radius`, never pill-shaped.
- No monospace in the interface. Code samples may use the system monospace.
- Respect `prefers-reduced-motion`: no motion beyond short color transitions.

## Where it's applied

| Surface | How |
|---|---|
| www.michaelweihrouch.com | The Radiate theme itself (this file follows it) |
| daemon.michaelweihrouch.com (accent: `color-daemon-accent` blue instead of purple, since purple reads poorly as text there) | The deployment build's `design/apply.ts` turns the tokens into `design.css` and adds it to the built dashboard; its `design/overrides.css` maps them onto the dashboard's styles |
