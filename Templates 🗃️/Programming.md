---
title: "Random Programming Quote"
date: {{date}}
tags: tech, programming, quote
---
## Here’s a random tech-related fact for you:

```dataviewjs
async function fetchTechFact() {
  const response = await fetch('https://techy-api.vercel.app/api/json');
  const data = await response.json();
  return data.message;
}

fetchTechFact().then(fact => {
  dv.paragraph(fact);
});
```
