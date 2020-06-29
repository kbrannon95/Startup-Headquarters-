# Startup-Headquarters

# Business Problem
For this project we will investigate neighborhoods in Chicago, New York City, and Toronto to determine which city and neighborhood a mid sized start-up company should choose for its headquarters. The selection process for a budding company's main office can be strenuous, and its often hard to figure out the best location without physically being in the city. For business reasons they have narrowed their search to Chicago, New York (Manhattan or Brooklyn only), and Toronto, but have no way to decide which city is best.  The company leaders have decided that they would like to put their office in a fun and vibrant neighborhood with plenty of good food and bars nearby for their employees. In addition, they would like the neighborhood to not be overpopulated to avoid congestion. The output of this project will be a recommendation of the ideal city and neighborhood for the start-up's office and the findings will be presented to the executive team.  

# Data
I will be using neighborhood location data sets for Chicago, New York City, and Toronto. First, we will need the name and coordinates of each neighborhoods in each city. 

For New York City, we find the data is publicly available at https://geo.nyu.edu/catalog/nyu_2451_34572
For Chicago, we find the neighborhoods and their coordinates at https://data.cityofchicago.org/Facilities-Geographic-Boundaries/Boundaries-Community-Areas-current-/cauq-8yn6 
For Toronto, we will scrape neighborhood data from the webpage https://en.wikipedia.org/wiki/List_of_postal_codes_of_Canada:_M and then find the coordinates of the neighborhoods here https://cocl.us/Geospatial_data

An example of the resulting data for Toronto is shown below.

Neighborhood	      Latitude	    Longitude	
Parkwoods\n	        43.753259	    -79.329656	
Parkwoods\n	        43.753259	    -79.329656	
Parkwoods\n	        43.753259	    -79.329656	
Victoria Village\n	43.725882	    -79.315572	
Victoria Village\n	43.725882	    -79.315572

I will leverage the Foursquare API explore endpoint to retrieve the name, location, and category for venues close to each neighborhood in each city. An example of this data for Toronto is shown below.

Neighborhood          Venue	                    Latitude      Longitude     Category
Parkwoods\n	          Brookbanks Park	          43.751976	    -79.332140	  Park
Parkwoods\n	        	Variety Store	            43.751974	    -79.333114	  Food & Drink Shop
Parkwoods\n	         	Corrosion Service	        43.752432	    -79.334661	  Construction & Landscaping
Victoria Village\n	  Victoria Village Arena	  43.723481	    -79.315635	  Hockey Arena
Victoria Village\n	  Portugril	                43.725819	    -79.312785	  Portuguese Restaurant

Finally, I will use publicly available census data for the population of neighborhoods in each city. This will best the metric we use for how congested a neighborhood is. 

For New York City, we find the data at https://data.cityofnewyork.us/City-Government/New-York-City-Population-By-Neighborhood-Tabulatio/swpk-hqdp 
For Chicago, we find the data at https://en.wikipedia.org/wiki/Community_areas_in_Chicago
For Toronto, we find the data at https://en.wikipedia.org/wiki/Demographics_of_Toronto_neighbourhoods

An example of the data for New York City is shown below.

Neighborhood      Population
Bay Ridge	        80539
Sunset Park West	52312
Carroll Gardebs	  38327
Sunset Park East	66150
