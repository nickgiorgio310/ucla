This folder contains metrics for the Network Performance trips passing through the road segment zones of the named analysis.

The trips that are analyzed for each zone are determined by the pass-through designation for the zone.

TERMS
=====
Gate Direction: A start gate or end gate may optionally have a direction which limits the trips analyzed for the gate-- only trips that pass through the gate within -20/+20 degrees of the direction will be analyzed for the gate. Values are provided in degrees from 0 to 359, where 0 is due north, 90 is east, 180 is due south, etc. A value of "Null" refers to no direction filter and therefore all trips that pass through the gate will be used. However, unless the zone is bi-directional, the analysis will use only trips that pass through the start gate before they pass through the end gate. Gate directions are applied both ways for bi-directional zones.


OUTPUT UNIT TERMS
=================
StreetLight Volume: The estimated trip counts as calculated by StreetLight Data's machine learning algorithm.

StreetLight Sample Trip Counts: The total StreetLight sample trip counts for the zone (or set of zones) for all days in the entire data period.

*Note that, while most output units are represented as an average day per its day type definition, Trip Counts are not converted to an average day but rather represent the total Trip Counts. For example, a Trip Count value of 100 for an O-D pair, on an average weekday in March 2017, represents the sum of all trips used from the StreetLight data set for all the weekdays in March 2017.

*More information about the output unit methodology can be found in the StreetLight Help Center (https://help.streetlightdata.com).


FILES
=====
Analysis.txt
===========
This file lists information about the analysis as a whole, including the full analysis name, organization and user that created the analysis, and the analysis options configuration

*_network_performance_spot_metrics_*.csv
=======================================
This files contains the Network Performance metrics.

The fields are:
- Data Periods: Ranges of dates analyzed.
- Mode of Travel: Mode of travel analyzed.
- Zone ID: Numeric ID for the zone as provided by the user.
- Zone Name: Name for the zone.
- Zone Is Pass-Through: Indicates if the zone is pass-through or not as described above in the Terms.
- Zone Direction (degrees): This refers to the direction in which trips pass through the zone as described above in the Terms.
- Zone is Bi-Direction: Indicates if the zones are bi-directional. Values are "Yes" or "No".
- Day Type: All Days (traffic from Monday through Sunday), and other day type traffic segmentation as defined by user.
- Day Part: Segments of the day defined by the user in intervals of hours to analyze traffic (All Day is always included as entire 24 hours). The day parts reflect the local time at the zone.
- Spot Traffic: The volume of trips passing through the gate based on the Output Type (as described above in the Output Unit Terms). Bi-directional zones also include trips in the opposite direction.
- Avg Spot Speed: The average speed, delivered in the chosen unit of measurement (miles per hour or kilometers per hour).
- Free Flow Speed:  Free Flow Segment Speed is equal to the maximum Average Segment Speed that is observed in any one hour of the day in the data period.
- Free Flow Factor: a measure of congestion, is the "Average Trip Speed" divided by the "Free Flow Trip Speed". The Free Flow Trip Speed is the the Maximum Average Trip Speed in any one of the 24 hours of the day, averaged over all the days in the data period. The Free Flow Factor is a percentage value, between 0 and 1, to 3 digits of precision.
  Congestion: 1 minus the Free Flow Factor for a given segment.
- Percentile Speed (mph/kph): The speed at or below which x percent of all vehicles are observed to travel.
- Line Zone Length (Miles/Kilometers): The length of the zone line segment in miles/kilometers dependent on units of measure for analysis.

sample_size.csv
===============
This file contains information about the size of the data sample that was analyzed for this analysis and its data period.

The fields are:
- Data Periods: Ranges of dates analyzed.
- Mode of Travel: Type of mode analyzed.
- Approximate Device Count: Calculated as the number of unique devices in the analysis, rounded to nearest 10 (if below 100), and to nearest 100 (if above 100). N/A for analysis run with Navigaton-GPS data source.
- Approximate Trip Count Per Zone: An estimated value (calculated during processing) of the number of trips per zone in the StreetLight Data database that were analyzed for this analysis and its Data Period.

zones.csv
=========
This file contains information about the zones used in this analysis.

The fields are:
- Data Periods: Ranges of dates analyzed.
- Zone Type: Indicates if the zone for this is an origin or destination zone.
- Zone ID: Numeric ID for the zone as provided by the user.
- Zone Name: Name for the zone.
- Zone is Pass-Through: Indicates if the zone is marked as pass-through or not as described above under Terms. Is either makred as “Yes” or “No."
- Zone Direction (degrees): This refers to the direction in which trips pass through the zone as described above under Terms.
- Zone is Bi-Direction: Indicates if the zones are bi-directional. Is either marked as "Yes" or "No".
- Fingerprint1: A 64-bit signed integer assigned by StreetLight based on key spatial characteristics of the zone. Combination of Fingerprint1 and Fingerprint2 make up the fingerprint of the zone and indicate if two zones are the same or unique.
- Fingerprint2: A 64-bit signed integer assigned by StreetLight based on key spatial characteristics of the zone. Combination of Fingerprint1 and Fingerprint2 make up the fingerprint of the zone and indicate if two zones are the same or unique.

*.(dbf|prj|shp|shx|cpg)
=======================
These files comprise the shapefiles for the analysis's zone sets.

A shapefile consists of the following several files:
.shp file contains the feature geometries and can be viewed in a geographic information systems application such as QGIS.
.dbf file contains the attributes in dBase format and can be opened in Microsoft Excel.
.shx file contains the data index.
.prj file contains the projection information.
.cpg file contains the encoding applied to create the shapefile.

These shapefiles have the following attributes/columns:
- id: Numeric ID for the zone as provided by the user. This may be null as the field is optional.
- name: Name for the zone.*
- direction (degrees): This refers to the direction in which trips pass through the zone as described above under Terms.
- is_pass: Indicates if the zone is pass-through or not as described above under Terms. 1 = “Yes” and 0 = “No”.
- geom: Polygon of the zone.
- is_bidi: A value of 1 indicates traffic measured in two opposite directions for a single set of Metric values. 0 value indicates traffic is in single direction specified by users.

* If the zone_name format is [OSM Name] / [OSM ID] / #### (for example: 'Market Street / 9570488 / 1'), the zone file is an OSM Derivative Database, and subject to OSM terms. Refer to https://www.streetlightdata.com/open-source/ for more information.


NOTES
=====
Day Part Calculations
=====================
The Day Part calculations are done in relation to the zones used in the analysis. The Day Part is determined by when trips pass through the zone's start gate.

The Files in this Folder are the Confidential Information of StreetLight Data, Inc. Your access is provided via an End User License Agreement (the "License Agreement") between StreetLight Data, Inc. and Your Organization. You are responsible for knowing and abiding by the terms and restrictions set forth in the License Agreement.

Copyright © 2011 - 2025, StreetLight Data, Inc. All rights reserved.

