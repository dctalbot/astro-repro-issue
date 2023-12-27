1. `npm create astro@latest` with sample files, typescript strict
2. `npx astro add tailwind`
3. Add `/src/global.css` and import it in `/src/pages/index.astro`
4. Add the following contents to global.css

```css
@tailwind base;
@tailwind components;
@tailwind utilities;

body {
  background: red;

  h1 {
    font-style: italic;
  }
}
```
