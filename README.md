# NOAA
API calls to NOAA web service

The National Oceanic and Atmospeheric Assocation (NOAA) collects all National Weather Service (NWS) warnings issued for the continental U.S. and loads them to the Severe Weather Data Inventory (SWDI) database.  The SWDI db can be accessed via a web service at <http://www.ncdc.noaa.gov/swdiws>. 

The db is updated nighlty and contains all warnings through yesterday.  Requests' date range cannot be larger than 31 days, so if we need more days then we'll need to loop. Responses can be returned in either JSON or XML. Unfortunately, there is limited  contained in the fields of the response, however, the Warning ID is included and a separate request can be made to recover the warning message by Warning ID. 

1. Make an API call to the web service. Get the response back in JSON. 
2. For each Warning ID, make another call to get the warning message and extract county, state, and peril information. 
3. Multiple Warning ID's could correspond to the same event, so group ID's together.  Warning ID' are considered similar if they occur within 12 hours of each other and are issued for contiguous counties.





