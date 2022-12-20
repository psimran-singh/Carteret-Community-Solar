# Carteret, New Jersey - Potential for Community Solar

### What is Community Solar?
Community solar is an ambitious attempt to tackle the issue of inequality in access to cheap renewable energy. While wealthier homeowners may be able to afford the significant upfront cost of installing rooftop solar, low-to-moderate income households are often left behind in the transition to green energy. Community solar allows installations on commercial, public, non-profit buildings to provide low-to-moderate income households in their communities with the savings associated with green energy production.  

Read more about it [here](https://njcleanenergy.com/files/file/CI%20Program%20Literature/FY20%20Brochures/Community%20Solar%2011_9_19%20approved.pdf)  

Community solar is especially beneficial to renters, who are victim to a split incentive problem with their landlords. Since tenants pay their own electricity bills, landlords are not incentivized to make large investments like rooftop solar to lower their energy costs. Coupled with logistical issues like installing solar panels in dense urban areas or apartment buildings with HVAC equipment on their roofs, this leaves typically lower-income renters without access to cheap renewable energy. Community solar would allow these households to buy cheap energy from projects within their utility service area, all accounted for virtually through their usual electricity bills. Project developers can sell excess energy production through the Community Solar Program and enjoy additional incentives from the State.   

This analysis will focus on Carteret, NJ, a small commercial town in between New Brunswick and Newark under the PSE&G utility service area. Given its location near key ports like Elizabeth, Carteret has become a hub for the warehousing and logistics industries. In the last 10-15 years expansive warehouses have been built throughout Carteret, many of which already have solar on their roofs. There is significant potential to utilize the remaining rooftop area for community solar to serve low-income households anywhere within the PSE&G utility service area.  

### Community Solar for Who?
First, let’s examine the demand side of the equation. It is important to determine where there is the greatest need for a Community Solar Program, and where project developers may focus their efforts when signing up customers. Neighborhoods with high proportions of rented housing units and areas of low income are good candidates for community solar. Energy costs make up a large part of a low-income household’s budget. Relieving this financial burden through community solar has a positive economic effect on low-income communities while advancing green energy expansion. In the figures below, % Housing Units that are Renter Occupied and Median Household Income are mapped for the PSE&G Utility Service Area by Census Tract. Carteret is highlighted in green outline.    

![Percent Renter Map](/Carteret-Community-Solar/Renter Map Final.png)
![Percent Renter Map](/Carteret-Community-Solar/Income Map Final.png)

As expected dense urban areas like Jersey City/Hoboken, Bayonne, Paterson, the Oranges, Elizabeth, Perth Amboy, Trenton, and Camden have high rates of renters and low median incomes. These areas are also poorly suited for rooftop solar due to density and building types. If a project developer wanted to build a community solar project in Carteret, they may look to these areas to find potential customers.  

### Community Solar Where?
Finding customers is only the first part of the problem. In order to build a community solar project a developer will also need a suitable site. Carteret is a good candidate for community solar given the expansive warehouses that make up the commercial parts of town. 

![Warehouses](/Carteret-Community-Solar/Slide2.PNG)

There are also plenty of large existing solar installations which can be reallocated to provide electricity to the community solar program. 

![Amazon EWR9](/Carteret-Community-Solar/Slide3.png)  
![Existing Installations Text](/Carteret-Community-Solar/Slide4.png)
![Existing Installations](/Carteret-Community-Solar/Slide5.PNG)

However, the major obstacle for solar developers in Carteret is hosting capacity. PSE&G power lines have a set amount of capacity that they can accommodate. Given the large quantity of existing projects in Carteret, there is very little capacity for additional projects in Carteret. Most of the town has <10 kW of capacity remaining while some of the eastern part of town have between 10-1,000 kW.

![Hosting Capacity Map](/Carteret-Community-Solar/Slide1.PNG)

Until the hosting capacity problem is solved (i.e. lines are upgraded and the grid is modernized), new installations have to be limited to areas with yellow dots on them. The webmap below seeks to highlight potential sites for community solar including:
1.	Existing sites which can allocate up to 5MW (5,000 kW) towards the community solar program (orange pop-ups)
2.	Non-residential parcels with significant rooftop space (>3,000 sq. ft.) that are in an area with available hosting capacity (highlighted in green)  

Explore the map below to see possible sites to make Carteret a strong contributor to the NJ Community Solar Program: 

<iframe src="Carteret.html" height="1000" width="1000"></iframe>

You can explore the map [as its own webpage here](Carteret.html)  

### Data Sources
The following datasets were used in this analysis:

1. NJ Clean Energy Solar Installations Dataset
      - Provides data on current commercial solar installations in New Jersey.
      - This dataset has a very unclean address variables ("ADDRESS","CITY"), which need to cleaned before geocoding. OpenRefine was used to correct all misspellings of Carteret using the cluster function. Once cleaned, this dataset is geocoded using ESRI geocoder. Some addresses which are poorly geocoded ("STREET ADDRESS" as "MATCH_TYPE") are manually placed on the correct parcel using ArcGIS Pro.
      - Available [here](https://njcleanenergy.com/renewable-energy/project-activity-reports/solar-activity-report-archive)
            - Provided by NJBPU.
            - Used July 2022 dataset (updated monthly).
            - Downloaded as an Excel, then cleaned and geocoded into a .geojson file.
2. NHGIS Tracts and County Subdivisions + Census 2019 ACS Data
      - Census data is retrieved at tract level and joined with NHGIS geospatial data (on GEOID) to be mapped.
      - Subdivisions are used to highlight Carteret (and other municipalities), and clip larger datasets to area of study.
      - Available [here](https://data2.nhgis.org/main)
            - Provided by NHGIS and Census Bureau.
            - Maps of Census tracts and subdivisions are recent and regularly maintained (as far as I can tell).
            - Downloaded as shapefiles, but converted to .geojson after data management step.
3. Parcels and MOD-IV Composite of NJ
      - Provides information on tax parcels, allowing categorization and visualization of property types.
      - Spatially joined with Microsoft Footprint Data to classify footprints by property type and to calculate estimate of rooftop area per non-residential parcel.
      - Available [here](https://njogis-newjersey.opendata.arcgis.com/documents/406cf6860390467d9f328ed19daa359d)
            - Provided by NJ Office of GIS.
            - Last updated December 16, 2022, but this analysis uses the November 22, 2022 version.
            - Downloaded as a .geojson file.
4. Microsoft Building Footprint Dataset
      - Provides footprints of buildings in area of study. Used to calculate a rough estimate of rooftop area per non-residential parcel.
      - Spatially joined with MOD-IV Tax Parcel data to classify buildings by property type.
      - Available [here](https://github.com/microsoft/USBuildingFootprints)
            - Provided by Microsoft.
            - Imagery used to build this dataset is from 2019-2020.
            - Downloaded as .geojson file for all of NJ, then clipped to area of study (Carteret).
5. PSE&G Solar Power Suitability Map
      - Provides a rough idea of whether there is capacity on power lines to install grid-connected solar. If red then there is <100kw available, if yellow then there is 100-1000kw available, if green then there is >1000kw available.
      - This data isn't available for download, so using a georeferenced screenshot of the area of study, I manually drew polygons for the areas with different hosting capacity.
      - Available [here](https://nj.pseg.com/saveenergyandmoney/solarandrenewableenergy/solarpowersustanibility)
            - Provided by PSE&G.
            - Updated regularly, although unclear when the last update was.
            - Retrieved as screenshot, georeferenced, then applied over a polygon of Carteret city extent, which was manually split into areas of different hosting capacity.
6. Electric Utilities Territory Map of New Jersey
      - Provides a polygon of each electric utility's service area. This analysis uses PSE&G's service area (the utility that Carteret falls in) extent when analyzing the demand for community solar service.
      - Available [here](https://njogis-newjersey.opendata.arcgis.com/datasets/d23845cc51454ee59affd226cff3fcd5_10/about)
            - Provided by NJDEP Bureau of GIS.
            - Created on March 29, 2012. These service areas do not change very often and it is likely that the current is still the same.
            - Downaloaded as a .geojson file, limited to PSE&G, and used to clip Census data for static maps.

