# React + TypeScript + Vite + Tailwind + Shadcn + React-router-dom



Tailwind launched version 4.0.0

So,there is problem to install tailwind with shadcn

Here is steps to solved the problem


## Install React-router dom v6.28.2


```js
npm create vite@latest name-of-your-project -- --template react
# follow prompts
cd <your new project directory>
npm install react-router-dom localforage match-sorter sort-by
```

## Install tailwind css v3.4.17

```js
npm install -D tailwindcss postcss autoprefixer
```

After that it automatically installed version 4.0.0.So, you need to update version in package.json

![image](https://github.com/user-attachments/assets/0827ab23-57e6-44f4-bc98-e91eb031b4f7)


Then follow 


```js
npm install -D tailwindcss postcss autoprefixer
npx tailwindcss init -p
```


## Install Shadcn

Add this import header in your main css file, src/index.css in our case:
```js
@tailwind base;
@tailwind components;
@tailwind utilities;
```


Configure the tailwind template paths in tailwind.config.js:
```js
/** @type {import('tailwindcss').Config} */
module.exports = {
  content: ["./index.html", "./src/**/*.{ts,tsx,js,jsx}"],
  theme: {
    extend: {},
  },
  plugins: [],
}

```


Edit tsconfig.json file
```js
{
  "files": [],
  "references": [
    {
      "path": "./tsconfig.app.json"
    },
    {
      "path": "./tsconfig.node.json"
    }
  ],
  "compilerOptions": {
    "baseUrl": ".",
    "paths": {
      "@/*": ["./src/*"]
    }
  }
}


```
Edit tsconfig.app.json file
```js
{
  "compilerOptions": {
    // ...
    "baseUrl": ".",
    "paths": {
      "@/*": [
        "./src/*"
      ]
    }
    // ...
  }
}

```
Update vite.config.ts

```js
npm install -D @types/node

```
```js
import path from "path"
import react from "@vitejs/plugin-react"
import { defineConfig } from "vite"

export default defineConfig({
  plugins: [react()],
  resolve: {
    alias: {
      "@": path.resolve(__dirname, "./src"),
    },
  },
})

```
Run the shadcn-ui init command to setup your project:

```js
npx shadcn@latest init

```
That's it
You can now start adding components to your project.

```js
npx shadcn@latest add button

```
```js
import { Button } from "@/components/ui/button"

export default function Home() {
  return (
    <div>
      <Button>Click me</Button>
    </div>
  )
}

```


run the terminal
```js
npm run dev
```

Final Result 
![image](https://github.com/user-attachments/assets/4e55f82f-ba9d-40ab-8a34-31fef8c5af15)


