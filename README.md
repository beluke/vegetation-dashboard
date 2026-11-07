# Conservation Area Vegetation Health

Interactive web map of growing-season NDVI anomalies for four conservation areas
in the San Francisco Bay Area.

**Live map:** https://beluke.github.io/vegetation-dashboard/

## What it shows

- **NDVI anomaly** = median NDVI for May–Sep 2026 minus the median for May–Sep 2016–2025.
  Brown = browner than normal, teal = greener than normal.
- Popups show current NDVI, baseline NDVI, anomaly, condition label, and the number of
  250 m land pixels each average is based on.
- Headquarters locations are a separate layer you can turn on and off.

## Workflow

1. **Google Earth Engine:** loaded MODIS NDVI, kept good-quality growing-season pixels,
   calculated current and baseline medians and the anomaly, masked water, and ran zonal
   statistics per conservation area.
2. **Python (geopandas):** joined the results to the conservation-area boundaries.
3. **Folium:** built the interactive map (choropleth, popups, tooltips, layer control).

## Data sources

- NDVI: NASA MODIS Terra MOD13Q1 v061 (250 m, 16-day composites), via Google Earth Engine
- Basemap imagery: Esri, Maxar, Earthstar Geographics
- Conservation area boundaries and HQ locations: course-provided sample data
