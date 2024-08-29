---
title: "Random Space Image"
date: {{date}}
tags: fun, random, space
---
## Here’s a random space image to inspire your curiosity:

```dataviewjs
async function fetchRandomSpaceImage() {
  const response = await fetch('https://api.nasa.gov/planetary/apod?api_key=DEMO_KEY');
  const data = await response.json();
  return data.url;
}

fetchRandomSpaceImage().then(spaceUrl => {
  dv.paragraph(`<img src="${spaceUrl}" alt="Random Space Image" style="max-width: 100%; height: auto;">`);
});
```
