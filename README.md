# IOT-project


Voor het keuze vak IoT voor Data science moet ik een IoT project beginnen. 
Het project moet iets inbregen voor de mens als in het hoofd doel. 
Als het gelukt is moet ik er een repository over maken. 

# De begin fase
Als eerste leerden wat data science en IoT inhoude. Hier merkte ik meteen dat ik met mijn computer
skills nog niet ver genoeg was om zo iets te maken en daardoor ook tegen veel problemen aan liep.
Echter zal ik mijn idee wel uitleggen en hoe je zo iets zou kunnen maken.

De eerste stap is een Raspberry pi en een SD kaartje met daar op noob of Raspbian.

![image](https://user-images.githubusercontent.com/95296656/152030991-1c2ae71d-23ec-4e2e-8c63-fb94f2a7bd27.png)

Dit is de software raspbian
![image](https://user-images.githubusercontent.com/95296656/152031037-74ac084c-a9a1-4df6-b5a0-2143d8de25cb.png)


Voor het project heb je een paar extra liberies nodig. Dit is namelijk nodig om met de sensor te kunnen communiceren.
De sensor die we voor het project nodig hebben is DHT22. 

![image](https://user-images.githubusercontent.com/95296656/152031398-7c8bbe9d-4354-4dbc-a4e9-1e74d599f5fc.png)

Daar naast heb je kabletjes nodig en een breadbord.
![image](https://user-images.githubusercontent.com/95296656/152031512-9f1d9808-dad2-40b9-b6fe-9c4a0f438f09.png)


De tweede stap  is om alle electronische componenten aan elkaar te sluiten.
Daarvoor heb je een resistor nodig zodat de sensor niet te veel stroom krijgt.
Je hebt daar een 4.7k ohm.
![image](https://user-images.githubusercontent.com/95296656/152031888-99c55ed6-79a5-402c-847d-99ecac4cdce2.png)

Nu dat we alle componenten hebben gaan we alles aansluiten. 

![image](https://user-images.githubusercontent.com/95296656/152032081-18837e17-d742-4e07-8204-3ab3986495a7.png)

Je kan aan de kleur van de kabel waarvoor het bedoelt is. Rood is power, Zwart is grond, en blauw is de data.

# Fase 2

In deze fase gaan we de benodigte software instaleren. 

Voor dat we dat doen zorg ervoor dat je Pi is geconnect tot het internet. Dit heb je nu maar ook later nodig in dit project.


Open de shell de shell in de raspberry pi.
Voor het volgede command in
> sudo apt-get update 
> sudo apt-get upgrade

Voor het installeren van de software en het programmeren hebben we Python 3 nodig.
Python 3 is als geinstalleerd door de OS zelf, maar we hebben extra tools nodig.
Dit doen we met het volgende command:
> sudo apt-get install python3-dev python3-pip
> sudo python3 -m pip install --upgrade pip setuptools wheel

Nu dat de OS Up to Date is kunnen we beginnen met het instaleren van de SDK van de Sensor.
Daarvoor hebben we de volgende command:
> sudo pip3 install Adafruit_DHT> sudo apt-get upgrade 


# Fase 3
In deze fase maken we contact met de sensor en gaan we data ervan halen.

ALs eerst maken we een script aan. 
Je kan dit op meerdere manieren doen. 
De manier waarop ik het gedaan heb is:
> nano ~/humidity.py

De script kan je vinden in de map Scripts samen met alle andere die ik gebruikt heb.

Om de script uit te voeren doe je het volgende commando:
> python3 ~/humidity.py

Het antwoord dat je zou moeten krijgen is: 
> Temp=19.2C humidity=51.8%

Wat ik hierna gedaan heb is een logger geschreven. Zodat ik bij kan houden wanneer er een tempretuur is opgenomen. 
Dit kan ook later helpen met het debuggen als er iets mis is gegaan.

Ik heb het document op het zelfde manier aan gemaakt.
> nano ~/humidity_logger.py
Ook deze script zal je terug kunnen vinden.
De script kan je ook op de zelfde mannier gebruiken.
> python3 ~/humidity_logger.py
en om het txt bestand te zien kan je het volgende commando gebruiken:
> nano ~/humidity.csv

Moet je alle scripts op deze manier aanmaken en gebruiken. Nartuurlijk niet, er zijn meerdere manieren voor. Echter 
vind ik zeld dit de meest leuke manier om het te doen. Het is alleen niet altijd even makkelijk.

# De laatste fase
In deze fase is het de bedoeling dat je een connectie maakt met thingSpeak.
ThingSpeak is een programma dat je kan gebruiken voor data science. Het kan bijvoorbeeld een grafiek maken van de tempratuur en humidity. Echter is het mij nog niet gelukt om dit werkend te maken. Dit is wel mijn doen en zal ook na het einde verder werken aan het project. Ik naar mijn mening iets gevomden wat uitdagend, leuk en dat je het resultaat meeteen ziet. 
Het lijkt er op dat dit door de tijd heen een soort nieuwe hobbie is geworden. Maar ik moet er wel voor leren programmeren en in electronica gaan verdiepen. Zodat ik meer sensoren kan gaan gebruiken en dat ik een beetje weet hoe ik iets moet aansluiten.

Dit gezegt te hebben gaan we verder.
Om ThingSpeak te kunnen gebruiken heb je een account nodig. Deze kan je aan maken op de website.

![image](https://user-images.githubusercontent.com/95296656/152038781-2c4514c9-6d1b-40ce-b8e5-e80883782517.png)

ALs je een account heb gemaakt dan kom je op dit scherm terecht:
![image](https://user-images.githubusercontent.com/95296656/152039170-536e45f2-9dec-489f-a31f-9cc2f70c2478.png)
Maak een nieuwe Channel aan
![image](https://user-images.githubusercontent.com/95296656/152039443-ac60a2fc-68db-4532-a594-ac3e495a2a68.png)
Zorg er voor dat je de Channel een naam geeft en dat je Field 1 een naam geeft. Bijvoorbeeld temperatuur. ALs je dat gedaan heb 
kan je op save Channel klikken.

Als volgende wil je naar de tab van API Keys gaan deze heb je nodig voor de connectie van de Raspberry Pi naar ThingSpeak.
![image](https://user-images.githubusercontent.com/95296656/152041423-51951806-bad9-42de-b1e1-e20a1b9bdde6.png)

Nu is het de bedoeling dat we door middel van een script een connectie maken. Dit is mij helaas nog niet gelukt. Dit komt door medere problemen waar ik op dit moment nog geen oplossing heb. Zo vind de OS de Cammand
>pip3 
niet of wilt hij de liberry van de sensor niet goed installeren. Dit is later wel gelukt alleen het is soms een beetje buggy. 
Het kan ook zijn dat ik perongelijk de sensor een beetje laten branden. Dit kwam doordat ik perongeluk de verkeerde resistor gebruikt had. 
