# Composable CBDT POC

Proof of concept: layered emoji can be made with CBDT/GCLC glyphs. Works for the following sequence:

👩&amp;zwj;❤️&amp;zwj;👩

The font turns these three emoji into one single emoji.

## Description of process

1. Create "artwork" for separate pieces of the composed emoji: `woman, left`, `woman, right` and `small heart, centered`
2. Create CBDT/CBLC table, using "artwork" as PNG → hex
2. Create GSUB substitution rules table
3. Generare font
4. Show result in `test.html`

## Notes

- Dimensions of "artwork" are off
- There is no artwork for the single `woman` and `heart` emoji in the demo font
- Once substitution rules are in place, this will work regardless of color glyphs used. E.g. COLR/CPAL, SVG, sbix. It's possible to further re-use glyph components in the SVG format.
- In proper artwork, more substitutions can happen. E.g. re-use shadow layers between foreground/background emoji.