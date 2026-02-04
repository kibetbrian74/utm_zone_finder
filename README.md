# UTM Zone Finder 🗺️

An interactive web-based mapping application that allows users to find UTM (Universal Transverse Mercator) zones by clicking anywhere on a map. The application calculates and displays the UTM zone number and hemisphere designation for any location on Earth.

![UTM Zone Finder](https://img.shields.io/badge/Status-Active-success)
![License](https://img.shields.io/badge/License-MIT-blue)
![HTML5](https://img.shields.io/badge/HTML5-E34F26?logo=html5&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?logo=javascript&logoColor=black)
![Leaflet](https://img.shields.io/badge/Leaflet-199900?logo=leaflet&logoColor=white)

## 🌐 Live Demo

**[Launch Application](https://utmzonefinder.netlify.app/)**

Try it now! Click anywhere on the map to see the UTM zone.

---

## 📋 Table of Contents

- [Features](#-features)
- [What is UTM?](#-what-is-utm)
- [How It Works](#-how-it-works)
- [Technologies](#-technologies)
- [Installation](#-installation)
- [Usage](#-usage)
- [Base Layers](#-base-layers)
- [Offline Capability](#-offline-capability)
- [Browser Support](#-browser-support)
- [Contributing](#-contributing)
- [License](#-license)
- [Acknowledgments](#-acknowledgments)

---

## ✨ Features

### Core Functionality

- 🎯 **One-Click UTM Detection**: Simply click anywhere on the map to instantly calculate the UTM zone
- 📍 **Precise Coordinates**: Displays exact latitude and longitude values for clicked locations
- 🧮 **Accurate Calculations**: Uses the standard UTM zone formula for reliable results
- 🌍 **Hemisphere Detection**: Automatically determines Northern (N) or Southern (S) hemisphere

### User Interface

- 🎨 **Faded Gray Aesthetic**: Professional muted grayscale map styling
- ➕ **Crosshair Cursor**: Precision targeting for accurate location selection
- ⏱️ **Auto-fade Popups**: Results automatically disappear after 3 seconds for a clean interface
- 🧭 **North Arrow**: Visual orientation indicator
- 📏 **Scale Control**: Distance scale for reference

### Map Layers

- 🗺️ **Multiple Base Layers**: Toggle between 4 different map styles
  - OpenStreetMap (Default)
  - Satellite Imagery
  - Topographic Maps
  - Humanitarian Style
- 📶 **Offline Capability**: Default layer works offline after initial tile caching
- 🔄 **Layer Switcher**: Easy toggle control in the top-right corner

### Technical Features

- ⚡ **No Backend Required**: Pure client-side application
- 📱 **Fully Responsive**: Works on desktop, tablet, and mobile devices
- 🚀 **Fast Loading**: Lightweight with minimal dependencies
- 🔒 **Secure**: HTTPS compatible, no data collection

---

## 🌎 What is UTM?

The **Universal Transverse Mercator (UTM)** coordinate system divides the Earth into a grid of zones for accurate positioning and mapping.

### UTM Grid System

- **60 Zones**: The Earth is divided into 60 longitudinal zones
- **Zone Width**: Each zone spans 6° of longitude
- **Numbering**: Zones are numbered 1-60 from west to east, starting at 180°W
- **Hemispheres**: Each zone is divided into Northern (N) and Southern (S) hemispheres at the equator

### Common Applications

- Military and defense mapping
- Surveying and engineering
- GPS navigation
- Geographic Information Systems (GIS)
- Scientific research
- Land management and cadastral systems

### Example UTM Zones

- **New York City**: UTM Zone 18N
- **London, UK**: UTM Zone 30N
- **Tokyo, Japan**: UTM Zone 54N
- **Sydney, Australia**: UTM Zone 56S
- **Nairobi, Kenya**: UTM Zone 37S

---

## ⚙️ How It Works

### UTM Zone Calculation

The application uses the standard mathematical formula to calculate UTM zones:

```javascript
UTM_zone = floor((longitude + 180) / 6) + 1;
```

**Where:**

- `longitude` = the longitude of the clicked point (in decimal degrees)
- `floor()` = rounds down to the nearest integer
- The result is a number between 1 and 60

### Hemisphere Determination

```javascript
hemisphere = latitude >= 0 ? "N" : "S";
```

**Where:**

- `latitude >= 0` = Northern Hemisphere (N)
- `latitude < 0` = Southern Hemisphere (S)

### Example Calculation

**Location**: Nairobi, Kenya

- Latitude: -1.2921°
- Longitude: 36.8219°

**Calculation:**

```
UTM_zone = floor((36.8219 + 180) / 6) + 1
         = floor(216.8219 / 6) + 1
         = floor(36.1370) + 1
         = 36 + 1
         = 37

Hemisphere = -1.2921 < 0 → 'S'

Result: UTM Zone 37S
```

---

## 🛠️ Technologies

### Core Technologies

- **HTML5**: Structure and content
- **CSS3**: Styling and responsive design
- **JavaScript (ES6)**: Application logic and interactivity

### Libraries & APIs

- **[Leaflet.js](https://leafletjs.com/)** (v1.9.4): Interactive mapping library
- **[OpenStreetMap](https://www.openstreetmap.org/)**: Default map tiles
- **[Esri World Imagery](https://www.arcgis.com/)**: Satellite base layer
- **[OpenTopoMap](https://opentopomap.org/)**: Topographic base layer
- **[Humanitarian OSM](https://www.hotosm.org/)**: Humanitarian style tiles

### Graphics

- **SVG**: Scalable vector graphics for the north arrow
- **CSS Filters**: Grayscale and brightness adjustments

---

## 📥 Installation

### Option 1: Direct Download

1. Download the repository:

   ```bash
   git clone https://github.com/kibetbrian74/utm_zone_finder.git
   cd utm_zone_finder
   ```

2. Open `index.html` in your web browser

### Option 2: Local Web Server

Using Python:

```bash
# Python 3
python -m http.server 8000

# Python 2
python -m SimpleHTTPServer 8000
```

Using Node.js:

```bash
npx http-server
```

Using PHP:

```bash
php -S localhost:8000
```

Then navigate to `http://localhost:8000` in your browser.

### Option 3: VS Code Live Server

1. Install the "Live Server" extension in VS Code
2. Right-click on `index.html`
3. Select "Open with Live Server"

---

## 🎮 Usage

### Basic Usage

1. **Open the Application**: Navigate to the live demo or local instance
2. **View the Map**: The map loads centered on the world view
3. **Click a Location**: Click anywhere on the map
4. **View Results**: A popup appears showing:
   - UTM Zone number and hemisphere (e.g., "UTM Zone 37S")
   - Latitude and longitude coordinates
5. **Auto-close**: The popup automatically fades after 3 seconds

### Changing Map Layers

1. Locate the **layer control** in the top-right corner
2. Click to expand the layer options
3. Select from available base layers:
   - **Offline Map (Default)**: Standard OpenStreetMap
   - **Satellite (Online)**: Aerial imagery
   - **Topographic (Online)**: Terrain and elevation
   - **Humanitarian (Online)**: Humanitarian mapping style

### Navigation Controls

- **Zoom In/Out**: Use the `+` and `-` buttons or scroll wheel
- **Pan**: Click and drag the map
- **Reset View**: Zoom out to see the entire world
- **Scale**: Reference the scale bar in the bottom-left corner

### Tips for Best Results

- **Crosshair Cursor**: Use the crosshair for precise clicking
- **Multiple Clicks**: Click as many locations as you want
- **Offline Usage**: Load the default map first, then work offline
- **Mobile**: Tap anywhere on the map on mobile devices

---

## 🗺️ Base Layers

### 1. Offline Map (Default)

- **Provider**: OpenStreetMap
- **Style**: Standard street map
- **Offline**: ✅ Yes (after initial cache)
- **Best For**: General use, offline work

### 2. Satellite (Online)

- **Provider**: Esri World Imagery
- **Style**: Aerial/satellite imagery
- **Offline**: ❌ No (requires internet)
- **Best For**: Identifying physical features, terrain

### 3. Topographic (Online)

- **Provider**: OpenTopoMap
- **Style**: Topographic with contours
- **Offline**: ❌ No (requires internet)
- **Best For**: Elevation, terrain analysis

### 4. Humanitarian (Online)

- **Provider**: HOT OSM
- **Style**: Humanitarian-focused mapping
- **Offline**: ❌ No (requires internet)
- **Best For**: Crisis mapping, aid operations

---

## 📶 Offline Capability

### How Offline Mode Works

The default OpenStreetMap layer supports offline usage through browser tile caching:

1. **Initial Load**: When you first visit, tiles are downloaded from the server
2. **Browser Cache**: Your browser automatically caches the tiles
3. **Offline Access**: Previously viewed areas remain accessible without internet
4. **Limitations**: Only cached areas work offline; new areas require internet

### Enabling Full Offline Support

For complete offline capability:

1. **Pre-cache Areas**: Navigate and zoom around areas you'll need
2. **Browser Storage**: Ensure your browser allows sufficient cache storage
3. **Service Workers**: Consider implementing a service worker for enhanced caching

### Cache Duration

- Tiles remain cached based on browser settings (typically 1-7 days)
- Clear cache will require re-downloading tiles
- Different browsers have different cache limits

---

## 🌐 Browser Support

### Fully Supported Browsers

| Browser | Version | Status             |
| ------- | ------- | ------------------ |
| Chrome  | 90+     | ✅ Fully Supported |
| Firefox | 88+     | ✅ Fully Supported |
| Safari  | 14+     | ✅ Fully Supported |
| Edge    | 90+     | ✅ Fully Supported |
| Opera   | 76+     | ✅ Fully Supported |

### Mobile Browsers

| Platform | Browser          | Status             |
| -------- | ---------------- | ------------------ |
| iOS      | Safari           | ✅ Fully Supported |
| iOS      | Chrome           | ✅ Fully Supported |
| Android  | Chrome           | ✅ Fully Supported |
| Android  | Firefox          | ✅ Fully Supported |
| Android  | Samsung Internet | ✅ Fully Supported |

### Requirements

- JavaScript must be enabled
- Cookies/LocalStorage enabled (for tile caching)
- Internet connection (for initial load and online layers)

---

## 🤝 Contributing

Contributions are welcome! Here's how you can help:

### Reporting Bugs

1. Check if the bug has already been reported
2. Open a new issue with:
   - Clear description of the bug
   - Steps to reproduce
   - Expected vs actual behavior
   - Browser and OS information
   - Screenshots if applicable

### Suggesting Features

1. Open an issue describing the feature
2. Explain the use case and benefits
3. Discuss implementation approaches

### Submitting Pull Requests

1. Fork the repository
2. Create a feature branch: `git checkout -b feature/amazing-feature`
3. Make your changes
4. Test thoroughly
5. Commit: `git commit -m 'Add amazing feature'`
6. Push: `git push origin feature/amazing-feature`
7. Open a Pull Request

### Code Style Guidelines

- Use consistent indentation (2 spaces)
- Write clear, descriptive variable names
- Comment complex logic
- Follow existing code patterns
- Test on multiple browsers

---

## 📄 License

This project is licensed under the **MIT License** - see the [LICENSE](LICENSE) file for details.

### What This Means

✅ Commercial use  
✅ Modification  
✅ Distribution  
✅ Private use

**Conditions:**

- Include original license and copyright notice
- Provide attribution

---

## 🙏 Acknowledgments

### Map Data & Tiles

- **OpenStreetMap Contributors**: Map data and default tiles
- **Esri**: Satellite imagery
- **OpenTopoMap**: Topographic tiles
- **Humanitarian OpenStreetMap Team**: HOT style tiles

### Libraries & Tools

- **Leaflet.js**: Powerful open-source mapping library
- **GitHub**: Code hosting and collaboration
- **Netlify/Vercel**: Free deployment platforms

### Inspiration

- UTM coordinate system standardization
- GIS community feedback and requirements
- Modern web mapping best practices

### Special Thanks

- All contributors who improve this project
- Users who report bugs and suggest features
- Open-source community for tools and libraries

---

## 📞 Contact & Support

### Get Help

- 📖 **Documentation**: Read this README
- 🐛 **Bug Reports**: [Open an issue](https://github.com/kibetbrian74/utm_zone_finder/issues)
- 💡 **Feature Requests**: [Start a discussion](https://github.com/kibetbrian74/utm_zone_finder/discussions)
- ❓ **Questions**: Check existing issues or create a new one

### Stay Updated

- ⭐ **Star this repository** to follow updates
- 👁️ **Watch** for notifications on changes
- 🔔 **Subscribe** to release notifications

### Connect

- **GitHub**: [@kibetbrian74](https://github.com/kibetbrian74/)
- **Email**: bkibetcheuiyot@gmail.com
- **LinkedIn**: [Brian_Cheruiyot] (https://www.linkedin.com/in/brian-kibet-cheruiyot74/)

---

## 📊 Project Stats

![GitHub stars](https://img.shields.io/github/stars/kibetbrian74/utm_zone_finder?style=social)
![GitHub forks](https://img.shields.io/github/forks/kibetbrian74/utm_zone_finder?style=social)
![GitHub issues](https://img.shields.io/github/issues/kibetbrian74/utm_zone_finder)
![GitHub pull requests](https://img.shields.io/github/issues-pr/kibetbrian74/utm_zone_finder)

---

## 🗺️ UTM Zone Reference Map

```
Zone    Longitude Range
────────────────────────
  1     180°W - 174°W
  2     174°W - 168°W
  3     168°W - 162°W
  ...
 30     006°W - 000°
 31     000°  - 006°E
 32     006°E - 012°E
  ...
 59     168°E - 174°E
 60     174°E - 180°E
```

**Hemisphere Division:**

- Northern (N): 0° to 84°N
- Southern (S): 0° to 80°S

---

## Suggestions Welcome!

Have an idea? [Open an issue](https://github.com/yourusername/utm_zone_finder/issues) with the "enhancement" label.

---

## 📚 Additional Resources

### Learn More About UTM

- [USGS UTM Grid System](https://www.usgs.gov/faqs/what-does-term-utm-mean-utm-better-or-more-accurate-latitudelongitude)
- [UTM on Wikipedia](https://en.wikipedia.org/wiki/Universal_Transverse_Mercator_coordinate_system)
- [Understanding Map Projections](https://www.esri.com/arcgis-blog/products/arcgis-pro/mapping/gcs_vs_pcs/)

### Web Mapping Resources

- [Leaflet Documentation](https://leafletjs.com/reference.html)
- [OpenStreetMap Wiki](https://wiki.openstreetmap.org/)
- [Web Mapping Tutorial](https://maptimeboston.github.io/leaflet-intro/)

---

<div align="center">

**Made with ❤️ for the GIS community**

⭐ **Star this repo if you find it useful!** ⭐

[Report Bug](https://github.com/kibetbrian74/utm_zone_finder/issues) · [Request Feature](https://github.com/kibetbrian74/utm_zone_finder/issues) · [View Demo](https://utmzonefinder.netlify.app/)

</div>

---

_Last Updated: February 2026_
