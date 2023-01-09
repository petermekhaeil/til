# CSS property: `font-variant-numeric`

Some OpenType fonts support alternate numeric glyphs that can be styled using `font-variant-numeric`.

## Demo

Here is a [CodeSandbox](https://flqxy1.csb.app/) that demonstrate each value. This demo uses the "Source Sans Pro" font which supports these features.

Take a look at the `tabular-nums` feature - it can make the design of tabular data very satisfying. 

## Syntax

```css
/* normal: Disable using alternate glyphs */
font-variant-numeric: normal;

/* ordinal: Use letters to represent numeric order */
font-variant-numeric: ordinal;

/* slashed-zero: Use a 0 with a diagonal slash */
font-variant-numeric: slashed-zero;

/* lining-nums: Use glyphs that are all aligned by their baseline. */
font-variant-numeric: lining-nums;

/* oldstyle-nums: Use glyphs where some numbers have descenders */
font-variant-numeric: oldstyle-nums; 

/* proportional-nums: Use glyphs where numbers are not all of the same size */
font-variant-numeric: proportional-nums; 

/* tabular-nums: Use glyphs where numbers all have the same width */
font-variant-numeric: tabular-nums; 

/* diagonal-fractions: Use diagonal fractions (numbers are made smaller and separated by a slash) */
font-variant-numeric: diagonal-fractions; 

/* stacked-fractions: Numbers are made smaller, stacked and separated by a horizontal line */
font-variant-numeric: stacked-fractions; 
```

Values can be combined together:

```css
font-variant-numeric: slashed-zero tabular-nums;
```

## Support

Not all fonts support these features. The values will have no effect if the font family does not have support.
