# Tactical GeoAR

A spatial computing web application for  navigation and augmented reality viewing of equipment

The application utilizes OpenStreetMap (Leaflet) and location-based WebXR (A-Frame + AR.js) to anchor and render 3D glTF/GLB training models directly at their real-world WGS84 geographic coordinates.

---

## Architecture Overview

- **Decoupled Geospatial Data**: Simulator metadata, scale parameters, and coordinates are isolated in `simulators.json`.
- **Edge-to-Edge Viewport**: Switches cleanly between an inverted, high-contrast tactical 2D map and an in-situ mobile AR camera view.
- **WGS84 Real-World Anchoring**: Uses AR.js `gps-new-entity-place` to render 3D models at exact latitude and longitude positions relative to the user's GPS hardware location.
- **Dynamic Proximity Tracking**: Runs the Haversine formula against active coordinates to update the distance to the nearest training simulator in real time.
- **Environmental Telemetry**: Queries Open-Meteo REST endpoints for local surface wind velocity and ambient temperature.

---

## File Structure

```text
.
├── index.html          # Application markup, styling, Leaflet and AR pipeline
├── simulators.json     # WGS84 registry of simulator locations and GLB definitions
├── README.md           # Documentation
└── models/             # 3D GLB simulation assets
    ├─model.glb
    ├─model.usdz
