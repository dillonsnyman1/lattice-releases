# Lattice Terminal

A Bloomberg Terminal alternative built for quantitative analysts. Keyboard-first, data-dense, wired to live market data.

## Download

Get the latest release from the [Releases](https://github.com/dillonsnyman1/lattice-releases/releases/latest) page.

| Mac | File |
|---|---|
| Apple Silicon (M1/M2/M3/M4) | `Lattice_x.x.x_aarch64.dmg` |
| Intel | `Lattice_x.x.x_x64.dmg` |

Open the `.dmg`, drag Lattice to Applications, and launch it.

**First launch:** macOS may block the app since it is not notarized through the App Store. Right-click the app icon, select Open, and confirm.

## Updates

Lattice checks for updates automatically on startup. When a new version is available, a green chip appears in the top bar showing the version number. Click it to install and restart.

## Configuration

Open **CFG** inside the app. Most data sources work without any setup. Optional API keys:

| Provider | Used for |
|---|---|
| Polygon.io | Real-time US equity data (free tier available, falls back to Yahoo Finance without it) |
| OANDA | CFD trading: FX, indices, commodities (free practice account available) |
| MyShipTracking | Vessel tracking on the globe view |

Everything else (SEC EDGAR, US Treasury yields, World Bank macro, USGS earthquakes, NOAA storms, commodity prices) is free and requires no configuration.

## Features

Full feature list and keyboard shortcuts are in the [User Guide](https://github.com/dillonsnyman1/lattice/blob/main/docs/USER_GUIDE.md).
