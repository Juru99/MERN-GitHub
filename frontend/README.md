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

https://tailwindcss.com/docs/installation/using-postcss : Using PostCSS

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

> The url(' ') value of the background property starts from the 'public' folder path.

```css
@tailwind base;
@tailwind components;
@tailwind utilities;

body {
  background: linear-gradient(
      to bottom right,
      rgba(0, 0, 0, 0.9),
      rgba(0, 0, 0, 0.4)
    ), url('/bg.png');
  background-repeat: no-repeat;
  background-size: cover;
  background-position: center;
  background-attachment: fixed;
}
```

**finally, delete App.css**

### [Tailwind CSS Tip]

**1. reusing tailwind CSS**

```css
/* reusing tailwind CSS */
@layer components {
  .bg-glass {
    @apply bg-clip-padding backdrop-filter backdrop-blur-md bg-opacity-10 border border-gray-800 hover:bg-gray-600/10;
  }
}
```

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

---

## pages Folder

> If you want to auto-complete the JSX initial structure, install the `VS Code ES7+ React/Redux/React-Native/JS snippets` extension and enter **'rafce'**.

- **HomePage.jsx**
- **LoginPage.jsx**
- **SignUpPage.jsx**

- **ExplorePage.jsx**
- **LikesPage.jsx**
  - Flowbite(design) tables link: https://flowbite.com/docs/components/tables/

---

## components Folder

> tailwind css glassmorphism generator: https://tailwindcss-glassmorphism.vercel.app/

> https://react-icons.github.io/react-icons/

- Sidebar.jsx: Displays links.

  1. If `authUser = true`, Likes link, Explore link, and Logout link are displayed.
  2. If `authUser = false`, Login link, SignUp link are displayed.

  - Logout.jsx: Displays your profile and logout link.

- **Search.jsx**: Added Search UI in HomePage
- **SortRepos.jsx**: Added Sort UI in HomePage
- **ProfileInfo.jsx**: Added ProfileInfo UI in HomePage
  - Profile image, GitHub link, Location, Member since, Full Name, Username, Followers, Follwing, Public repos, Public gists

---

## etc.

> If you want to differentiate comments in various ways, install the `Better Comments` extension.

```jsx
/** MyMethod (green)
 * * Important information is highlighted (yellowgreen)
 * ! Deprecated method, do not use (red)
 * ? Should this mthod be exposed in the public API? (blue)
 * TODO: refactor this method so that it conforms to the API (orange)
 * @param myParam The parameter for this method (JSDoc)
 */
```
