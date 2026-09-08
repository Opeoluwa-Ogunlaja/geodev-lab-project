Project brief

# The Question
Which farms in Ibadan are prone to flooding during high rainfall based on distance to water bodies and elevation?

## Data Needed

- Ibadan LGA boundary
- Farms in Ibadan
- Rivers in Ibadan
- Road network data for map context

## Data Sources

| Data needed | Source | Dataset / query | Format |
|---|---|---|---|
| Ibadan LGA boundary | GRID3 | [GRID3 NGA – Operational LGA Boundaries](https://data.grid3.org/datasets/GRID3::grid3-nga-operational-lga-boundaries/about) (774 features, CC BY 4.0) | GeoPackage / Shapefile |
| Farms in Ibadan | OSM via QuickOSM | `landuse=farmland`, `landuse=farmyard`, `landuse=orchard`, `landuse=plantation` — clipped to Ibadan | GeoPackage |
| Farms — coverage backstop | Digital Earth Africa | [Cropland Extent Map 2019, 10 m](https://docs.digitalearthafrica.org/en/latest/data_specs/Cropland_extent_specs.html) (`crop_mask_western`) | COG raster |
| Rivers in Ibadan | OSM via QuickOSM | `waterway=river`, `waterway=stream`; add `natural=water` for reservoirs (Eleyele, Asejire) | GeoPackage |
| Rivers — network backstop | HydroSHEDS | HydroRIVERS, Africa | Shapefile |
| Road network | OSM via QuickOSM | `highway=*` — extracted for Ibadan | GeoPackage |
| Roads — bulk alternative | Geofabrik | Nigeria extract, `gis_osm_roads_free_1` | Shapefile / PBF |
