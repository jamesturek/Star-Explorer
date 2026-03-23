# Star Explorer

An interactive space data science project built from real astronomical catalogs and NASA APIs. Contains two notebooks: a Hertzsprung-Russell stellar classification diagram and a near-Earth asteroid close approach tracker.

![HR Diagram](hr_diagram_preview.png)

---

## Projects

### 1. Hertzsprung-Russell Diagram (`star_explorer.ipynb`)

An interactive HR diagram built from the HYG star catalog containing 107,860 stars from the Hipparcos, Yale Bright Star, and Gliese catalogs.

#### What is the Hertzsprung-Russell Diagram?

The Hertzsprung-Russell (HR) diagram is one of the most important tools in astronomy. It plots stars by two properties:

- **X axis: Colour Index (B-V)** — a measure of a star's temperature. Negative values (left) are hot blue stars. Positive values (right) are cool red stars.
- **Y axis: Absolute Magnitude** — a star's intrinsic brightness, independent of its distance from Earth. Brighter stars sit higher on the chart.

When you plot enough stars, distinct structures emerge that reveal the life cycle of stars:

| Region | Description |
|---|---|
| **Main Sequence** | The diagonal band running top-left to bottom-right. This is where stars spend most of their lives fusing hydrogen into helium. The Sun sits here. |
| **Red Giants** | Upper-right region. Stars that have exhausted their hydrogen and expanded enormously. Betelgeuse and Antares are examples. |
| **Supergiants** | Top of the diagram. Extremely luminous, massive stars with short lifespans. Rigel and Deneb sit here. |
| **White Dwarfs** | Lower-left. The dense, cooling remnants of dead stars. Van Maanen's Star is one of the nearest. |
| **Red Dwarfs** | Lower-right. Small, dim, cool stars. The most common type in the galaxy. Proxima Centauri and Wolf 359 are examples. |

#### Spectral Classification

| Class | Colour | Temperature | Example |
|---|---|---|---|
| O | Blue | > 30,000 K | Naos |
| B | Blue-white | 10,000-30,000 K | Rigel |
| A | White | 7,500-10,000 K | Sirius |
| F | Yellow-white | 6,000-7,500 K | Procyon |
| G | Yellow | 5,200-6,000 K | The Sun |
| K | Orange | 3,700-5,200 K | Arcturus |
| M | Red | < 3,700 K | Betelgeuse |

Mnemonic: **O**h **B**e **A** **F**ine **G**uy/**G**irl, **K**iss **M**e.

#### Data Source

The [HYG Database](https://www.astronexus.com/projects/hyg) (v3.7), a compilation of stellar data from Hipparcos, Yale Bright Star, and Gliese catalogs. Licensed under [CC BY-SA 2.5](https://creativecommons.org/licenses/by-sa/2.5/).

---

### 2. Near-Earth Asteroid Tracker (`asteroid_explorer.ipynb`)

An interactive tracker of near-Earth asteroid close approaches built from NASA's NeoWs API, covering 7,940 close approaches from one year back to six months forward.

#### What are Near-Earth Objects?

Near-Earth Objects (NEOs) are asteroids and comets with orbits that bring them within 1.3 AU of the Sun. NASA's Planetary Defense Coordination Office tracks these objects and maintains a Sentry list of objects requiring active monitoring.

| Term | Definition |
|---|---|
| **Potentially Hazardous Asteroid (PHA)** | Passes within 0.05 AU of Earth and is larger than ~140m |
| **Sentry Object** | Actively monitored by NASA's impact risk assessment system |
| **Lunar Distance (LD)** | ~384,400 km. Used as a standard unit for close approach distances. |

#### Dataset Summary

- **7,940** total close approaches tracked
- **358** potentially hazardous asteroids
- **571** Sentry objects under active monitoring
- **Closest approach:** (2025 UC11) at 6,599 km, closer than many satellites
- **Fastest approach:** (2022 HB4) at 52.9 km/s

#### Visuals

1. **Close Approach Scatter Plot** — All 7,940 objects plotted by date and miss distance. Bubble size scaled to estimated diameter. Red rings indicate potentially hazardous asteroids. Moon reference line at 1 LD.
2. **Animated Timeline** — Month-by-month animation of close approaches building over time, with play/pause and scrub controls.

#### Data Source

[NASA NeoWs API](https://api.nasa.gov). Free API key available at api.nasa.gov. The DEMO_KEY works for testing but is rate limited to 30 requests per hour.

---

## Getting Started

### Requirements

```bash
pip install -r requirements.txt
```

### Data Setup

**HR Diagram:** Run the first cell in `star_explorer.ipynb` to download `hygdata_v37.csv.gz` locally.

**Asteroid Tracker:** Get a free API key at `https://api.nasa.gov` and paste it into the `API_KEY` variable in `asteroid_explorer.ipynb`. The notebook fetches fresh data on each run.

### Running

Open in VS Code with the Jupyter extension installed, or run:

```bash
jupyter notebook
```

---

## Repo Structure

```
star-explorer/
  star_explorer.ipynb        HR diagram notebook
  asteroid_explorer.ipynb    Near-Earth asteroid tracker
  hr_diagram.html            Interactive HR diagram
  hr_diagram_preview.png     Preview image
  asteroid_approaches.html   Close approach scatter plot
  asteroid_animated.html     Animated close approach timeline
  hygdata_v37.csv.gz         HYG star catalog (gitignored)
  requirements.txt           Python dependencies
```

---

## Tools

- **Python:** pandas, numpy, plotly, requests
- **Data:** HYG v3.7 stellar catalog, NASA NeoWs API
- **Environment:** Jupyter Notebook / VS Code

## Author

James Turek — [jamesturek.github.io](https://jamesturek.github.io)

MSc Geographic Data Science, London School of Economics
