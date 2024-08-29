---
title: "Random Joke"
date: {{date}}
tags: fun, random, joke
---
## Here’s a random joke to make you laugh:

```dataviewjs
async function fetchRandomJoke() {
  const response = await fetch('https://icanhazdadjoke.com/', {
    headers: {
      'Accept': 'application/json'
    }
  });
  const data = await response.json();
  return data.joke;
}

fetchRandomJoke().then(joke => {
  dv.paragraph(joke);
});
```
