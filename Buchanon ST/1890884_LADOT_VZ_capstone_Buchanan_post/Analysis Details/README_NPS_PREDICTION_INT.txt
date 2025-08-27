This folder contains Metrics about the Estimated StreetLight Volume at the Zones of the named Analysis.

TERMS
=====
Pass-Through: A zone setting indicating how to analyze how trips interact with the zone. Zones marked as pass-through use trips that pass through the zone but do not start or stop in it. Zones not marked as pass-through use trips that start or stop in the zone.

Zone Direction: A pass-through zone can have applied direction which limits the trips analyzed for the zone: only trips that pass through the zone within -20/+20 degrees of the direction will be analyzed for the zone. Values are provided in degrees from 0 to 359, where 0 is due north, 90 is east, 180 is due south, etc.


OUTPUT UNIT TERMS
=================
StreetLight Volume: The estimated trip counts as calculated by StreetLight Data's machine learning algorithm.

95 Prediction Range: The 2.5th percentile and the 97.5th percentile of the error distribution.

*More information about the output unit methodology can be found in the StreetLight Help Center (https://help.streetlightdata.com).


*prediction_intervals.csv
==================
This file contains the Metrics for the Estimated StreetLight Volume for each Zone in the Analysis.  The columns are:
- Data Periods: Ranges of dates analyzed.
- Mode of Travel: Mode of travel analyzed.
- Intersection Type: Type of trips analyzed--dependent on whether the zone Is Pass-Through. If Zone Is Pass-Through is "Yes", then Intersection Type = "Trip Pass-Through". If Zone Is Pass-Through is "No", then there is a row each for Intersection Type = "Trip Start" and "Trip End".
- Zone ID: Numeric ID for the origin zone as provided by the user.
- Zone Name: Name of the zone.
- Zone is Pass-Through: For this Analysis, all Zones are required to have a value of "Yes".
- Zone Direction (degrees): This refers to the direction in which trips pass through the zone as described above under Terms.
- Zone is Bi-Direction: Indicates if the zones are bi-directional. Is either marked as "Yes" or "No".
- Year Month: Indicates the year-month of the prediction interval.
- Day Type: Average Day (average of traffic Monday through Sunday).
- Day Part: All Day, i.e. all 24 hours.
- Average Daily Zone Traffic (StL Volume): The volume of trips starting in, passing through, or ending in the zone based on the zone Mode of Travel, Intersection Type, and Output Type (as described above in the Output Unit Terms).
- Lower 95 Percent Prediction Range: Lower bound of the range for a true vehicle volume value for each zone with a 95% confidence.
- Upper 95 Percent Prediction Range: Upper bound of the range for a true vehicle volume value for each zone with a 95% confidence.

*95 Percent Prediction Range are formed using the 2.5th percentile and the 97.5th percentile of the error distribution.
**For more information about prediction intervals, please refer to the StreetLight Help Center (https://help.streetlightdata.com)


NOTES
=====
Zones with No Values
=================
If the output unit values for a zone for a specific time period (e.g. Average Weekday, Early AM) are below StreetLight's significance threshold, no results will be shown in the *prediction_intervals.csv file.

The Files in this Folder are the Confidential Information of StreetLight Data, Inc. Your access is provided via an End User License Agreement (the "License Agreement") between StreetLight Data, Inc. and Your Organization. You are responsible for knowing and abiding by the terms and restrictions set forth in the License Agreement.

Copyright © 2011 - 2025, StreetLight Data, Inc. All rights reserved.

