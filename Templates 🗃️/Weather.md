---
title: Weather for Clemson, SC
date_created:
  "{ date }": 
location: Clemson, SC
---
```dataviewjs
const location = dv.current().location;

async function fetchWeather(location) {
    const apiUrl = `https://wttr.in/${encodeURIComponent(location)}?format=j1`;
    
    try {
        const response = await fetch(apiUrl);
        const data = await response.json();
        return data;
    } catch (error) {
        console.error("Error fetching weather data:", error);
        return null;
    }
}

fetchWeather(location).then(data => {
    if (data) {
        const currentCondition = data.current_condition[0];
        const weatherDesc = currentCondition.weatherDesc[0].value;
        const tempF = currentCondition.temp_F;
        const feelsLikeF = currentCondition.FeelsLikeF;
        const humidity = currentCondition.humidity;

        dv.header(2, "Current Weather in Clemson, SC");
        dv.paragraph(`**Weather:** ${weatherDesc}`);
        dv.paragraph(`**Temperature:** ${tempF}°F (Feels like ${feelsLikeF}°F)`);
        dv.paragraph(`**Humidity:** ${humidity}%`);
    } else {
        dv.paragraph("Failed to fetch weather data.");
    }
});
```




