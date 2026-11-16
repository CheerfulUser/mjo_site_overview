# Ōtehīwai Mt John Observatory site overview

A 3D view of the Mt John summit with the current weather, Sun and Moon, and the pointing and status of each telescope. It is served as a static page by GitHub Pages; open `index.html` from any web server (for example `python3 -m http.server`) to run it locally.

**Development zone:** the telescope states and replay history (`history_mock/`) are mock data driven by recorded MJO weather node1 measurements.

## Files

| File | Contents | Written by |
|---|---|---|
| `index.html` | The viewer (three.js r128, Astronomy Engine 2.1.19 from CDNs) | |
| `terrain_heights.bin`, `terrain_texture.jpg`, `model.json`, `buildings.json` | Terrain, aerial photo, telescope geometry and building meshes | `site_map/build_3d_model.py` |
| `building_styles.json` | Building colours sampled from site photos | by hand |
| `config.json` | Viewer settings and closure limits | by hand |
| `telescope_state.json`, `weather_state.json`, `alerts_state.json` | Current state, polled by the viewer | `site_map/feeds/*.py` |
| `history_mock/` | Replay history, one JSON-lines file per UTC day and kind, listed in `index.json` | `site_map/feeds/make_mock_history.py` |

All links between files are relative.

## Data credits

Terrain (LiDAR DEM and DSM) and aerial photo: [LINZ](https://data.linz.govt.nz/), CC BY 4.0. Building footprints: © [OpenStreetMap](https://www.openstreetmap.org/copyright) contributors, ODbL. Weather: MJO weather node1, University of Canterbury.
