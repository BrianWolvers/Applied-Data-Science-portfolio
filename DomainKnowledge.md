# Domain Knowledge van het Container project

## Algemene kennis

De opdrachtgevende organisatie van het uitgevoerde project is Cofano Software Solutions. De organisatie is benieuwd naar welke mogelijkheden er zijn voor het indelen van containers doormiddel van AI mogelijkheden. Voor het uitgevoerde project is er aangegeven dat container vanaf binenvaartschepen op de kade geladen worden en vanaf de kade op zeeschepen. Voor simplificatie is er maar één type machine die gebruikte kan worden om de containers te verplaatsen. Deze machine heet een reachstacker. Een reachstacker zou je kunnen zien als een grote vorkheftruck speciaal voor het optillen van containers. Deze machine kan maximaal vier containers op elkaar zetten. Vanuit Cofano is er een plattegrond ontvangen van een klant van Cofano. Op deze plattegrond zijn verschillende Markers te zien en binnen deze markers zijn de verschillende Stacks te herkennnen. 

## Datasets
Vanuit Cofano zijn er meerdere CSV's ontvangen met data over de bestaande kade. Deze CSV's bevatten informatie over de kade, het geeft aan waar een containers op de kade is geplaatst, alle verplaatsingen van containers die uitgevoerd zijn, extra informatie over een container die verplaatst is en een CSV die informatie geeft over containers die getransporteerd zijn.  

### [Stacks](https://github.com/BrianWolvers/ADS/blob/main/ContainerDataset/stacks.csv) + [Marker](https://github.com/BrianWolvers/ADS/blob/main/ContainerDataset/marker.csv) 

Voor informatie over de kade zijn er twee CSV-bestanden ontvangen. Het bestand genaamd [Stacks](https://github.com/BrianWolvers/ADS/blob/main/ContainerDataset/stacks.csv) bevat informatie over de verschillende plekken op de kade waar een container geplaatst kan worden. Welke vakken er dus mogelijke plekken zijn om een container te plaatsen. Deze dataset bevat bijvoorbeeld bijvoorbeeld de maximale hoogte en maximale lengte van een container voor dat vak samen met de relatieve X en Y coördinaten op de kade. Naast naast het Stack-bestand is er ook de CSV genaamd [Marker](https://github.com/BrianWolvers/ADS/blob/main/ContainerDataset/marker.csv). De CSV [Marker](https://github.com/BrianWolvers/ADS/blob/main/ContainerDataset/marker.csv) gaat verder in op zo'n plek in een stack. Een marker geeft aan welke containers op een stack locatie staan. Op basis van deze twee CSV's kan de indeling van de kade achterhaald worden.

### [Stacks entry](https://github.com/BrianWolvers/ADS/blob/main/ContainerDataset/stackentry.csv) 

In de CSV [Stacks entry](https://github.com/BrianWolvers/ADS/blob/main/ContainerDataset/stackentry.csv) is dat opgeslagen wat een plaatsing van een container in een stack aangeeft. Hierin is data opgeslagen zoals het ID van een stack en het ID van de handeling. Uit deze dataset kan er gehaald worden welke containers er op het moment dat de dataset gedeeld was op de kade staan. Ook valt er uit deze dataset te halen welke voertuigen de container hebben verplaatst of hoevaak. Zo kan je dus achter of de plek waar de container stond ideaal was. Dit is mogelijk door te kijken naar de containers die nog op de kade staan en hoevaak deze verplaatst is. 

### [Handling](https://github.com/BrianWolvers/ADS/blob/main/ContainerDataset/handling.csv)

In de CSV [Handling](https://github.com/BrianWolvers/ADS/blob/main/ContainerDataset/handling.csv) zijn verplaatsingen van containers geregistreerd. Bij een verplaatsing van een container is er meer informatie bekend als alleen de vertreklocatie en de vertreklocatie. Zo is er de begin- en eindtijd van een verplaatsing opgeslagen samen met welke machine de verplaatsing heeft uitgevoerd en een hoog die prioriteit van de verplaatsing was. Zo kan er dus gekeken worden hoeveel containers er op een dag in en uit gaan en hoeveel verplaatsingen er inter gedaan worden.

### [Container location information](https://github.com/BrianWolvers/ADS/blob/main/ContainerDataset/containerlocationinformation.csv)

Deze CSV geeft extra informatie over de locatie van een container. Er zijn 3 typen locaties waar de dataset informatie geeft, dit zijn namelijk als een container op de kade staat, wanneer de container op een vrachtwagen staat en wanneer hij op een schip staat. Als een container op de kade staat, dan is hierover ook een Marker- en stackID van bekend. Dit kan gebruikt worden om containers op de kade te plaatsen in een simulatie omgeving.

### [Action](https://github.com/BrianWolvers/ADS/blob/main/ContainerDataset/actions.csv)

Wanneer er iets met een container moet gebeuren dan wordt dit in deze CSV opgeslagen. Dit kan zijn dat een container binnen de haven naar een andere kade moet of een andere actie. Als een container de haven verlaten heeft dan wordt hier ook informatie over opgeslagen. Een voorbeeld hiervan is dat het momente dat de container de haven in is gekomen en ook het vertrekmoment ervan is opgeslagen. Uit deze dataset is te halen welke acties er allemaal zijn uitgevoerd op een specifieke container.


## Bibliografie

Team, P. T. (2021, 5 mei). How can ports use Artificial Intelligence? Port Technology International. https://www.porttechnology.org/news/how-can-ports-use-artificial-intelligence/

O’Dwyer, R. (2022, 2 maart). An artificial intelligence use case for smart port resource allocation. Smart Maritime Network. https://smartmaritimenetwork.com/2022/03/03/an-artificial-intelligence-use-case-for-smart-port-resource-allocation/

Yeo, D. (2022, 15 september). How AI Will Boost Sustainability at the Port of Tanjung Pelepas. MarineLink. https://www.marinelink.com/news/ai-boost-sustainability-port-tanjung-499487

