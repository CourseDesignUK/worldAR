# FSC Tactical GeoAR

A single-file spatial computing web application designed for on-site navigation and augmented reality inspection of training rigs at the Fire Service College (FSC), Moreton-in-Marsh. 

The application integrates OpenStreetMap (Leaflet) with location-based WebXR (A-Frame + AR.js) to render 3D glTF/GLB training assets anchored directly to their real-world WGS84 geographic coordinates.

---

## Features

- **Edge-to-Edge Viewport Architecture**: Seamlessly toggles between an inverted, high-contrast tactical 2D map and a full-screen camera AR overlay.
- **WGS84 Real-World Spawning**: Binds 3D simulation assets directly to physical latitude and longitude coordinates using `gps-new-entity-place`.
- **Dynamic Haversine Telemetry**: Computes range and bearing to the nearest training simulator in real time.
- **Micro-Climate Telemetry**: Pulls live wind speed, wind direction, and surface temperature via the Open-Meteo API.
- **Zero-Dependency Toolchain**: Bundled into a standalone, zero-build single HTML file running pure vanilla ES6+ and CDN-backed web components.

---

## Spatial Asset Registry

| Node ID | Simulator Asset | Coordinates (Lat, Lng) | Asset Model |
| :--- | :--- | :--- | :--- |
| `sim-2` | Cat 10 Rig (A380 ARFF) | `51.996011, -1.683188` | `models/rig.glb` |
| `sim-3` | ARFF Rig C-17 | `51.998301, -1.678853` | `models/arff.glb` |
| `sim-4` | Merlin Helicopter Sim | `51.996062, -1.682645` | `models/merlin.glb` |
| `sim-5` | Industrial A Scenario Trainer | `51.995724, -1.677713` | `models/IndA.glb` |
| `sim-6` | Cessna Airframe Sim | `52.000157, -1.678911` | `models/cessna.glb` |
| `sim-7` | Tornado Fast Jet Sim | `51.998965, -1.678473` | `models/f3.glb` |
| `sim-8` | Lynx Helicopter Trainer | `52.000487, -1.677733` | `models/lynx.glb` |
| `sim-9` | Main Drill Tower | `51.995679, -1.678509` | `models/mdt.glb` |
| `sim-10` | USAR Complex | `51.995794, -1.674954` | `models/usar.glb` |
| `sim-11` | College Gymnasium | `51.991110, -1.676447` | `models/gym.glb` |

---

## Directory Structure

To deploy the application, ensure the directory structure matches the referenced static assets:

```text
.
├── index.html
├── models/
│   ├── rig.glb
│   ├── arff.glb
│   ├── merlin.glb
│   ├── IndA.glb
│   ├── cessna.glb
│   ├── f3.glb
│   ├── lynx.glb
│   ├── mdt.glb
│   ├── usar.glb
│   └── gym.glb
└── README.md
