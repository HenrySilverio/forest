# 🌲 Forest — Nature Immersion Landing Page

**Forest** is an immersive, nature-inspired landing page built entirely with **Tailwind CSS** and enhanced with **animations, dynamic weather via Open-Meteo API**, and responsive design techniques. It simulates a real-world forest retreat website, ideal for eco-tourism, glamping, or digital detox experiences.

![Forest Cover](./img/forest.svg)

---

## 🌟 Features

- 🎨 Fully responsive UI powered by **Tailwind CSS**
- 🌦️ Dynamic **weather & temperature integration** (via [Open-Meteo API](https://open-meteo.com/))
- 🌘 Smooth scroll navigation
- 🔮 Custom **animations** and **delay classes**
- 🌿 Natural color palette with custom **Greener** shades
- 📽️ Background video autoplay based on temperature
- 🏕️ Custom components like `.neon`, `.btn`, `.input`, `.radial-gradient`
- 🌐 Font integration using **Google Fonts (DM Sans + DM Serif Text)**
- 🎉 Event cards, image galleries, and call-to-action components
- 📱 Mobile-first navigation toggle

---

## 📦 Tech Stack

| Tech        | Description                           |
|-------------|---------------------------------------|
| TailwindCSS | Utility-first CSS framework           |
| HTML        | Semantic and clean layout             |
| JavaScript  | DOM manipulation and weather logic    |
| Open-Meteo  | Real-time weather forecast API        |

---

## 🧪 Live Preview

> Experience the project locally:
```bash
npm install
npm run dev
```

---

## 🎯 Key Components

### `📦 tailwind.config.js`
```js
theme: {
  extend: {
    animation: {
      ['slide-in']: 'slideIn 0.4s ease-out forwards',
      ['fade-in']: 'fadeIn 0.4s ease-out forwards',
    },
    colors: {
      greener: {
        200: '#ACEF75',
        300: '#91EE77',
        400: '#17E880',
        700: '#2E482C',
        800: '#16281F',
        900: '#0F1C15',
        950: '#030504',
      },
    },
  },
},
```

### `🎨 Custom Tailwind Classes`

```css
@layer components {
  .neon {
    @apply rounded-full border border-greener-200 bg-gradient-to-b from-greener-200 to-greener-400 text-greener-900;
    box-shadow: 0 1px 4px 1px theme(colors.greener.200 / 25%), inset 0px -1px 2px theme(colors.greener.200);
  }

  .btn {
    @apply rounded-full border border-greener-200 bg-gradient-to-b from-greener-200 to-greener-400 px-5 py-2 text-greener-900 transition hover:contrast-200;
  }

  .input {
    @apply bg-greener-800 rounded-md border-2 border-greener-800 p-2 text-white focus:outline-none focus:ring-2 focus:ring-greener-400 focus:border-greener-900;
  }

  .radial-gradient {
    background-image: radial-gradient(
      50% 100% at 50% 0%,
      theme(colors.greener.700) 0%,
      theme(colors.greener.800) 100%
    );
  }
}
```

---

## 🔄 Dynamic Weather Integration

Real-time weather data is pulled from Open-Meteo API using the user's **geolocation**, updating:
- Date
- Temperature
- Weather icon
- Background video (`video_chuva.mp4` or `video_sol.mp4`)

### JS Highlight:
```js
const apiUrl = `https://api.open-meteo.com/v1/forecast?latitude=${lat}&longitude=${lon}&current_weather=true&timezone=auto`;

fetch(apiUrl)
  .then(res => res.json())
  .then(data => {
    temperature.textContent = `${Math.round(data.current_weather.temperature)}°C`;
    // Dynamically sets video source
    video.src = data.current_weather.temperature < 25 ? './img/video_chuva.mp4' : './img/video_sol.mp4';
  });
```

---

## 📷 Image Gallery & Sections

- **Accommodations** — with tags: *Ruby*, *Emerald*, *Saphire*
- **Events** — Moon phases, meteor showers, aurora borealis
- **Experiences** — Canoeing, Wildlife, Stargazing
- **Natural Cycle** — Dawn, Noon, Dusk timeline
- **Contact Form** — Responsive and styled input components

---

## 🤝 Partners

![Partners](./img/parceiros/caravan.svg)
![Partners](./img/parceiros/dogs.svg)
![Partners](./img/parceiros/wildbeast.svg)
![Partners](./img/parceiros/lescone.svg)
![Partners](./img/parceiros/surfbot.svg)

---

## 📇 Contact

> Interested in visiting Forest? Reach out!

📍 **Address:** Mata Street, 123 - National Forest - RJ  
📧 **Email:** [contact@forest.com](mailto:contact@forest.com)  
📞 **Phone:** +55 (34) 99999-9999  

---

## 🔗 Socials

[🌿 Instagram](https://www.instagram.com/henriquesilveriobx/)  
[💼 LinkedIn](https://www.linkedin.com/in/henrique-b-silverio/)  
[👨‍💻 GitHub](https://github.com/HenrySilverio/forest)

---

## 🪵 Final Words

> “Come and experience life in the forest” — where the code is clean, and the air is cleaner.  
Breathe in nature, one Tailwind class at a time.

---
```html
🌳 Made with Tailwind CSS · Designed by @HenrySilverio
```