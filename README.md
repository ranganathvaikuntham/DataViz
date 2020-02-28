# DataViz
Visualization of Australian Fires

https://ranganathvaikuntham.github.io/DataViz/

# Context
 
Forest fires of unprecedented scale and violence have devastated entire regions of Australia since September 2019. They have caused considerable damage, not only to homes but also to flora and fauna. Over 1 billion animals have been killed and million hectares of forest land has been burned. Damage to human life and property is estimated around 485M $.
With our visualization, we want to answer some questions about the evolution of the fire dispersion, the regions that have experienced intense fires, in which periods of summer and what were the maximum values, etc.
Observing the trends for this year of 2019 could help relevant authorities to be better prepared for the future, if bushfires of this scale and intensity were ever to repeat.

# Collection and sourcing of the data
Current news about fires in Australia is spreading rapidly, but the same cannot be said of the data. NASA satellites are providing the first set of data on fires in Australia. 

Source: https://www.kaggle.com/carlosparadis/fires-from-space-australia-and-new-zeland?fbclid=IwAR0btRqk-fTw1-Ae5Xj7wTABf99LHqtQbmRANsFshZ2oYyE2RE_WKBnbbDk

Possible source for additional data : https://modis.gsfc.nasa.gov/
https://www.google.com/search?q=modis+australia+wildfire&oq=modis+australia+wildfire&aqs=chrome..69i57.8016j0j4&sourceid=chrome&ie=UTF-8


# Description of the data
The dataset is in the form of a table whose columns are described below.

Latitude - Center of a 1 km fire pixel 
Longitude: Centre of a 1 km fire pixel
Brightness: Temperature in Kelvin measured by the Channel 21 tool on the satellite.
Scan & Track: Reflects the actual pixel size.
Acq_date: date of acquisition
Acq_time: Acquisition time (in UTC).
Satellite - Satellite: A = Aqua and T = Terra.
Instrument - Constant value for MODIS.
Confidence (0-100%): This value is based on a set of quantities of intermediate algorithms used in the detection process. It is intended to help users evaluate the quality of each hotspot/fire pixel. Confidence estimates range from 0-100% and are assigned one of three fire classes 
-low-confidence fire.
-nominal confidence fire.
-high confidence fire.
Version - near real time(NRT) or standard processing.
Bright_t31 - Temperature in Kelvin measured by the Channel 31 tool on the satellite.
Frp- 'fire radiative power' in Megawatts: Represents the radiative power of the fire integrated into the pixels. 
Daynight - D- Daytime , N- Nighttime

For our analysis we propose to use only a few columns of the data we need. These are as follows:

Latitude
Longitude
Brightness ( we choose the output of Channel 21 on Channel 31)
Acq_date and Acq_time 
 Frp
Daynight

# Data Cleaning and preparation
Since the source link of our data consists of four databases, we decided to use the first one called 'fire_archive_M6_96619.csv'.

Excel is the tool we use to clean up our data. 
The steps to follow to clean up data with excel are the following:

Understand the meaning of all the columns and remove what doesn't interest us.
In our case we remove the columns type (not useful for us), bright_t31 (we already use the brightness parameter) and version (only one value for this data - redundant).

Exercise the function of the filter on each column to see if empty values exist for these columns. If so, remove these lines.
 Empty cells do not exist in our data, so there is no need for modification.

Let's check if there is abnormal or false data. 
Abnormal or false data are identified normally with exploratory visualizations and an understanding of the data. 
Having done some exploratory visualizations we conclude that there is no abnormal data. In addition the NASA source is very reliable and reputable. 

The data is ready to download for visualization.

# Visualization
![Map Visualization](/images/map.PNG)

Our goal is to show the temperatures and fire radiative power(frp) of the bushfires during August 2019-December 2019. Initially, when the page loads, we chose to project only the fires for the first date (08/01/2019) to speed up the loading of the map. An option to show all the fires during this period of 5 months is available as a checkbox below the map. The legend indicates the values of the temperatures according to their colors.

![Map Visualization](/images/grid.PNG)

The ‘Github style’ heatmap on the right gives a global view of the evolution of fires during this period. The color intensity reflects the maximum temperature value observed on the particular day. Each day of every month is covered here. Upon hovering the mouse over a rectangle corresponding to a particular day you can see the date, maximum temperature and the maximum frp value recorded this day.

By clicking on the rectangle, only the fires initiated on that particular day are projected on the map with a brief animation that takes place to emphasize the change. On the map, by hovering over the fire points a tooltip is displayed which shows the information related to this specific location including the temperature and the frp value .

# Authors 
Redwane AIT-OUAMMI && 
Ranganath VAIKUNTHAM

# Credits

This work is done as part of an academic deliverable for the course [Interactive Data Visualization](https://github.com/LyonDataViz/MOS5.5-Dataviz) supervised by Mr. Romain Vuillemot - Ecole Centrale Lyon

