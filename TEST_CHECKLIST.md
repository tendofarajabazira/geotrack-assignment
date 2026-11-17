# GeoTrack — Manual Testing Checklist

**Test date:** __________  **Tester:** __________  **Browser / device:** __________

Mark each test **Pass / Fail / Not tested** and save evidence of the result.

| ID | Test and action | Expected result | Actual result | Status |
|---|---|---|---|---|
| T01 | Open HTTPS site on Linux | Professional interface and map load | | |
| T02 | Open HTTPS site on iPhone | Responsive mobile layout and tiles load | | |
| T03 | Click Demo route | Blue simulated polyline and marker appear | | |
| T04 | Inspect statistics after demo | Non-zero route distance and record counts; simulated label | | |
| T05 | Select geofence centre, then click map | Orange circle moves to selected place | | |
| T06 | Change radius 100 m → 200 m | Circle visibly expands | | |
| T07 | Click CSV after data available | CSV file downloads with timestamp / coordinates / source | | |
| T08 | Click GeoJSON after data available | GeoJSON FeatureCollection downloads | | |
| T09 | Reset | Blue route and data clear | | |
| T10 | On iPhone, tap Locate me once and grant permission | Device-reported position appears; source is not DEMO | | |
| T11 | On iPhone, tap Start live, keep Safari open | One or more location updates arrive; status is Live | | |
| T12 | Tap Stop | No further tracking; user controls request | | |
| T13 | Deny location permission | Helpful error; no successful fix | | |
| T14 | On a deliberate geofence crossing test (if safe) | Status changes with uncertainty accounted for | | |

**Privacy:** Only test with the device owner's permission. Avoid exporting or posting private residential coordinates. A static position does NOT establish that a route has been recorded in real time. Do not simulate real movement by claiming Demo route is actual GPS.

**Evidence file names:**
- `01_dashboard_desktop.png`
- `02_demo_route_simulated.png`
- `03_geofence_selected.png`
- `04_location_once_device.png` (redact home coordinates if sharing)
- `05_export_files.png`

## Notes and known limitations
____________________________________________________________________________
____________________________________________________________________________
