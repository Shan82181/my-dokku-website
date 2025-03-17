---
sidebar_position: 4
---
# HOW TO ADD CUSTOM COLORS 

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
      color:{
        csblue:{
	   50:'#DFDFF0',
           75:'#DFDFF2',
           100:'#F0F2FA',
           200:'#010101',
           300:'#4FB7DD',
	}
      }
    },
  },
  plugins: [],
}

```