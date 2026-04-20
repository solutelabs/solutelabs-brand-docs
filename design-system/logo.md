# SoluteLabs Logo

Logo assets, usage rules, and animation specs. All source files are in `assets/`.

---

## Assets

### Static logos

| File | Description | Use on |
|---|---|---|
| `assets/logo-wordmark.svg` | Full wordmark "SoluteLabs_" in purple (`#6622CB`) | Light backgrounds, white pages |
| `assets/logo-wordmark-white.svg` | Full wordmark in magnolia white (`#FBF6FF`) | Dark backgrounds (`#171717`), hero sections |
| `assets/logo-icon.svg` | S-mark icon (purple + dark purple + white) | Favicon context, app icons, compact spaces |
| `assets/logo-symbol.svg` | Large S-mark symbol (same shape, larger viewBox) | Hero illustrations, splash screens |

### Meta / social

| File | Description | Dimensions |
|---|---|---|
| `assets/favicon.ico` | Multi-size favicon (9 sizes, 16x16 through 256x256) | — |
| `assets/og-default.png` | Default Open Graph image. Purple bg, white wordmark, "AI-Native Product Engineering" tagline | 1200 x 630 |

### Animations (Lottie)

| File | Description | Duration |
|---|---|---|
| `assets/lottie/icon-loop.json` | S-mark icon animation, loops | Short |
| `assets/lottie/logo-full-loop.json` | Full wordmark reveal + loop | Full |
| `assets/lottie/logo-short-loop.json` | Full wordmark, shorter loop | Short |

Use with `lottie-web`, `@lottiefiles/react-lottie-player`, or any Lottie renderer. These were designed for white backgrounds; for dark backgrounds, you may need to override fill colors at runtime.

### Fonts (self-hosted)

| File | Description |
|---|---|
| `assets/fonts/Archivo-Variable.woff2` | Archivo variable font (all weights, 72KB) |
| `assets/fonts/Archivo-VariableItalic.woff2` | Archivo italic variable font (80KB) |
| `assets/fonts/LICENSE-Archivo.txt` | OFL license |

Manrope (body font) is not included in the brand kit. Load it via `next/font/google` or download from [Google Fonts](https://fonts.google.com/specimen/Manrope).

---

## Logo anatomy

The wordmark is custom type reading "SoluteLabs" followed by an underscore-like horizontal bar:

```
Solute
Labs___
```

The bar sits at baseline and extends right. It's part of the logo — don't remove or modify it.

The icon mark is flat — a solid purple (`#6622CB`) square with two white shapes:
1. A horizontal bar (lower center)
2. A small square (upper right)

No shadows, no gradients, no depth effects. The icon uses rounded corners (`rx="96"` at 512px) when rendered as an app icon.

---

## Usage rules

### Do

- Use the SVG files as-is. Don't rebuild the logo in a different tool.
- Maintain the aspect ratio at all times.
- On dark backgrounds (`#171717` or darker), use `logo-wordmark-white.svg`.
- On light backgrounds, use `logo-wordmark.svg` (purple).
- Leave breathing room. Minimum clear space = the height of the "S" character on all sides.

### Don't

- Don't change the purple (`#6622CB`). Don't recolor the logo to match a section's accent.
- Don't add drop shadows, outlines, or glow effects to the logo.
- Don't place the logo on busy photography without a solid-color container.
- Don't use the icon mark alone where the wordmark would fit. The wordmark is the primary lockup.
- Don't animate the static logo yourself. Use the provided Lottie files.
- Don't stretch, skew, or rotate.

### Minimum size

- **Wordmark:** 80px wide (below this, the "Labs_" text becomes illegible)
- **Icon mark:** 24px (below this, the internal shapes lose definition)
- **Favicon:** use the `.ico` file which includes optimized versions at 16px, 24px, 32px, 48px

---

## Implementation

### Favicon (Next.js)

```tsx
// app/layout.tsx
export const metadata = {
  icons: {
    icon: '/favicon.ico',
  },
};
```

### Favicon (HTML)

```html
<link rel="icon" href="/favicon.ico" sizes="any" />
```

### OG image (Next.js)

```tsx
export const metadata = {
  openGraph: {
    images: [{ url: '/images/og-default.png', width: 1200, height: 630 }],
  },
};
```

### Logo in header (Tailwind)

```jsx
import LogoWhite from '@/assets/logo-wordmark-white.svg';

<a href="/" className="block w-[120px]" aria-label="SoluteLabs home">
  <LogoWhite className="w-full h-auto" />
</a>
```

### Lottie animation

```jsx
import Lottie from 'lottie-react';
import logoAnim from '@/assets/lottie/logo-short-loop.json';

<Lottie animationData={logoAnim} loop className="w-[160px]" />
```

### Self-hosted Archivo

```css
@font-face {
  font-family: 'Archivo';
  src: url('/fonts/Archivo-Variable.woff2') format('woff2');
  font-weight: 100 900;
  font-style: normal;
  font-display: swap;
}

@font-face {
  font-family: 'Archivo';
  src: url('/fonts/Archivo-VariableItalic.woff2') format('woff2');
  font-weight: 100 900;
  font-style: italic;
  font-display: swap;
}
```
