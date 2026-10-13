# Public Service Advisory Slideshow

![GitHub](https://img.shields.io/github/license/kentoyblcsrs/PUBLIC-SERVICE-ADVISORY-GENERATOR-IMAGE-ONLY)
![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)

> A real-time, security-conscious public service advisory display for DENR air quality monitoring stations in Metro Cebu.

## Overview

This project is a self-contained, full-screen slideshow that displays live PM2.5 and PM10 advisories for Talisay and Toledo monitoring stations. It features an animated gooey bubble background, automatic refresh from a live Google Sheets data source, and protective measures against casual screen capture/download attempts.

## Features

- **Real-time Data** – Pulls live AQI readings every 5 seconds from the official DENR AQMS Google Sheets source
- **Dual Pollutants** – Rotates between PM2.5 and PM10 advisories for each station
- **Animated Background** – Fluid, gooey gradient bubble animation with mouse-interactive effect
- **Auto-slideshow** – Cycles advisories every 5 seconds with smooth fade transitions
- **Navigation** – Manual control via arrow keys or on-screen navigation buttons
- **Content Protection** – Disables right-click, drag, text selection, common save/print/devtools shortcuts, and adds a protective overlay
- **Self-contained** – Everything (HTML, CSS, JS, SVG filters) is embedded in a single `index.html` file

## Live Preview

Since GitHub raw doesn't render HTML, you can view it in one of these ways:

| Method | Notes |
| --- | --- |
| **Local** | Clone the repo and open `index.html` directly in your browser |
| **GitHub Pages** | Go to `Settings > Pages > Deploy from branch > main`, then access `https://yourusername.github.io/repo-name/` |
| **Hosting Services** | Deploy to [Netlify](https://www.netlify.com/), [Vercel](https://vercel.com/), or [Cloudflare Pages](https://pages.cloudflare.com/) by dragging the folder |

## Project Structure

```text
.
├── index.html              # Main slideshow application (self-contained)
├── New Background.png     # Advisory poster background asset
├── DENR LOGO.png           # DENR logo
├── New Bagong Pilipinas.png # Bagong Pilipinas logo
└── README.md               # Project documentation
```

## Data Source

The application fetches CSV data directly from this Google Sheets:

- **Spreadsheet ID:** `1Fh6w15beHCAHPGJw-2nfwNryez3vwnSVCd8bsFGKvHE`
- **Sheets:** `talisay`, `toledo`

Data is parsed client-side and refreshed automatically every 5 seconds.

## Usage

1. Clone or download this repository
2. Open `index.html` in a modern web browser (Chrome, Firefox, Edge, Safari)
3. The slideshow will automatically load and cycle through advisories
4. Use the left/right arrows or keyboard arrow keys to navigate manually

## Customization

- **Slideshow timing:** Modify `SLIDESHOW_INTERVAL` and `DATA_REFRESH_INTERVAL` in `index.html` (default: 5000ms)
- **Colors/theme:** Adjust CSS variables under `:root` in the bubble background styles
- **AQI categories:** Edit the `aqiCategories` array to match your desired thresholds
- **Station configuration:** Update `ADVISORIES` and `continuousSheets` arrays as needed

## Tech Stack

- **HTML5** – Semantic structure
- **CSS3** – Animations, filters (SVG goo filter), gradients, glassmorphism
- **Vanilla JavaScript** – No frameworks, dependencies, or build tools
- **Canvas API** – Dynamic poster rendering
- **Fetch API** – Live data retrieval

## Security & Protection

This display includes anti-capture measures intended for public display environments:

- Disables context menu, text selection, copy/cut, and drag operations
- Blocks common keyboard shortcuts (Ctrl+S, Ctrl+P, Ctrl+U, F12, Ctrl+Shift+I/J/C)
- Attempts to clear clipboard on PrintScreen
- Applies a transparent shield overlay above interactive elements

> **Note:** These are client-side deterrents only. Determined users can still capture content through external means (hardware capture, etc.).

## Browser Compatibility

Tested and compatible with modern browsers supporting:

- CSS `filter: url()` with SVG filters
- CSS animations & keyframes
- Canvas 2D API
- ES6+ JavaScript features (arrow functions, const/let, template literals)

## Contributing

Contributions are welcome! Feel free to:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Credits

- **DENR** – Air Quality Monitoring data
- **Design Inspiration** – Animated gradient bubble background concept
- **Developed by** – [kentoyblcsrs](https://github.com/kentoyblcsrs)

---

**⚡ Built for impactful public awareness through live environmental data visualization.**
