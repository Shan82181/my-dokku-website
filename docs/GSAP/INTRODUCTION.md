---
sidebar_position: 1
---
# how_to_install

## Using NPM[​](https://shan82181.github.io/Noteshub/docs/GSAP/how_to_install/#using-npm "Direct link to Using NPM")

```jsx
npm install gsap    // for react    
npm install @gsap/react  
```

```jsx
import { gsap } from "gsap";    
import { useGSAP } from "@gsap/react";   // for react    
gsap.registerPlugin(useGSAP);
```

## Using CDN[​](https://shan82181.github.io/Noteshub/docs/GSAP/how_to_install/#using-cdn "Direct link to Using CDN")

```
    <script src="https://cdn.jsdelivr.net/npm/gsap@3.12.5/dist/gsap.min.js"></script>
```