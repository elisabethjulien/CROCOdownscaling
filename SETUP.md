# Setup

## Pre-processing toolkit

- **Software:** CROCO Pytools v2.0.6
- citation?
- **Source archive:** `croco_pytools-v2.0.6.tar.gz` (not included in this repo)
- **Run on:** [WSL2 Ubuntu aarch64 / HPC name + OS]
- **Environment:** `croco_pyenv`, created from the toolkit's `env.yml`

## Installation

```bash
tar -xzf croco_pytools-v2.0.6.tar.gz
cd croco_pytools-v2.0.6
conda env create -f env.yml
conda activate croco_pyenv
```

### Deviations from the stock `env.yml`

- [e.g. removed `wxpython` (only needed for croco_pyvisu); or "none"]
- [any package pinned or changed, and why]

### Reproducing the exact environment

```bash
conda env create -f environment.yml
```

(`environment.yml` in this repo is the export of the environment actually used.)

## Data sources

| Component | Dataset | Notes |
|-----------|---------|-------|
| Open boundaries / initial conditions | Mercator (CMEMS) [product name] | [period, resolution] |
| Surface forcing | ERA5 | via `ONLINE` cppkey / `download_era5` |
| Rivers | GloFAS | [rivers included, passive tracers] |

Credentials (Copernicus CDS, Copernicus Marine) are stored locally and never committed.

## Configuration files

| Step | Tool | Config file |
|------|------|-------------|
| Grid | `prepro/make_grid` | `config/[file]` |
| Boundaries | `prepro/make_bry` | `config/[file]` |
| Initial conditions | `prepro/make_ini` | `config/[file]` |
| Rivers | `prepro/make_rivers` | `config/[file]` |

## Not in this repo

Large NetCDF inputs and outputs live at: [HPC path / Zenodo link].
