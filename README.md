# Catchment Hydrology — Lecture 2 (Europe edition): The runoff ratio of European catchments

[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/wberghuijs/EStreams_Lecture_RunoffRatio/main?filepath=Lecture_EStreams_RunoffRatio.ipynb)

A Binder-launchable companion to [`CatchmentHydro_Lecture2_RunoffRatio`](https://github.com/wberghuijs/CatchmentHydro_Lecture2_RunoffRatio)
(which uses CAMELS, US catchments), built the same way but for **EStreams** — a pan-European
catalogue of streamflow, hydro-climatic signatures and landscape descriptors covering **17,130
gauged catchments in 41 countries** (Nascimento et al., 2024, *Scientific Data*).

Click the *launch binder* badge above (once this repo is on GitHub) to open the notebook in a
ready-to-run Jupyter environment — no local installation needed. To run it locally instead:

```bash
pip install -r requirements.txt
jupyter notebook Lecture_EStreams_RunoffRatio.ipynb
```

## What's in this repo

- `Lecture_EStreams_RunoffRatio.ipynb` — the interactive lecture notebook: an intro to the runoff
  ratio and the Budyko framework, followed by interactive histogram, scatter, map and correlation
  tools (built with `ipywidgets`) for exploring EStreams, plus a set of discussion questions.
- `requirements.txt` — Python dependencies for Binder / local use.
- `data/` — a bundled subset of EStreams (see below).

## Data

The `data/` folder contains the **summary tables** from EStreams, one row per catchment
(`basin_id`):

| file | content |
|---|---|
| `estreams_hydrometeo_signatures.csv` | hydro-climatic signatures (runoff ratio, aridity, baseflow index, seasonality, ...) |
| `estreams_gauging_stations.csv` | gauge metadata (coordinates, country, drainage area, record length, ...) |
| `estreams_topography_attributes.csv` | elevation, slope, stream density, ... |
| `estreams_soil_attributes.csv` | soil texture, water capacity, rooting depth, ... |
| `estreams_vegetation_attributes.csv` | monthly LAI / NDVI climatology |
| `estreams_hydrology_attributes.csv` | dams, reservoirs, lakes |
| `estreams_geology_attributes.csv` | lithology fractions |
| `estreams_snowcover_attributes.csv` | monthly snow-cover climatology |
| `estreams_meteorology_density.csv` | density of the weather-station network behind the E-OBS interpolation |

This is a small fraction of the full EStreams release — the daily streamflow and meteorological
time series (one file per catchment, tens of GB in total) and the full catchment-boundary
shapefiles are **not** included, both because of their size and, for streamflow specifically,
because a number of national data providers restrict redistribution of the raw series (see
"License & attribution" below). Get the complete archive from Zenodo if you need those.

## License & attribution

EStreams itself is compiled from many underlying sources with different terms, documented in full
in the `appendix/licenses.txt` file of the original release. Two things worth knowing before you
reuse or extend this repo:

- The meteorological signatures here (`p_mean`, `pet_mean`, `aridity`, `p_seasonality`,
  `frac_snow`, ...) are derived from the **E-OBS** dataset, whose data policy restricts use to
  *non-commercial research and non-commercial education* — which is exactly what this notebook is
  for. Please respect that if you reuse this data elsewhere.
- Raw daily streamflow (and therefore this repo does **not** include it) is subject to
  per-provider redistribution terms; about a quarter of the ~65 national/regional providers behind
  EStreams mark their data "no redistribution". The derived signatures and landscape attributes
  bundled here are the same aggregate tables already published openly as part of the EStreams
  Zenodo archive.

If you use this notebook or the data, please cite:

> Nascimento, T. V. M., Rudlang, J., Höge, M., van der Ent, R., Chappon, M., Seibert, J.,
> Hrachowitz, M., & Fenicia, F. (2024). EStreams: An integrated dataset and catalogue of
> streamflow, hydro-climatic and landscape variables for Europe. *Scientific Data*, 11, 879.
> https://doi.org/10.1038/s41597-024-03706-1

Dataset (Zenodo): https://doi.org/10.5281/zenodo.13154470
Code / tools: https://doi.org/10.5281/zenodo.13255133 (mirrored at [thiagovmdon/EStreams](https://github.com/thiagovmdon/EStreams))
