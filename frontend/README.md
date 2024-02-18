# MERN-GITHUB Frontend

## Install

1. Development environment settings: `npm create vite@latest .`
2. Select a framework: `React`
3. Select a variant: `JavaScript`
4. install package: `npm install`
5. execution: `npm run dev`

---

## Init

**vite.config.js**

```js
export default defineConfig({
  plugins: [react()],
  server: {
    port: 3000,
  },
});
```

---

## Tailwind CSS

> If you want to use Tailwind CSS more easily, install the **'Tailwind CSS IntelliSense'** extension.

> If you want to check SVG images, install the **'Svg Preview'** extension.

1. `npm install -D tailwindcss postcss autoprefixer`
2. `npx tailwindcss init -p`

**Created Tailwind CSS config file: tailwind.config.js**

> You may need to modify the value of **'content'** depending on the filename extension you use.

```js
/** @type {import('tailwindcss').Config} */
export default {
  content: ['./src/**/*.{html,js,jsx}'],
  theme: {
    extend: {},
  },
  plugins: [],
};
```

**Created PostCSS config file: postcss.config.js**

```js
export default {
  plugins: {
    tailwindcss: {},
    autoprefixer: {},
  },
};
```

**index.css**

```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```

**delete App.css**

---

## react-router-dom

`npm install react-router-dom react-hot-toast react-icons`

**main.jsx**

```jsx
import React from 'react';
import ReactDOM from 'react-dom/client';
import App from './App.jsx';
import './index.css';
import { BrowserRouter } from 'react-router-dom';

ReactDOM.createRoot(document.getElementById('root')).render(
  <React.StrictMode>
    <BrowserRouter>
      <App />
    </BrowserRouter>
  </React.StrictMode>
);
```
