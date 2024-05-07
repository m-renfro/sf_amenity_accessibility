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
  
**Measuring accessibility:** Calculate accessibility metrics using network
- Calculate the number of parks/schools/healthcare facilities within 1000 meter walking distance from each census tract node
- Calculate the shortest path and distance (in meters) from each census tract node to the nearest park/school/healthcare facility
- Rank census tracts by the number of parks/schools/healthcare facilities and shortest distance to parks/schools/healthcare facilities 

**Analyzing who has access:** Use demographic information such as race/ethnicity and income to measure who has access to amenities 

## Findings - Geographic Distribution and Accessibility Metrics
### Parks

The park property data set from DataSF contains information. I cleaned the parks data by dropping the following park property types : Mini Park, Community Garden, Civic Plaza or Square, Other Non-Park Property, Library, Real Estate/Administrative Services property, Family Camp, and Concession. 

<iframe src="index/park_map.html" width="100%" height="600px"></iframe>

Figure 1 shows the geographic distribution of parks in San Francisco. Parks provide important recreational, health, environmental, and communal benefits for cities. San Francsico  has a reputation of being very park accessible TODO: link article. Golden Gate Park was recently nominated for best park in the nation TODO: link. I was curious to see which areas in San Francisco have the best park accessibility.

TODO: Insert 

### Schools

Geographic distribution of public schools in San Francisco. I used a marker cluster to aggregate different school locations and display on the map.

<iframe src="index/schools_map.html" width="100%" height="600px"></iframe>


### Healthcare Facilities
Geographic disribution of healthcare facilities in San Francisco
<iframe src="index/health_map.html" width="100%" height="600px"></iframe>

## Findings - Analyzing Who Has Access
### Parks
### Schools
### Healthcare Facilities

## Conlcusion 
