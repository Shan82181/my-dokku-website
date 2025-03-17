---
sidebar_position: 3
---
# HOW TO ADD FONTS 

In `index.css` file 
```css
 @tailwind base;
 @tailwind components;
 @tailwind utilities;

 @layer base{
    @font-face {
        font-family: 'circular-web';
        src: url('/fonts/circularweb-book.woff2') format('woff2')
    }
```
In `tailwind.config.js` file 
```css
/** @type {import('tailwindcss').Config} */
export default {
  content: [
    "./index.html",
    "./src/**/*.{js,ts,jsx,tsx}",
  ],
  theme: {
    extend: {
      fontFamily:{
        'circular-web':['circular-web','sans-serif']
      }
    },
  },
  plugins: [],
}

```