# San Francisco Amenity Access: Parks, Schools, and Healthcare Facilities
Matt Renfro

## Research Questions
**What is the geographic distribution of amenities in San Francisco?**

**How accessible are these amenities?**

**Who has access?**

## Data Sources
- Parks: DataSF, Recreation and Parks Properties

- K-12 Public schools: CA Dep of Education, California Schools 2022-23

- Health care facilities: DataSF,Health Care Facilities

- Demographic information: ACS

## Methodology Overview
**Geographic distribution:** Map census tracts and amenities
- Drop census tracts with populaiton of 0 or null
- Generate centroids for each census tract
- Sanp census tract centroids to the nearest node on network
- _Repeat this process for parks, snap school and healthcare facility points to network_
  
**Measuring accessibility:** Calculate cumulative accessibility metrics using network
- Calculate the number of parks/schools/healthcare facilities within 1000 meter walking distance from each census tract node
- Calculate the shortest path and distance (in meters) from each census tract node to the nearest park/school/healthcare facility
- Rank census tracts by the number of parks/schools/healthcare facilities within 1000 meter walking distance and shortest distance to the nearest park/school/healthcare facility

**Analyzing who has access:** Use demographic information such as race/ethnicity and income to measure who has access to amenities 

## Findings - Geographic Distribution and Accessibility Metrics
### Parks

I cleaned the parks property dataset by dropping the following park property types : Mini Park, Community Garden, Civic Plaza or Square, Other Non-Park Property, Library, Real Estate/Administrative Services property, Family Camp, and Concession. 

**Figure 1.0: Geographic Distribution of Parks in SF**

<iframe src="index/park_map.html" width="100%" height="600px"></iframe>

Figure 1.0 shows the geographic distribution of parks in San Francisco. Parks provide important recreational, health, environmental, and communal benefits for cities. San Francsico  has a reputation of being very park accessible TODO: link article. Golden Gate Park was recently nominated for best park in the nation TODO: link. I was curious to see which areas in San Francisco have the best park accessibility in terms of the number of parks within a 1000m walking distance

**Figure 1.1: Number of Parks Within a 1000m Walking Distance by Census Tract (Percentile Ranking)**
<iframe src="index/parks_percentile.html" width="100%" height="600px"></iframe> 

Figure 1.1 is a choropleth map of census tracts in San Francisco detailing cumulative park accessibility metrics for each tract.  After calculating the number of parks within 1000 meters walking distance on the network from each snapped census tract centroid, I then cut these values into percentiles. This process provides a stronger comparison between census tracts in San Francisco.

TODO: ranking based off of distance nearest park

### Schools

Figure 2.0 details the geographic distribution of public schools in San Francisco. I used a marker cluster to aggregate different school locations and displayed these on the map.

**Figure 2.0: Geographic Distribution of Public Schools in SF**
<iframe src="index/schools_map.html" width="100%" height="600px"></iframe>

Figure 2.1 is a choropleth map of census tracts in San Francisco detailing cumulative school accessibility metrics for each tract.  After calculating the number of schools within 1000 meters walking distance on the network from each snapped census tract centroid, I then cut these values into percentiles like I did with parks.

**Figure 2.1: Number of Schools Within a 1000m Walking Distance by Census Tract (Percentile Ranking)**
<iframe src="index/school_percentile.html" width="100%" height="600px"></iframe>

TODO: ranking based off of distance to nearest school

### Healthcare Facilities
Figure 3.0 details the geographic disribution of healthcare facilities in San Francisco. I used simple circle markers to plot these points to gain more experience with diffferent marker types in folium.

**Figure 3.0: Geographic Distribution of Healthcare Facilities**
<iframe src="index/health_map.html" width="100%" height="600px"></iframe>

Figure 3.1 is a choropleth map of census tracts detailing cumulative healthcare accessibility metrics for each tract in the city. I followed the same process to produce this map as I did with parks and schools: I sorted the number of healthcare within 1000 meters walking distances into a percentile ranking and assigned these percentiles a color in the choropleth color ramp.

<iframe src="index/healthcare_percentile.html" width="100%" height="600px"></iframe>


## Findings - Analyzing Who Has Access
### Parks
### Schools
### Healthcare Facilities

## Conlcusion and Limitations
As I 
