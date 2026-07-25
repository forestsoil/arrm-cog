# arrm-cog
Land hot spotter COG hosting repo
# arrm-cog

Pre-computed Cloud-Optimised GeoTIFFs (COGs) for the ARRmapper suite.  
Served via GitHub Pages to support HTTP range requests from `appHotspot.html`.

## Rasters

| File | Project | Layer | Period |
|------|---------|-------|--------|
| `asha1_flood_freq.tif` | Asha 1 (Jalpaiguri, Alipurduar, Coochbehar) | Flood frequency (NDWI) | 2013–present |
| `asha1_stress_score.tif` | Asha 1 | Drought/barrenness stress (BSI) | 2013–present |
| `asha2_flood_freq.tif` | Asha 2 Tea (+ Darjeeling, Kalimpong) | Flood frequency (NDWI) | 2013–present |
| `asha2_stress_score.tif` | Asha 2 Tea | Drought/barrenness stress (BSI) | 2013–present |
| `arun_flood_freq.tif` | Arun (Namsai, Changlang, Lohit, Lower Dibang Valley, East Siang) | Flood frequency (NDWI) | 2015–present |
| `arun_stress_score.tif` | Arun | Drought/barrenness stress (BSI) | 2015–present |
| `banani_flood_freq.tif` | Banani (Birbhum, Bankura, Purulia, Jhargram, Paschim Bardhaman) | Flood frequency (NDWI) | 2015–present |
| `banani_stress_score.tif` | Banani | Drought/barrenness stress (BSI) | 2015–present |

**Resolution:** 30 m (Landsat 8/9)  
**CRS:** EPSG:4326  
**Source:** Google Earth Engine via `geemap` + `geedim`; converted to COG with `rio-cogeo`

## Usage

Files are accessible at:
```
https://forestsoil.github.io/arrm-cog/{filename}
```

COG structure supports HTTP range requests — clients fetch only the tile window covering a plot or village boundary, not the full raster.

## Update cadence

Re-run `arr_cog_export_v2.py` annually (or after a significant new wet season) and commit the replacement files. The script end-date is set to run-date automatically.

## Related

- [forestsoil/ARRmapper](https://github.com/forestsoil/ARRmapper) — field tool suite
