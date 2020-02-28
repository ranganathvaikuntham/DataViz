# DataViz
Visualization of Australian Fires

https://ranganathvaikuntham.github.io/DataViz/

# Context
 
Forest fires of unprecedented scale and violence have devastated entire regions of Australia since September 2019. They have caused considerable damage, not only to homes but also to flora and fauna. Over 1 billion animals have been killed and million hectares of forest land has been burned. Damage to human life and property is estimated around 485M $.
With our visualization, we want to answer some questions about the evolution of the fire dispersion, the regions that have experienced intense fires, in which periods of summer and what were the maximum values, etc.
Observing the trends for this year of 2019 could help relevant authorities to be better prepared for the future, if bushfires of this scale and intensity were ever to repeat.

# Visualization
![Map Visualization](/images/map.PNG)

Our goal is to show the temperatures and fire radiative power(frp) of the bushfires during August 2019-December 2019. Initially, when the page loads, we chose to project only the fires for the first date (08/01/2019) to speed up the loading of the map. An option to show all the fires during this period of 5 months is available as a checkbox below the map. The legend indicates the values of the temperatures according to their colors.

![Map Visualization](/images/grid.PNG)

The ‘Github style’ heatmap on the right gives a global view of the evolution of fires during this period. The color intensity reflects the maximum temperature value observed on the particular day. Each day of every month is covered here. Upon hovering the mouse over a rectangle corresponding to a particular day you can see the date, maximum temperature and the maximum frp value recorded this day.

By clicking on the rectangle, only the fires initiated on that particular day are projected on the map with a brief animation that takes place to emphasize the change. On the map, by hovering over the fire points a tooltip is displayed which shows the information related to this specific location including the temperature and the frp value .



