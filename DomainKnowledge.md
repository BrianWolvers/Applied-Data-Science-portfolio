# Domain Knowledge van het Container project

## Algemene kennis


## Datasets
Vanuit de opdrachtgevende organisatie Cofano zijn er meerdere CSV's ontvangen met data over de bestaande kade. Deze CSV's bevatten informatie over de kade, het geeft aan waar een containers op de kade is geplaatst, alle verplaatsingen van containers die uitgevoerd zijn, extra informatie over een container die verplaatst is en een CSV die informatie geeft over containers die getransporteerd zijn.  

### [Stacks](https://github.com/BrianWolvers/ADS/blob/main/ContainerDataset/stacks.csv) + [Marker](https://github.com/BrianWolvers/ADS/blob/main/ContainerDataset/marker.csv) 

Voor informatie over de kade zijn er twee CSV-bestanden ontvangen. Het bestand genaamd [Stacks](https://github.com/BrianWolvers/ADS/blob/main/ContainerDataset/stacks.csv) bevat informatie over de verschillende plekken op de kade waar een container geplaatst kan worden. Welke vakken er dus mogelijke plekken zijn om een container te plaatsen. Deze dataset bevat bijvoorbeeld bijvoorbeeld de maximale hoogte en maximale lengte van een container voor dat vak samen met de relatieve X en Y coördinaten op de kade. Naast naast het Stack-bestand is er ook de CSV genaamd [Marker](https://github.com/BrianWolvers/ADS/blob/main/ContainerDataset/marker.csv). De CSV [Marker](https://github.com/BrianWolvers/ADS/blob/main/ContainerDataset/marker.csv) gaat verder in op zo'n plek in een stack. Een marker geeft aan welke containers op een stack locatie staan. Op basis van deze twee CSV's kan de indeling van de kade achterhaald worden.

### [Stacks entry](https://github.com/BrianWolvers/ADS/blob/main/ContainerDataset/stackentry.csv) 

In de CSV [Stacks entry](https://github.com/BrianWolvers/ADS/blob/main/ContainerDataset/stackentry.csv) is dat opgeslagen wat een plaatsing van een container in een stack aangeeft. Hierin is data opgeslagen zoals het ID van een stack en het ID van de handeling. Uit deze dataset kan er gehaald worden welke containers er op het moment dat de dataset gedeeld was op de kade staan. Ook valt er uit deze dataset te halen welke voertuigen de container hebben verplaatst of hoevaak. Zo kan je dus achter of de plek waar de container stond ideaal was. Dit is mogelijk door te kijken naar de containers die nog op de kade staan en hoevaak deze verplaatst is. 

### [Handling](https://github.com/BrianWolvers/ADS/blob/main/ContainerDataset/handling.csv)

In de CSV [Handling](https://github.com/BrianWolvers/ADS/blob/main/ContainerDataset/handling.csv) zijn verplaatsingen van containers geregistreerd. Bij een verplaatsing van een container is er meer informatie bekend als alleen de vertreklocatie en de vertreklocatie. Zo is er de begin- en eindtijd van een verplaatsing opgeslagen samen met welke machine de verplaatsing heeft uitgevoerd en een hoog die prioriteit van de verplaatsing was. Zo kan er dus gekeken worden hoeveel containers er op een dag in en uit gaan en hoeveel verplaatsingen er inter gedaan worden.
