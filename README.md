========================================================
                   A T I S   L O C A T O R
========================================================

ATIS Locator is a lightweight, client-side web application 
designed to automatically detect your current geographical 
location and route you to the nearest live Digital ATIS 
(D-ATIS) feed provided by ATIS.guru.

--------------------------------------------------------
FEATURES
--------------------------------------------------------
* Automatic Location Detection: Utilizes the HTML5 
  Geolocation API to find your current coordinates.

* Human-Readable Locations: Integrates with the OpenStreetMap 
  Nominatim API to translate raw coordinates into identifiable 
  city or region names.

* Distance Calculation: Employs the Haversine formula to 
  accurately calculate the great-circle distance between 
  your location and a database of 535 supported global 
  aerodromes.

* Top 10 List: Displays the 10 nearest airports in a clean, 
  touch-friendly list.

* Auto-Redirect Timer: Features a built-in 10-second 
  countdown that automatically routes the browser to the 
  nearest aerodrome's ATIS feed if no manual selection is made.

--------------------------------------------------------
REPOSITORY STRUCTURE
--------------------------------------------------------
* index.html: The main application file containing the UI 
  layout, CSS styling, and execution logic.

* wikipedia_airports.js: A static JSON object containing the 
  exact latitude and longitude coordinates for all 535 ICAO 
  codes supported by the application.

--------------------------------------------------------
HOW IT WORKS
--------------------------------------------------------
1. Upon loading, the browser prompts the user for location access.
2. Once granted, the script fetches the user's latitude and 
   longitude.
3. The script iterates through the wikipedia_airports.js 
   database, calculating the distance to each aerodrome.
4. The array is sorted by distance, and the top 10 results 
   are rendered on the screen.
5. A 10-second timer begins. If the user clicks a specific 
   airport, the script immediately redirects to 
   https://atis.guru/atis/{ICAO}. If the timer hits zero, 
   it automatically redirects to the top result.

--------------------------------------------------------
HOSTING & DEPLOYMENT
--------------------------------------------------------
This project is built entirely with client-side technologies 
(HTML, CSS, Vanilla JavaScript) and requires no backend server. 

It is designed to be hosted on static hosting services like 
GitHub Pages. Note that the HTML5 Geolocation API requires the 
site to be served over a secure HTTPS connection to function 
properly.

--------------------------------------------------------
DEPENDENCIES & APIS
--------------------------------------------------------
* ATIS.guru: The target destination for live D-ATIS feeds.
  (https://atis.guru)

* Nominatim (OpenStreetMap): Used for reverse-geocoding 
  coordinates into city names.
  (https://nominatim.openstreetmap.org/)

* Wikipedia API: Used to source the static coordinate database.
