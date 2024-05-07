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
- Drop census tracts with population of 0 or null
- Generate centroids for each census tract
- Snap census tract centroids to the nearest node on network
- _Repeat this process for parks; snap school and healthcare facility points to network_


**Measuring accessibility:** Calculate cumulative accessibility metrics using network
- Calculate the number of parks/schools/healthcare facilities within 1000 meter walking distance from each census tract network node
- Calculate the shortest path and distance (in meters) from each census tract node to the nearest park/school/healthcare facility
- Rank census tracts by the number of parks/schools/healthcare facilities within 1000 meter walking distance and shortest distance to the nearest park/school/healthcare facility

**Analyzing who has access:** Use demographic information such as race/ethnicity and income to measure who has access to amenities 




## Findings - Geographic Distribution and Accessibility Metrics
### Parks

I cleaned the parks property dataset by dropping the following park property types : Mini Park, Community Garden, Civic Plaza or Square, Other Non-Park Property, Library, Real Estate/Administrative Services property, Family Camp, and Concession. 

**Figure 1.0: Geographic Distribution of Parks in SF**

<iframe src="index/park_map.html" width="100%" height="600px"></iframe>

Figure 1.0 shows the geographic distribution of parks in San Francisco. Parks provide important recreational, health, environmental, and communal benefits for cities. San Francisco  has a reputation of having some of the [best parks in the country](https://www.axios.com/local/san-francisco/2023/06/05/san-francisco-best-parks-ranking). In fact, Golden Gate Park was recently nominated for [best city park in the nation](https://www.kron4.com/news/bay-area/golden-gate-park-nominated-for-best-city-park-in-u-s/).  I was curious to see which areas in San Francisco have the best park accessibility in terms of the number of parks within a 1000m walking distance.

**Figure 1.1: Number of Parks Within a 1000m Walking Distance by Census Tract (Percentile Ranking)**
<iframe src="index/parks_percentile.html" width="100%" height="600px"></iframe> 

Figure 1.1 is a choropleth map of census tracts in San Francisco detailing cumulative park accessibility metrics for each tract.  After calculating the number of parks within 1000 meters walking distance on the network from each snapped census tract centroid, I then cut these values into percentiles. This process provides a stronger comparison between census tracts in San Francisco.



### Schools

Figure 2.0 details the geographic distribution of public schools in San Francisco. I used a marker cluster to aggregate different school locations and displayed these on the map.

**Figure 2.0: Geographic Distribution of Public Schools in SF**
<iframe src="index/schools_map.html" width="100%" height="600px"></iframe>

Figure 2.1 is a choropleth map of census tracts in San Francisco detailing cumulative school accessibility metrics for each tract.  After calculating the number of schools within 1000 meters walking distance on the network from each snapped census tract centroid, I then cut these values into percentiles like I did with parks.

**Figure 2.1: Number of Schools Within a 1000m Walking Distance by Census Tract (Percentile Ranking)**
<iframe src="index/school_percentile.html" width="100%" height="600px"></iframe>



### Healthcare Facilities
Figure 3.0 details the geographic distribution of healthcare facilities in San Francisco. I used simple circle markers to plot these points to gain more experience with different marker types in folium.


**Figure 3.0: Geographic Distribution of Healthcare Facilities**
<iframe src="index/health_map.html" width="100%" height="600px"></iframe>

Figure 3.1 is a choropleth map of census tracts detailing cumulative healthcare accessibility metrics for each tract in the city. I followed the same process to produce this map as I did with parks and schools: I sorted the number of healthcare facilities within 1000 meters walking distances into a percentile ranking and assigned these percentiles a color in the choropleth color ramp.

**Figure 3.1: Number of Healthcare Facilities Within a 1000m Walking Distance by Census Tract (Percentile Ranking)**
<iframe src="index/healthcare_percentile.html" width="100%" height="600px"></iframe>


## Limitations
The process of using networks to calculate the number of parks/schools/healthcare facilities offers a better measure of accessibility than relying on straight census tract centroid to amenity distance calculations. The network analyses takes into account the walking paths people actually traverse to get to the amenity destination. This measure of accessibility emphasizes the quantity of a given amenity, and thus, rewards tracts that have a higher number of a given amenity within 1000 meters walking distance. However, this measure does not consider the quality of the amenity or other features of an amenity that might make it more or less accessible, beneficial, or desirable for an individual. 

For instance, while I provided a rough control for park properties by removing properties that did not fit my definition of a park, this approach did  not take into account overall quality of a given park. Families with young kids might rank a park with an large playground structure higher than a park with an extensive trail network. 

The cumulative accessibility calculation that uses a walking network also has limitations as the nearest amenity on a walking network might not always be the most accessible. For example, people living with disabilities and seniors may prefer amenities near transit stops or with accessible parking.

Finally there are limitations on the amenity type. The accessibility of a school and healthcare facility varies by individual. An nearby high school might not be the most relevant for a family with young children, for them a nearby preschool or elementary school could be of greater importance. In terms of healthcare facilities, some may not be accepting new patients or be covered by an individual's health insurance. 




## Next Steps
- Explore who is able to access amenities: While I was able to conduct network analyses to determine cumulative accessibility metrics, I was unable to examine the relationship between demographic factors and amenity accessibility. A next step would be to use Census tract data for characteristics such as race/ethnicity, age, education, and income to test for correlations between demographic features and amenity access. These findings would yield significant information about who is being served by existing amenities and who is being left out.
-  Explore amenity quality: A next step could be compile park visitor ratings from online sources for each park to measure quality. I could similarly compile reviews and ratings for schools and healthcare facilities to build a measure of overall amenity quality. 






# Conclusion
This research delved into the geographic distribution and accessibility of parks, schools, and healthcare facilities in San Francisco, aiming to address questions regarding their accessibility and who has access. I used a comprehensive methodology involving mapping census tracts and amenities, leveraging network analyses, and calculating accessibility metrics. This research revealed the geographic distribution of parks, schools, and healthcare facilities across San Francisco, highlighting areas with higher concentrations of these amenities. Accessibility metrics were calculated to assess the number of amenities within a 1000-meter walking distance from each census tract, providing insights into the overall accessibility landscape of the city.

Future research could delve deeper into understanding who has access to amenities by integrating demographic data and examining correlations between demographic characteristics and amenity accessibility. Overall, this research serves as a foundational exploration of amenity accessibility in San Francisco, laying the groundwork for future study to further explore the dynamics of urban accessibility and equity. By addressing disparities in amenity access, policymakers and urban planners can foster more inclusive and equitable communities.

