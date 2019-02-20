# Points to notice about this dataset
This dataset consists of csv files (of a total of 921109 rows) are converted from ROS bags collected by an autonomous vehicle.
The csv files are named as `<time_start_recording>.csv`.
Efforts have been made so that the data follow standards and formats of those of NGSIM dataset as much as possible.
However several inconsistencies between standards still exist. These inconsistencies are caused by different coordinate
definition, different measuring equipments and different regions in which we operate our vehicles. The rest of this article
explains any inconsistencies that currently exist.

## Definition of coordinates:
Two sets of coordinates are used in this dataset:
1. Body coordinate of ego car (x-axis points to the front of the car, y-axis points to the left of the car, the center is at center of rear axle of the car)
2. GPS coordinate  (x-axis points towards east, y-axis points towards north, measured by GPS on ego car)

## Attributes that are not applicable in this dataset include:
- `O_Zone`: unavailable at the moment due to lack of annotation of ramps and intersections
- `D_Zone`: unavailable at the moment due to lack of annotation of ramps and intersections
- `Int_ID`: unavailable at the moment due to lack of annotation of ramps and intersections

## Attributes that where discrepancies between standards of this dataset and those of NGSIM exist include:
- `Total Frames`: these are total frames over each csv file instead of the whole dataset.
- `Local_X`: x-position of each vehicle in ego car's body coordinate.
- `Local_Y`: y-position of each vehicle in ego car's body coordinate.
- `Global_X`: x-position of each vehicle in GPS coordinate.
- `Global_Y`: y-position of each vehicle in GPS coordinate.
- `v_Class`: all vehicles apart from ego car (Vehicle_ID=0) in this dataset are in fact unclassified obstacles and are assumed to be type auto (v_Class=2).
- `Lane_ID`: lanes in this dataset are in body coordinate of ego car and maximum of 3 lanes are detected (Lane_ID 1: lane on which ego car drives, Lane_ID 0: left, Lane_ID 2: right).
- `Section_ID`: in this dataset, sections usually cover a larger area than NGSIM while featuring fewer intersections and ramps.
- `Direction`: in this dataset, Direction is determined from Global_X and Global_Y by dividing the GPS coordinate into four quadrants with its diagnols (i.e. East for quadrant: [-0.25pi, 2.5pi)).
- `Movement`: in this dataset, Movement of an vehicle is inferred from either its estimated time for finishing lane crossing or the angle between its velocity and that of ego car.
- `Time_Headway`: to avoid numerical issues while generating the dataset, vehicles with 0 speed are assigned 9999.99 as their Time_Headway.
- `Location`: this dataset features a single location, which cover a wider area than NGSIM but is less geographically diversified.

## N/A representations
NGSIM features missing cells as well as cells with values of NA. This dataset fills all empty cells with NA.