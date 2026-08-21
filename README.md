# Albuquerqulator

Enter your location and a destination (defaults to Albuquerque, NM), pick a travel mode, and find out how many times you could listen to Weird Al Yankovic's "Albuquerque" (11:23) on the way there.

## Live demo

_Add your GitHub Pages link here once it's live, e.g. `https://yourname.github.io/albuquerqulator`_

## Features

- Address autocomplete as you type, powered by OpenStreetMap Nominatim
- Editable destination (defaults to Albuquerque, NM, but can be changed to anywhere)
- Three travel modes:
  - **Driving** — real road routing via OSRM
  - **Walking** — real pedestrian routing via OpenStreetMap's foot-routing server
  - **Blimp** — straight-line ("as the crow flies") distance at a 35 mph cruise speed, plus a 15-minute mooring/prep buffer
- Automatically recalculates when you switch travel modes
- No build step, no dependencies — a single self-contained HTML file

## How it works

1. **Geocoding** — your typed location and destination are converted to coordinates using [Nominatim](https://nominatim.openstreetmap.org).
2. **Routing** — driving and walking distances/times come from public [OSRM](https://project-osrm.org) routing servers. Blimp mode uses the Haversine formula for great-circle distance, since blimps don't follow roads.
3. **The Weird Al math** — total travel time (in seconds) is divided by 683 seconds (11:23), the runtime of "Albuquerque" from the 1999 album *Running with Scissors*.

## Contributing

Pull requests are welcome. Some ideas for extending this:

- Additional travel modes (bike, train, hot air balloon)
- A picker for other long songs to benchmark against
- Showing the remainder as "and 40% of the way through verse 3"
- Support for round-trip calculations

## Notes and limitations

- Nominatim and OSRM are free public services with fair-use rate limits — fine for personal or small-scale use, but not built for heavy traffic.
- Blimp mode is a simplified estimate (straight-line distance, fixed cruise speed) rather than a real flight plan.
- Driving and walking times don't account for traffic, weather, or road closures.

## License

MIT — see [LICENSE](LICENSE) for details. Fork it, extend it, make it your own.
