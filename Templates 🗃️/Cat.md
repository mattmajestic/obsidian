---
title: "Random Cat Image"
date: {{date}}
tags: fun, random, cat
---
## Here’s a random cat image to brighten your day:

```dataviewjs
async function fetchRandomCatImage() {
  const response = await fetch('https://api.thecatapi.com/v1/images/search');
  const data = await response.json();
  return data[0].url;
}

fetchRandomCatImage().then(catUrl => {
  dv.paragraph(`<img src="${catUrl}" alt="Random Cat Image" style="max-width: 40%; height: auto;">`);
});
```
