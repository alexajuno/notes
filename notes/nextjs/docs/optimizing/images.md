# Image Optimization

## Usage

next/image

### Local Images

- `import` your image
- Next will auto determine the width and height and can prevent Cumulative Layout Shift

### Remote Images

- src is a string
- you need to provide `width`, `height` and optional `blurDataURL`
- you also need to define support URL in next.config.[mjs/js]

## Image sizing

- Three way of sizing
  - automatically static import
  - explicitly `width` and `height`
  - implicitly with `fill` to fits its parent element
