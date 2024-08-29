---
title: "Random Dog Image"
date: {{date}}
tags: fun, random, dog
---
## Here’s a random dog image to make you smile:

```dataviewjs
async function fetchRandomDogImage() {
  const response = await fetch('https://random.dog/woof.json');
  const data = await response.json();
  return data.url;
}

fetchRandomDogImage().then(dogUrl => {
  dv.paragraph(`<img src="${dogUrl}" alt="Random Dog Image" style="max-width: 40%; height: auto;">`);
});
```
