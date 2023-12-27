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

5. I tried messing around with the vite config, but no luck.

```ts
import { defineConfig } from "astro/config";

import tailwind from "@astrojs/tailwind";
import postcssImport from "postcss-import";
import postcssNested from "postcss-nested";
import tailwindcss from "tailwindcss";
import tailwindcssNesting from "tailwindcss/nesting";

// https://astro.build/config
export default defineConfig({
  integrations: [tailwind({ applyBaseStyles: false })],
  vite: {
    css: {
      postcss: {
        plugins: [
          postcssImport(),
          postcssNested(),
          tailwindcss(),
          tailwindcssNesting(),
        ],
      },
    },
  },
});
```
