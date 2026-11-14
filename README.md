# 🌍 EarthWatch AI

**Tap anywhere on Earth and see its environmental risk, powered by NASA satellite data.**

🔗 **Live demo:** https://earthwatch-ai.vercel.app/

Built for the **NASA Space Apps Challenge 2026**.

---

## What it does

EarthWatch AI is an interactive 3D globe. Spin and zoom the Earth, tap any place, and a pin drops with a panel showing the current environmental picture in plain language:

- **Flood risk:** Low, Medium or High, with a short explanation
- **Rainfall:** last 7 days, last 30 days and the wettest day
- **Soil wetness:** from dry to saturated
- **Vegetation change:** an early sign of deforestation or drought
- **Search:** find any city, region or coordinates (for example `23.8, 90.4`)
- **NASA layers:** toggle vegetation, rainfall rate and active fires over the globe
- **India view:** all 35 states and union territories ranked by flood risk, with a tap-through to each state's full report

## NASA data used

| Data | Source | Used for |
|---|---|---|
| Rainfall and soil wetness | NASA POWER | Flood risk, rainfall panel |
| Vegetation index | MODIS (via ORNL DAAC) | Vegetation change |
| Satellite imagery | NASA GIBS (Blue Marble, vegetation, rainfall rate, fires) | Globe and overlays |

Place search uses OpenStreetMap Nominatim.

## How it works

1. You tap a point on the globe, which gives a latitude and longitude.
2. The app requests NASA POWER and MODIS data for that location.
3. A rule-based formula combines rainfall, soil wetness and vegetation change into a risk level.
4. The result appears in a side panel with a one-line summary.

If NASA services can't be reached, the app falls back to clearly labelled **sample data** and shows a badge so you always know which mode you're in. A badge reading **Live NASA data** means real values.

## Run it locally

This is a single static file. No install or build step is needed.

1. Download `index.html`.
2. Open it in Chrome.

## Limitations (honest notes)

- The risk score is a **simple rule-based formula**, not a trained machine-learning model, and it has **not been validated** against recorded flood events.
- In the India view, each state is read at a single point and shown as one dot, not as a shaded state outline.
- The globe uses one whole-Earth image, so very close zoom looks soft.

## Roadmap

- Train and validate a model against past events (for example the 2018 Kerala floods)
- Real state boundary outlines for the India view
- Rainfall and vegetation trend charts over time
- Alerts for high-risk areas

## Credits

NASA POWER, NASA GIBS and MODIS data courtesy of NASA. Place search by OpenStreetMap contributors.
