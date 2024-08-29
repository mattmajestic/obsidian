---
title: "Crypto Prices for {{title}}"
date: {{date}}
tags: crypto, finance
---
## Current Crypto Prices


```dataviewjs
// DataviewJS Script
const currencies = ["bitcoin", "ethereum", "litecoin"];

async function fetchCryptoData(symbol) {
  const response = await fetch(`https://api.coingecko.com/api/v3/coins/markets?vs_currency=usd&ids=${symbol}`);
  const data = await response.json();
  return {
    price: `$${data[0].current_price.toFixed(2)}`,
    change: `${data[0].price_change_percentage_24h.toFixed(2)}%`,
    marketCap: `$${(data[0].market_cap / 1e9).toFixed(2)}B`
  };
}

Promise.all(currencies.map(fetchCryptoData)).then(results => {
  dv.table(["Currency", "Symbol", "Price (USD)", "24h Change (%)", "Market Cap (USD)"], [
    ["Bitcoin", "BTC", results[0].price, results[0].change, results[0].marketCap],
    ["Ethereum", "ETH", results[1].price, results[1].change, results[1].marketCap],
    ["Litecoin", "LTC", results[2].price, results[2].change, results[2].marketCap]
  ]);
});
```


