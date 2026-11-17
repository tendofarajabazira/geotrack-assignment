# GeoTrack Professional — GIS Location Intelligence

**Project:** GeoTrack: A Web-Based Real-Time Location Tracking and Geospatial Analysis System  
**Type:** Undergraduate GIS web-app prototype  
**Live application:** https://tendofarajabazira.github.io/geotrack-assignment/  
**Source:** https://github.com/tendofarajabazira/geotrack-assignment

## Overview
GeoTrack is a consent-based, mobile-friendly browser app that visualizes the **device owner's** reported position on an interactive map. It supports one-off location reads, foreground updates, simulated routes, accuracy circles, distance estimates, a configurable geofence, and exports to CSV / GeoJSON.

## Technology
- HTML, CSS, JavaScript — responsive interface and application logic
- Browser Geolocation API — permission-based `getCurrentPosition()` and `watchPosition()`
- Leaflet 1.9.4 — interactive mapping and geospatial overlays
- OpenStreetMap tiles — basemap with attribution
- GitHub Pages — static HTTPS hosting
- WGS84 (EPSG:4326) — geographic coordinate reference system

## How to run locally (Linux)
From the folder containing `index.html`:

```bash
python3 -m http.server 8765
```

Then open `http://localhost:8765` in a browser. For live positioning on a phone, use the **HTTPS** GitHub Pages link.

## Controls
| Control | What it does |
|---|---|
| Locate me once | Requests one position from your device (permission required) |
| Start live | Requests position updates while this page is open and visible |
| Stop | Stops the active location watch or demonstration |
| Demo route | Plays a **simulated** Mbarara route, not a GPS measurement |
| Reset | Clears positions, distance, route and geofence centre |
| Geofence size | Chooses a 50, 100, 200 or 500 m radius |
| Select geofence centre on map | Arm the control, click the map once, and draw a zone centred at that point |
| Export CSV / GeoJSON | Downloads collected positions and applicable route geometry |
| Recenter / Fit route | Navigates to current position or recorded route |

## Privacy and limitations
- The user must grant browser location permission. This app cannot track other people remotely.
- Coordinates are processed in the browser and are **not sent to a GeoTrack backend**; map tiles are requested from OpenStreetMap's service and may reveal the map area being viewed.
- Geolocation may combine GPS, Wi-Fi, and cellular positioning. This app does **not** directly implement cell tower triangulation or IP geolocation.
- Continuous updates are designed for a **visible foreground browser tab**, not background surveillance.
- Geofence results and route distance are estimates; location uncertainty and device jitter affect the outcome.
- Demo data is clearly marked as simulated. Keep real-location screenshots and exported files private when they could reveal home or workplace coordinates.

## System architecture
```text
[User on phone or computer]
              |
              v
[Browser permission + Geolocation API]
              |
              v
[JavaScript coordinates / accuracy / timestamp]
              |
        +-----+-------+
        |             |
        v             v
 [Leaflet map]    [In-memory records]
        |             |
  Markers, route,     CSV / GeoJSON
  geofence, accuracy  manual export
        |
 [OpenStreetMap tiles requested over internet]
```

## Run the tests
See `TEST_CHECKLIST.md` for a reproducible manual test log. Distinguish **observed passes** from **not yet tested**; do not label simulated data as actual GPS testing.

## Suggested applications
Consent-based route mapping for field surveys, logistics, school transport visualization, tourism, and volunteered emergency location sharing. These are potential applications rather than supported multi-user features of the current prototype.

## References
- MDN Geolocation API: https://developer.mozilla.org/en-US/docs/Web/API/Geolocation_API
- MDN watchPosition(): https://developer.mozilla.org/en-US/docs/Web/API/Geolocation/watchPosition
- Leaflet documentation: https://leafletjs.com/
- OpenStreetMap tile policy: https://operations.osmfoundation.org/policies/tiles/
- GitHub Pages documentation: https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site
