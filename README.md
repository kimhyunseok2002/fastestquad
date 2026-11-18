# SPEED-QUAD TS5

Interactive 3D model and spec sheet of the **SPEED-QUAD TS5**, a 5-inch, 6S tail-sitter quad built for straight-line speed, with a fully 3D-printed airframe (rev. v4.1). It is a design study modeled in Fusion 360 and has not yet been printed or flown.

By **Top Secret Aero** · Instagram [@topsecret.aero](https://www.instagram.com/topsecret.aero/)

## Files

| File | Contents |
| --- | --- |
| `index.html` | The whole site: the spec sheet and the three.js viewer. three.js and the fonts load from public CDNs. |
| `model.json` | The airframe's 32 parts, exported from the Fusion 360 model (2.9 MB). |
| `flow.json` | Airflow streamlines for the 3D view (100 KB): a potential-flow model of the fuselage and nacelle pods plus a prop-slipstream model. It shows the flow pattern; it is not CFD. |

There is no build step. In `model.json`, each part holds base64-encoded float32 positions in millimetres (three.js Y-up), int8 normals and uint16/uint32 triangle indices.

## Deploy on Vercel

Import this repository at [vercel.com/new](https://vercel.com/new) and keep the defaults: framework preset **Other**, no build command, no output directory. Every push to `main` redeploys the site.

## Run locally

The page loads `model.json` with `fetch`, so serve the folder over HTTP. Opening `index.html` straight from disk will not load the model.

```
python -m http.server 8000
```

Then open http://localhost:8000.
