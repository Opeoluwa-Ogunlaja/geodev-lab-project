Project brief

# The Question
Which farms in Ibadan are prone to flooding during high rainfall based on distance to water bodies and elevation?

## Data Needed

- Ibadan LGA boundary
- Farms in Ibadan
- Rivers in Ibadan
- Road network data for map context

## Data Sources

| Data needed | Source | Dataset / query | Format | Notes |
|---|---|---|---|---|
| Ibadan LGA boundary | GRID3 | [GRID3 NGA – Operational LGA Boundaries](https://data.grid3.org/datasets/GRID3::grid3-nga-operational-lga-boundaries/about) (774 features, CC BY 4.0) | GeoPackage / Shapefile | Filter `statename = 'Oyo'`, then select the Ibadan LGAs. Dissolve to one polygon for a single study-area boundary. |
| Farms in Ibadan | OSM via QuickOSM | `landuse=farmland`, `landuse=farmyard`, `landuse=orchard`, `landuse=plantation` — clipped to Ibadan | GeoPackage | Coverage in Nigeria is thin and volunteer-dependent. Expect gaps. |
| Farms — coverage backstop | Digital Earth Africa | [Cropland Extent Map 2019, 10 m](https://docs.digitalearthafrica.org/en/latest/data_specs/Cropland_extent_specs.html) (`crop_mask_western`) | COG raster | Continuous cropland presence/absence. Fills the holes OSM leaves; excludes grazing land and perennial crops. |
| Rivers in Ibadan | OSM via QuickOSM | `waterway=river`, `waterway=stream`; add `natural=water` for reservoirs (Eleyele, Asejire) | GeoPackage | Main channels — Ogunpa, Ona, Omi — are reasonably mapped. |
| Rivers — network backstop | HydroSHEDS | HydroRIVERS, Africa | Shapefile | Consistent topology for upstream/downstream or catchment logic. Coarse (15 arc-sec) at city scale. |
| Road network | OSM via QuickOSM | `highway=*` — extracted for Ibadan | GeoPackage | For a basemap, `motorway/trunk/primary/secondary/tertiary/residential` is usually enough. |
| Roads — bulk alternative | Geofabrik | Nigeria extract, `gis_osm_roads_free_1` | Shapefile / PBF | Faster than QuickOSM if the bounding box is large enough that the Overpass query times out. |
