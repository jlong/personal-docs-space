# Icon Component

Icon components shouldfollow a simple pattern using a shared `Base` wrapper that renders an SVG element.

## The Base Component

Located at `icons/Base.tsx`, it provides:

- **`BaseProps`** interface with optional `size` (default 20), `viewBox` (default `'0 0 20 20'`), and `className`

- Renders an `<svg>` with `fill="currentColor"` and `shrink-0` class

- Accepts children (the SVG path data)

## Creating a New Icon

1. **Get SVG path data** — source from [ZestIcons.com](https://zesticons.com) per the tech stack standard
2. **Create the file** at `icons/YourIcon.tsx`
3. **Follow this template:**

```tsx
import { Base, BaseProps } from '@/icons/Base'

export const YourIcon = ({ ...props }: BaseProps) => (
  <Base {...props}>
    <path
      fillRule="evenodd"
      clipRule="evenodd"
      d="M...your SVG path data..."
    />
  </Base>
)
```

## Overriding the viewBox

If your SVG uses a viewBox other than `0 0 20 20`, destructure it and pass a new default:

```tsx
export const CheckIcon = ({ viewBox = '0 0 24 24', ...props }: BaseProps) => (
  <Base viewBox={viewBox} {...props}>
    <path ... />
  </Base>
)
```

## Usage

Icons inherit color from `currentColor`, so they match the text color of their parent. Size defaults to 20px.

```tsx
<CheckIcon />                          // 20px, inherits color
<CheckIcon size={16} />                // 16px
<CheckIcon className="text-red-500" /> // custom color
```

## Conventions

- File name: PascalCase ending in `Icon.tsx` (e.g., `CheckIcon.tsx`)

- Export name matches file name

- Import from `@/icons/Base` using absolute path

- Use `fillRule="evenodd"` and `clipRule="evenodd"` on paths when applicable

- For custom fill colors on paths, use design system tokens like `fill-icon-primary`
