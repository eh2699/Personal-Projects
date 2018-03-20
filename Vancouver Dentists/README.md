## Geocoding Vancouver's Dental Offices

A dentist friend was looking to get a sense of where dental offices are located in Greater Vancouver, so I made a project out of it. Simply googling 'dentists in Vancouver' does not yield a comprehensive set of information or graphics, so I pulled the information off of BC Dental Association's 'Find a Dentist' directory using POST and GET requests to fill the initial HTML form on the website. 

The file `BCDA_scraper.ipynb` contains codes for scraping. The same code can be used over and over to scrape metadata of the dental offices listed on the page (dentist name, street address, city, postal code, phone number, and office name where available). The same code can be used by simply changing the `'ctl00$mainContent$drpCity'` field in the `params` dictionary. Theses codes as prescribed by the BCDA website can be gained through source inspection. For the purpose of this analysis, dental office locations of 10 major cities were scraped:
- Burnaby
- Coquitlam
- Langley
- New Westminster
- North Vancouver
- Pitt Meadows
- Port Moody
- Richmond
- Vancouver
- West Vancouver

Each city data were scraped, and cleaned, and were used to generate geolocation (latitude/longitude) using the googlemaps and geocoder libraries. Each city data were saved as separate `.cvs` file, and `BCDA_scrape_compile.ipynb` contains codes for combining the 10 individual files into one that contains geodata for 705 dental offices.

The locations were overlayed on top of a choropleth map depicting 2015 median household income, which were the most recent available data at the time of extraction. The data was taken from the Canadian government's census website. The `census_subdivisions_median_income_households_2015.csv` and `census_tract_shp` were cleaned and joined based on the census tract id to create a comprehensive dataset containing the median household income for corresponding census tract boundaries, which could then be uploaded to Carto to be mapped interactively. You can find the map [here](https://columbialibraries.carto.com/u/eh2699/builder/deae4f44-6257-4fe6-a739-3fc6aa24ab43/embed). 

Each point represents a dental office, and can be clicked to reveal further information about the office/dentist. The shades of blue represents varying range of median household income, with darker blues representing higher median household income. It's important to note, however, that certain census tracts have been 'grayed out' or may not be entirely accurate in its income representations due to lack of data. 

