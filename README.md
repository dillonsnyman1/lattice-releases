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

## Privacy

Lattice runs entirely on your machine. No usage data, watchlists, portfolio positions, or API keys are sent to or stored on any external server controlled by this project.

All app data (watchlists, saved screens, order history, settings) is kept in a local SQLite database on your own device.

The only outbound connections are ones you initiate:

- **Market data providers** (Yahoo Finance, Polygon.io, SEC EDGAR, etc.): read-only requests for prices and reference data
- **OANDA**: only if you connect a trading account; all communication goes directly between the app and OANDA's own servers
- **Your LLM provider** (OpenAI, Anthropic, Ollama, etc.): only if you configure the AI assistant; requests go directly to whichever API you set up using your own key

API keys are stored locally in the app's config directory on your device and are never transmitted anywhere by Lattice.

## Documentation

- [User Guide](https://github.com/dillonsnyman1/lattice-releases/blob/main/USER_GUIDE.md) — features, keyboard shortcuts, and configuration details
- [Changelog](https://github.com/dillonsnyman1/lattice-releases/blob/main/CHANGELOG.md) — what changed in each release
