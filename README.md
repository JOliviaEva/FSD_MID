# BannaMap – Student Edition

Find what's open near your PG or hostel in Bengaluru, by need.

BannaMap is a single-page web app for students living in PGs and hostels. At 11 pm you need a pharmacy, not a brand name. Pick what you need, say where you are, and BannaMap lists nearby places on a map and shows which are open right now. *Banna* means "colour" in Kannada.

## Features

- **Search by need:** study spots, coffee, food, medicine, ATM and cash, print and stationery, groceries and laundry, parks.
- **Open-now check:** reads the OpenStreetMap `opening_hours` tag, including overnight hours and 24/7 places.
- **Listing completeness:** flags places missing hours, phone or website, with a link to add them on OpenStreetMap.
- **Radius slider:** 300 m to 5 km, with an estimated walking time.
- **Sort and filter:** nearest, open now first, most complete, A to Z. Filter to places with hours or open now.
- **Interactive map:** Leaflet map with pins, a search-radius circle, and "Show on map" from each card.
- **My board:** save favourite places (kept in your browser), then download them as JSON or copy them as a list.
- **Form validation:** inline feedback for the area name and the need selection.
- **Resilient by design:** if the live services can't be reached, the app falls back to clearly labelled sample listings, and the map falls back through several free tile providers.

## Tech stack

| Part | What it uses |
|---|---|
| UI | HTML, Tailwind CSS (CDN), vanilla JavaScript |
| Map | [Leaflet](https://leafletjs.com/) with free tile providers (Esri, OSM France, OpenStreetMap) |
| Geocoding | [Nominatim](https://nominatim.org/) |
| Places data | [Overpass API](https://overpass-api.de/) (OpenStreetMap) |
| Storage | `localStorage` for the saved board |

No build step, no backend, no API keys.

## Run it

1. Download or clone this repo.
2. Open `Index.html` in a modern browser.

Then visit `https://fsd-five-fawn.vercel.app/`.

An internet connection is needed for live results. Without one, the **Use sample data** option still lets you explore the app.

## How to use

1. Type your PG, college or area, or tap a quick-area button such as Koramangala or HSR Layout.
2. Pick what you need.
3. Set how far you're willing to walk.
4. Press **Find places**.
5. Sort, filter, save places to your board, and download them as JSON.

## Notes and limitations

- Results depend on OpenStreetMap coverage. Some places lack names, hours or phone numbers; the app marks them so you can improve the data.
- The open-now check supports common `opening_hours` patterns. Unusual rules show "Check the hours".
- Public Nominatim and Overpass servers are rate-limited. If they're busy, wait a few seconds and retry.
- Some school, college or office networks intercept HTTPS and block map tiles. Try another network if the map background is blank.
- Sample listings are fictional and labelled "Demo data".

## Credits

Map data © [OpenStreetMap contributors](https://www.openstreetmap.org/copyright) (ODbL). Search by Nominatim, places by the Overpass API.
