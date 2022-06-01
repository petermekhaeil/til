# Hex color notation have an alpha channel

The hex color notation can be described as `#RGB[A]` or `#RRGGBB[AA]` - it accepts an alpha channel that can be used to represent the transparency.

When using it as `#RRGGBB[AA]`, the alpha channel is a hexadecimal number where `00` is full transparent and `FF` full opaque. If using the shorter `#RGB[A]` notation, it is a hexadecimal number ranging from `0` and `F`.

```cs
#FF7f00     /* orange               */
#FF7f0000   /* orange 	 0% opaque  */
#FF7f0080   /* orange   50% opaque  */
#FF7f00FF   /* orange  100% opaque  */

#01E        /* blue               */
#01E0       /* blue     0% opaque */
#01E8       /* blue    53% opaque */
#01EF       /* blue   100% opaque */
```

You can find out more on [MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/hex-color).
