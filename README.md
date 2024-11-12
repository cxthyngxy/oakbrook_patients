# oakbrook_patients
A GIS map of the patients attending G. Office in Chicago
LINK TO MAP 

The link below can be used to download the Tableau workbook containing the map (though the map itself
is included in this folder as "OakbrookDistribution")

https://public.tableau.com/app/profile/yuseof.j/viz/OakbrookDistribution/Dashboard1

Please note that only having this link gives access to the Tableau workbook online.


NOTE

I make reference to the specific data files in the "Data/" folder as such: <<< Data/name-of-file >>>
This may be important in case the data becomes of interest later, or just for general understanding of 
the project.


PROBLEM STATEMENT

The goal of this project was to visualize the distribution of patients for a secific clinic in Chicago. 


METHOD

Visualizing the patient distribution was accomplished by plotting addresses on a census tract level. 
This is important because rather than plotting individual patient addresses (of which there were thousands), 
I instead grouped the addresses by neighborhood (census tract codes). The size of each individual tract's pin on the map 
was then determined by the amount of patients in that neighborhood. 


DATA

I was provided with a collection of excel sheets containing patient addresses from a series of months. I simply appended these sheets in python, leaving me with 8050 rows. After removing duplicate rows (determined by patient name and address = 5366), as well as rows with no address information (41), I was left with 2,643 unique patient addresses. 

For each address, I used geolocation services (APIs) in python to create the following excel sheet:

<<< Data/geolocated_addresses_final.xlsx >>>

In this sheet, each address has a latitude, longitude, and Census FIPS code. These are used to plot the 
data in Tableau. 

The sheet <<< Data/fips_counts.xlsx >>> is simply the addresses grouped by fips codes in order to accomplish the goal outlined in METHOD.

The sheet <<< Data/final_missing_addresses.xlsx >>> is a list of patient addresses that could not be geolocated (22).

The sheet <<< Data/pt_add_masked.xlsx >>> is a list of the raw patient addresses after removing duplicates and nulls. 




