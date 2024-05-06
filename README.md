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

**Analyzing who has access:** Use demographic information such as race/ethnicity and income to measure who has access to amenities 

## Findings - Geographic Distribution and Accessibility Metrics
### Parks
### Schools
### Healthcare Facilities
