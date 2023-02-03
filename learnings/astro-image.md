# Astro's image integration

Astro's `<Image />` component can render optimised images. It can be used on local images and remote images.

```tsx
import { Image } from '@astrojs/image/components';
```

The required props are the real gotchas:

| Image Type                  | Props                                 |
| --------------------------- | ------------------------------------- |
| Local images in `src/`    | `src`, `alt`                          |
| Remote images               | `src`, `alt`, `format` and dimensions |
| Local images in `public/` | `src`, `alt`, `format` and dimensions |

Local images in `public/` are considered remote images.

## Dimensions

The `<Image />` component does not know the dimensions or the format of the remote images.

You will need provide either:
- `width` _and_ `height`, or
- `width` or `height` _and_ an as `aspectRatio` (to avoid layout shift).
