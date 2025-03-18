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
