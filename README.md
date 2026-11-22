# AERPAW ISAC Drone Tracking Lab

Interactive browser simulator for UAV tracking and simultaneous communication at Lake Wheeler Field Labs.

## Run locally

Download or clone this repository, then run from its root:

```sh
python3 -m http.server 8000
```

Open http://localhost:8000 and select **Start tracking**. The numerical simulation runs in the browser. No build step, package installation, API key, or radio hardware is required.

## Publish with GitHub Pages

For a public repository, open **Settings → Pages**. Select **Deploy from a branch**, **main**, and **/(root)**, then save. GitHub Pages will display the published address after deployment.

## Features

- Enable LW1–LW4 independently and configure sectors and heights.
- Select 4, 8, 16, 32, or 64 antennas and 650 MHz, 1.8 GHz, or 3.4 GHz.
- Compare cooperative uplink SRS, PRS/DMRS/SSB echo sensing, and SRS–PRS fusion.
- Select monostatic, bistatic, or combined echo geometry.
- Run five Phase 1 trajectories and choose editable Group 1–3 RCS profiles.
- Observe tracking errors, communication goodput, and resource tradeoffs.
- Export the current configuration, track, and tradeoff data.

## Model and map assumptions

Results use synthetic measurements and an illustrative propagation, reference-resource, and tracking model. They have not been field validated. Arrays are proposed configurations. Sharp-turn routes are kinematic stress cases with no aircraft dynamics. The frame diagram illustrates configured resources.

Tower and geofence coordinates are derived from the [AERPAW deployment map](https://aerpaw.org/deployment-areas/). The satellite image uses approximate registration, including the 100 m eastward image correction that places the overlays farther west relative to the imagery. The application retains Google Maps and imagery attribution. Map and imagery content is excluded from the software license.

## Files

- `index.html` contains the interface and styles.
- `app.js` connects controls, plots, exports, and simulation.
- `engine.js` implements the measurement and tracking model.
- `routes.js` contains the constrained flight paths.
- `view.js` draws the map and frame schematic.
- `satellite-google.jpg` supplies the map background.
