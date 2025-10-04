Some of the columns you want to use in your project will have coded values that represent longer more readable values. 
For instance the cancellation_reason column in 
the flights data set has the values: A, B, C, D These letters are not understandable by themselves. 
You need to replace these letters with the full reason to make your visualizations including this data more readable.

These letters correspond with the following reasons.

A - Airline/Carrier

B - Weather

C - National Air System

D - Security

You should review the Column Metadata tab on Kaggle for each data set to find details about the data like the one I have outlined above.

The following times are in the xx:yy - hour:minute format (e.g. 1536 means 3:36pm, 345 means 3:45am, 16 means 00:16am)

scheduled_departure

departure_time

scheduled_arrival

arrival_time

wheels_off

wheels_on

The following times are in minutes format 
(negatives mean actual_time is ahead of scheduled_time for the absolute value of that negative number)

arrival_delay

departure_delay

taxi_in

taxi_out

scheduled_time

elapsed_time

air_time

Distance in miles

Data Definition

WHEELS_OFF Time - The time point that the aircraft's wheels leave the ground.

WHEELS_ON Time - The time point that the aircraft's wheels touch on the ground.

TAXI_OUT Time - The time duration elapsed between departure from the origin airport gate and wheels off.

TAXI_IN Time - The time duration elapsed between wheels-on and gate arrival at the destination airport.

AIR_TIME - The time duration between wheels_off and wheels_on time.

Data Relationship

arrival_time = wheels_on + taxi_in

arrival_delay = arrival_time - scheduled_arrival

departure_time = wheels_off - taxi_out

departure_delay = departure_time - scheduled_departure

elapsed_time =air_time + taxi_in + taxi_out

air_time = wheels_on - wheels_off

Note:
In the flights file, there are around 480k flights with 
original_airport & destination_airport being a 5-digit number 
('14168') instead of three-character code ('LAX'). Not sure why it's the case.
. just be cautious when joining flights and airports data or analyzing based on airport info..