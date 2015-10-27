## Incomplete List of Mistakes in the Design of CSS

That should be corrected if anyone invents a time machine. :P

- white-space: nowrap should be white-space: no-wrap
	- and line wrapping behavior should not have been added to white-space
- vertical-align should not apply to table cells. Instead the CSS3 alignment properties should exist in Level 1.
- vertical-align: middle should be text-middle because it's not really in the middle.
- Percentage heights should be calculated against fill-available rather than being undefined in auto situations.
- Table layout should be sane.
- Box-sizing should be border-box by default.
- background-size with one value should duplicate its value, not default the second one to auto.
- background-position and border-spacing (all 2-axis properties) should take *vertical* first, to match with the 4-direction properties like margin.
- z-index should be called z-order or depth and should Just Work on all elements (like it does on flex items).
- word-wrap/overflow-wrap should not exist. Instead, overflow-wrap should be a keyword on 'white-space', like nowrap (no-wrap).
- The top and bottom margins of a box should never have been allowed to collapse together automatically as this is the root of all margin-collapsing evil.
- Partial collapsing of margins instead of weird rules to handle min/max-heights?
- Tables (and other non-blocks, e.g. flex containers) should form pseudo-stacking contexts.
- The currentcolor keyword should have a dash, current-color.
- There should have been a predictable color naming system instead of arbitrary X11 names.
border-radius should have been corner-radius.
- Absolutely-positioned replaced elements should stretch when opposite offset properties (e.g. left+right) are set, instead of being start-aligned.
- The hyphens property should be called hyphenate. (It's called hyphens because the XSL:FO people objected to hyphenate.)
rgba() and hsla() should not exist, rgb() and hsl() should have gotten an optional fourth parameter instead (and the alpha value should have used the same format as R, G, and B or S and L).
-descendant combinator should have been » and indirect sibling combinator should have been ++, so there's some logical relationships among the selectors' ascii art
- the *-blend-mode properties should've just been *-blend
- The syntax of unicode ranges should have consistent with the rest of CSS, like u0001-u00c8.
- font-family should have required the font name to be quoted (like all other values that come from “outside” CSS). The rules for handling unquoted font names make parsing font stupid, as it requires a font-size value for disambiguation.
- Flexbox should have been less crazy about flex-basis vs width/height. Perhaps: if width/height is auto, use flex-basis; otherwise, stick with width/height as an inflexible size. (This also makes min/max width/height behavior fall out of the generic definition.)
- :empty should have been :void, and :empty should select items that contain only white space
table-layout: fixed; width: auto should result in a fill-available table with fixed-layout columns.
- 'text-orientation' should have had upright as the initial value (given the latest changes to 'writing-mode').
- The @import rule is required to (a) always hit the network unless you specify cache headers, and (b) construct fresh CSSStyleSheet objects for every import, even if they're identical. It should have had more aggressive URL-based deduping and allowed sharing of stylesheet objects.
- Selectors have terrible future-proofing. We should have split on top-level commas, and only ignored unknown/invalid segments, not the entire thing.