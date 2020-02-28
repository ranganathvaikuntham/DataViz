# DataViz
Visualization of Australian Fires

https://ranganathvaikuntham.github.io/DataViz/

# Context
 
Forest fires of unprecedented scale and violence have devastated entire regions of Australia since September 2019. They have caused considerable damage, not only to homes but also to flora and fauna. Over 1 billion animals have been killed and million hectares of forest land has been burned. Damage to human life and property is estimated around 485M $.
With our visualization, we want to answer some questions about the evolution of the fire dispersion, the regions that have experienced intense fires, in which periods of summer and what were the maximum values, etc.
Observing the trends for this year of 2019 could help relevant authorities to be better prepared for the future, if bushfires of this scale and intensity were ever to repeat.

# Collecte et Source de données
	Les nouvelles actuelles sur les feux en Australie se répandent rapidement, mais on ne peut pas en dire autant des données. Les satellites de la NASA fournissent un premier ensemble de données sur les incendies en Australie. 

Sources: https://www.kaggle.com/carlosparadis/fires-from-space-australia-and-new-zeland?fbclid=IwAR0btRqk-fTw1-Ae5Xj7wTABf99LHqtQbmRANsFshZ2oYyE2RE_WKBnbbDk

Possible source pour donnés additionnelle : https://modis.gsfc.nasa.gov/
https://www.google.com/search?q=modis+australia+wildfire&oq=modis+australia+wildfire&aqs=chrome..69i57.8016j0j4&sourceid=chrome&ie=UTF-8


# Description du jeu de données
Le jeu de données est sous forme d’une table dont les colonnes sont décritent ci-dessous.

Latitude -Centre d'un pixel de feu de 1 km 
Longitude : Centre d'un pixel de feu de 1 km
Brightness : Température en Kelvin mesuré par l'outil de Channel 21 sur le satellite.
Scan & Track: reflètent la taille réelle des pixels.
Acq_date : date d'acquisition
Acq_time : Temps d'acquisition (en UTC).
Satellite -  Satellite: A = Aqua et T = Terra.
Instrument - Valeur constante pour MODIS.
Confidence (0-100%) : Cette valeur est basée sur un ensemble de quantités d'algorithmes intermédiaires utilisées dans le processus de détection. Elle est destinée à aider les utilisateurs à évaluer la qualité de chaque pixel de hotspot/feu. Les estimations de confiance varient entre 0 et 100 % et se voient attribuer l'une des trois classes d'incendie 
-incendie de faible confiance.
-incendie de confiance nominale.
-incendie de confiance élevée.
Version -  near real time(NRT) ou standard processing.
Bright_t31 - Température en Kelvin mesuré par l”outil de Channel 31 sur le satellite.
Frp-   ‘fire radiative power’ en Megawatts: Représente la puissance radiative du feu intégrée aux pixels 
Daynight - D- Daytime , N- Nighttime

Pour notre analyse on propose d’utiliser seulement quelques colonnes des données qui nous sert. Ce sont les suivantes:

Latitude
Longitude
Brightness ( on choisit le sortie du Channel 21 sur le Channel 31)
Acq_date et Acq_time 
 Frp
Daynight

# Data Cleaning and preparation
Etant donné que le lien de source de nos donnés se compose de quatre base de donnés, on a décidé d’utiliser le premier s’appelle ‘fire_archive_M6_96619.csv’.

Excel est l’outil qu’on emploie pour nettoyer nos donnés. 
Les étapes à suivre pour nettoyer des données avec excel sont le suites:

Comprendre le sense de toutes les colonnes et enlever ce qui nous intéresse pas.
Dans notre cas on enlève les colonnes type ( pas utile pour nous) ,bright_t31 (on utilise déjà le paramètre du ‘brightness’) et version (seulement une valeur pour ce donnes - redondant) .

Exercer la fonction du filtre sur chacun de colonnes pour voir si les valeurs vides existe pour ces colonnes. Si oui, enlève ces lignes.
 Il n’existe pas les cellules vides dans notre donnés, donc pas besoin de modification.

Vérifions s’il existe des données anormaux ou faux. 
Anormaux ou faux donnés sont identifié normalement avec les visualizations exploratives et une compréhension des données. 
Avoir fait quelques visualisations exploratifs on conclure qu'il n’y a pas des données anormaux. En plus le source de NASA est très fiable et réputé. 

Les données sont prêt à télécharger pour le visualization.



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

