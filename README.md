# 🎗️ Base configs

[![GitHub](https://img.shields.io/badge/README-%23121011.svg?style=for-the-badge&logo=github&logoColor=white)](https://github.com/tgvie/configs/blob/main/README-template.md)

[![Git](https://img.shields.io/badge/.gitignore-%23F05033.svg?style=flat-square&logo=git&logoColor=white)](https://github.com/tgvie/configs/blob/main/.gitignore)
[![Git](https://img.shields.io/badge/Git_Commands-%23F05033.svg?style=flat-square&logo=git&logoColor=white)](https://github.com/tgvie/configs/blob/main/git-commands.md)

[![SASS](https://img.shields.io/badge/reset.scss-hotpink.svg?style=flat-square&logo=SASS&logoColor=white)](https://github.com/tgvie/configs/blob/main/reset.scss)

[![ESLint](https://img.shields.io/badge/.eslintrc.cjs-4B3263?style=flat-square&logo=eslint&logoColor=white)](https://github.com/tgvie/configs/blob/main/.eslintrc.cjs)

[![Prettier](https://img.shields.io/badge/.prettierrc.json-%23F7B93E.svg?style=flat-square&logo=prettier&logoColor=black)](https://github.com/tgvie/configs/blob/main/.prettierrc.json)
[![Prettier](https://img.shields.io/badge/.prettierignore-%23F7B93E.svg?style=flat-square&logo=prettier&logoColor=black)](https://github.com/tgvie/configs/blob/main/.prettierignore)

[![Vite](https://img.shields.io/badge/vite.config.ts-%23646CFF.svg?style=flat-square&logo=vite&logoColor=white)](https://github.com/tgvie/configs/blob/main/vite.config.ts)

[![Vue.js](https://img.shields.io/badge/vue.config.js-%2335495e.svg?style=flat-square&logo=vuedotjs&logoColor=%234FC08D)](https://github.com/tgvie/configs/blob/main/vue.config.js)

[![JWT](https://img.shields.io/badge/jsonconfig.json-black?style=flat-square&logo=JSON%20web%20tokens)](https://github.com/tgvie/configs/blob/main/jsonconfig.json)
[![JWT](https://img.shields.io/badge/package.json-black?style=flat-square&logo=JSON%20web%20tokens)](https://github.com/tgvie/configs/blob/main/package.json)

[![PNPM](https://img.shields.io/badge/deploy.yml-%234a4a4a.svg?style=flat-square&logo=pnpm&logoColor=f69220)](https://github.com/tgvie/configs/blob/main/deploy.yml)
[![PNPM](https://img.shields.io/badge/deploy_pnpm.yml-%234a4a4a.svg?style=flat-square&logo=pnpm&logoColor=f69220)](https://github.com/tgvie/configs/blob/main/deploy-pnpm.yml)
[![PNPM](https://img.shields.io/badge/deploy_static.yml-%234a4a4a.svg?style=flat-square&logo=pnpm&logoColor=f69220)](https://github.com/tgvie/configs/blob/main/deploy-static.yml)
[![PNPM](https://img.shields.io/badge/deploy_vitepress_pnpm.yml-%234a4a4a.svg?style=flat-square&logo=pnpm&logoColor=f69220)](https://github.com/tgvie/configs/blob/main/deploy-vitepress-pnpm.yml)


# 🐣 Setup Vite + Vue

```sh
npm create vite@latest .
```

1. Choose `Vue`
2. Choose `Official Vue Starter` *(npm create vue@latest)*
3. Fill in project name
4. Choose:
    - `TypeScript`
    - `Router`
    - `Pinia`
    - `ESLint`
    - `Prettier`

- Then, run:
```sh
npm install
npm format
npm dev
```
- Open localhost and check if everything's installed correctly

<details>
<summary>Install Sass or Tailwind</summary>
  
- **Sass**
```sh
npm i -D sass
```
- Change `style.css` to `.scss`

<details>
<summary><strong>Tailwind</strong></summary>
  
```sh
npm install -D tailwindcss postcss autoprefixer
npx tailwindcss init -p
```
`tailwind.config.js` should look like this
```js
/** @type {import('tailwindcss').Config} */
export default {
  content: [
    "./index.html",
    "./src/**/*.{vue,js,ts,jsx,tsx}",
  ],
  theme: {
    extend: {},
  },
  plugins: [],
}
```
- In `style.css` add:
```css
@tailwind base;
@tailwind components;
@tailwind utilities;

body {
  @apply bg-slate-800 text-white;
}
```
</details>

- Remove `base.css`, `main.css` in `src/assets`
- In `src/main.ts`, change CSS-path to the correct one: `import './assets/style.css;`?
- Restart server with `npm run dev`
</details>

<details>
<summary>Remove unused files, like:</summary>
  
- `src/assets/base.css`
- `src/assets/main.css`
- `src/assets/logo.svg`
- `src/components/icons`
- `src/components/HelloWorld.vue`
- `src/components/TheWelcome.vue`
- `src/components/WelcomeItem.vue`
- In `App.vue`, remove the entire `<style>`-tag at the end
- In `views/HomeView.vue`, remove the import for `TheWelcome` and delete it from `<main>`. Replace with the text `Home` or similar
</details>

<details>
<summary><code>vite.config.js</code> should look similar to this:</summary>
  
```js
import { defineConfig } from "vite";
import vue from "@vitejs/plugin-vue";
import path from "path";

export default defineConfig({
  plugins: [vue()],
  base: "/", /*link to repo*/
  resolve: {
    alias: {
      /*Use @ instead of ../ in paths*/
      "@": path.resolve(__dirname, "src"),
    },
  },
  css: {
    preprocessorOptions: {
      scss: {
        /*Use variables globally*/
        additionalData: `@import "@/scss/_variables.scss";`,
      },
    },
  },
});
```
</details>


# 🐣 Setup Node/Express/TypeScript

```sh
npm init -y
npm install express
npm install -D typescript @types/express
npm install -D tsx
```
<details>
<summary>Create a new folder and file: <strong>src/index.ts</strong></summary>
  
```ts
import express from 'express';
const app = express();

const PORT = 3000;
app.listen(PORT, () => {
    console.log(`Server is running at http://localhost:${PORT}`)
})
```
```sh
npx tsc --init
```
</details>

<details>
<summary>Add these changes to <strong>tsconfig.json</strong></summary>
  
```json
"module": "NodeNext"
"outDir": "./dist"
```
</details>

<details>
<summary>Add these scripts to <strong>package.json</strong></summary>

```json
"scripts": {
"test": "echo \"Error: no test specified\" && exit 1",
"dev": "npx tsx watch src/index.ts",
"build": "npx tsc --build",
"start": "node dist/index.js"
}
```
</details>

<details>
<summary>To compile all ts-files to js</summary>

```sh
npx tsc --build
```
</details>

🧠 [Alternative](https://kinsta.com/blog/express-typescript/?utm_source=chatgpt.com)
