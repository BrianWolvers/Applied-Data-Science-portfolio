# Research Projects

## Task definition

Binnen de havens van de klanten van Cofano worden momenteel de containers op de kade ingedeeld op basis van de ervaring van medewerkers en simpele beslisregels. Cofano zou hier graag wat in willen veranderen. Zij willen namelijk de markt instappen met een oplossing hiervoor. Vanwege deze reden is Cofano benieuwd welke mogelijkheden er zijn om de methode van containerindeling naar het volgende niveau te brengen doormiddel van AI. Vanuit Cofano was er een interresse in het gebruik van Reinforcement learning. Aan de hand van de hierboven beschreven tekst is er de mogelijkheid om de volgende probleemstelling op te stellen: De methode van containers indelen in de haven van de klanten van Cofano is geheel afhankelijk van de denkkracht van mensen. Op basis van de probleemstelling kan er ook een doelstelling opgesteld worden. De doelstelling luidt als volgd: Welke AI-mogelijkheden zijn er voor het indelen van containers in de haven bij de klanten van Cofano. Voor simplificatie is er tijdens deze opdracht maar één type machine die containers verplaatst. Deze machine heet de reachstacker. De reachstacker kan machinaal vier containers op elkaar zetten.

### Onderzoeksvraag 1
Op basis van de opdrachtomschrijving was er de volgende onderzoeksvraag opgesteld: Hoe kunnen de containers optimaal ingedeeld worden, zodat de containers die bestemd zijn voor hetzelfde zeeschip bij elkaar blijven? Het doel achter de onderzoeksvraag was dat wij wilde achterhalen hoe containers zo veel mogelijk in groepen ingedeeld kunnen worden, want als containers die voor hetzelfde schip bestemd zijn in dezelfde rij staan dan staan er geen andere containers in de weg. Daarnaast wilde wij ook methodes selecteren naar welke wij meer onderzoek wilde doen om te achterhalen hoe geschikt zijn voor het oplossen van de probleemstelling.

### Onderzoeksvraag 2
Om te achterhalen welke mogelijkheden er zijn om dit probleem op te lossen doormiddel van data science moet hier onderzoek naar gedaan worden. Op basis hiervan is er de volgende onderzoeksvraag opgesteld: Welke data science mogelijkheden zijn er om de indeling van containers op de kade te bepalen? Om deze onderzoeksvraag te beantwoorden is er deskresearch uitgevoerd door verschillende papers, blogs en video's bestudeerd om verschillende methodes van AI te bestuderen.

## Evaluation

Het indelen van de containers is momenteel nog niet gelukt voor de gehele kade van de klant van Cofano. Momenteel is er maar een klein gedeelte hiervan gebruikt voor het berekenen van de ideale indeling van de containers. Voor verder onderzoek kan de environment van het reinforcement model uitgebreid worden om de gehele kade te berekenen.

Door gebrek aan tijd is het ons niet gelukt om het reinforcement model te trainen op een kade die gedeeltelijk gevuld is. Als we meer tijd hadden gehad, dan zouden wij dit proberen en de resultaten ervan analyseren. 

Tijdens ons onderzoek hebben wij ons gefocused op het optimaliseren van het uitlaad proces om het inlaadproces te kunnen versnellen door containers die naar hetzelfde schip gaan bij elkaar te zetten. Helaas zijn we er niet aan toe gekomen om het inlaadproces zelf te simuleren. In deze simulatie zou een echte situatie nagebootst kunnen worden, maar met de containers ingedeeld op basis van het reinforcement model. Hiermee zou het model gecontroleerd kunnen worden om te bepalen of de containers in de gesimuleerde omgeving sneller ingeladen zijn.

In de gesimuleerde situatie wordt er momenteel maar gebruik gemaakt van één machine om de containers te verplaatsen. Dit zou uitgebreidt kunnen worden door meerdere type machines en/of meerdere machines van dezelfde soort. Nu wordt er maar één reachstacker gebruikt, maar er zijn op de haven ook kranen en andere machines voor transport van containers.

Voor het trainen wordt momenteel zelf gegenereerde data gebruikt voor het bepalen van de hoeveelheid containers die aankomen en naar hoeveel schepen deze toe moeten. Hiervoor is er niet gebruik gemaakt van de schema's of planning in echte situatie. Als er meer tijd zou zijn, dan was dit een onderdeel waar wij onderzoek naar zouden doen om deze data te gebruiken voor het simuleren van de omgeving.

## Conclusions
Tijdens het onderzoek zijn er twee methodes onderzocht welke mogelijk het proces van containers indelen op de kade kunnen verbeteren. Bij Reinforcement Learning is er de mogelijkheid op basis van input data de containers in te delen op de kade. Momenteel geef je aan het model mee hoeveel containers je wilt plaatsen op de kade en over hoeveel schepen deze verdeeld zijn. het model gaat dan trainen op de verschillende mogelijkheden die er zijn van de input die je hebt gegeven.



![image](https://user-images.githubusercontent.com/121485743/212847752-812bb992-70a0-470c-8c58-c3be6453c7b6.png =250x250)



## Planning
Voor het plannen van de verschillende sprints en onderzoeken is er gebruik gemaakt van een scrumboard. Dit Scrumboard is gemaakt op de website Trello. Hieronder ziet u een foto van het scrumboard zoals deze er momenteel uit ziet.
![image](https://user-images.githubusercontent.com/121485743/212014720-201f27d9-c6a4-49cb-bfe5-3f1d323ba3be.png)
Op de foto zijn vijf verschillende blokken te zien. allereerst is er de backlog. In de backlog staan onderdelen welke in een latere sprint uitgevoerd gaan worden. Deze onderdelen staan nog in de backlog ondanks dat het onderzoek klaar is, want als er meer tijd was dan hadden wij deze taken nog willen uitvoeren. In het onderdeel To Do staan onderdelen die deze sprint nog uitgevoerd moeten worden. Het volgende blok heet Doing. In dit blok staan de onderdelen waar momenteel aan gewerkt wordt. Het vierde blok genaamd Checking gaat over onderdelen welke momenteel gecontroleerd moeten worden. Dit kan intern door een ander teamgenoot zijn of door één van de begeleiders van het onderzoek. In dit geval staan er drie onderdelen van de paper. Deze onderdelen zijn opgestuurd naar Tony ter controle. Als laatste blok is er het onderdeel Done. In de blok staan alle activiteiten die afgerond zijn. Hierin zijn ook de activiteiten van de vorige sprints te vinden. Aan elke activiteit wordt een persoon of meerdere personen aan gekoppeld. Zo is er overzichtelijk wie waaraan werkt en ontstaat er een verantwoordelijkheid voor de verschillende activieiten. Op deze manier kon er gecontroleerd of iedereen met zijn werk bezig en voldoende tijd besteede aan het onderzoek.

