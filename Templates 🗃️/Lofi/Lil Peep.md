```dataviewjs
const container = this.container;
const iframe = document.createElement("iframe");
iframe.width = "560";
iframe.height = "315";
iframe.src = "https://www.youtube.com/embed/p7y-LQouZ8k?autoplay=1";
iframe.frameBorder = "0";
iframe.allow = "accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture";
iframe.allowFullscreen = true;

container.appendChild(iframe);
```
