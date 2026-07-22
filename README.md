<p align="center">
  <img src="logo.png" width="96" alt="Lattice" />
</p>

# Lattice Terminal

A Bloomberg Terminal alternative built for quantitative analysts. Keyboard-first, data-dense, wired to live market data.

## Download

Get the latest release from the [Releases](https://github.com/dillonsnyman1/lattice-releases/releases/latest) page.

| Platform | File |
|---|---|
| macOS Apple Silicon (M1/M2/M3/M4) | `Lattice_x.x.x_aarch64.dmg` |
| macOS Intel | `Lattice_x.x.x_x64.dmg` |
| Windows | `Lattice_x.x.x_x64-setup.exe` |
| Linux | `Lattice_x.x.x_amd64.AppImage` |

**macOS first launch:** the app is not notarized through the App Store, so macOS may block it. Right-click the app icon, select Open, and confirm.

**Linux:** make the AppImage executable (`chmod +x Lattice_*.AppImage`) before running it.

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

See the [Changelog](https://github.com/dillonsnyman1/lattice-releases/blob/main/CHANGELOG.md) for a full list of what's included in each release.
