# Analyse Document
# teamleden
Vital Volckaerts
Keno Van Deuren
Quinten Van Ginderen
## Probleem stelling
The port of Antwerp is zeer geïntresseerd in de luchtkwaliteit in en rond de haven. Antwerpen heeft al vele maatregelen genomen om de luchtkwaliteit te doen verbeteren en de haven wilt nu opsporen of zij hun steentje niet kunnen bijdragen. Hiervoor moeten ze eerst bekijken of dat mogelijk is en de luchtkwaliteit in kaart brengen. Ze weten dat ze dit door sensoren te plaatsen op verscheidene locaties kan lukken en dat een LoRaWAN netwerk hiervoor een perfecte hulp kan zijn. Dit hebben ze dus al opgezet over de hele haven, maar sensoren zijn er nog niet.
### Analyse
#### Abstract
![Abstract Design](img/Abstract_Design.jpg)
#### Smart Object (Hardware Analyse)
![Blokdiagram](img/HW_Blokdiagram.jpg)
##### Specificatie tabel
| Blok                   | Specificatie | Min   | Nominaal    | Max   |
|------------------------|--------------|-------|-------------|-------|
| Lithium-batterij 18650 | Werkspanning | 3V    | 3,6V        | 4,2V  |
|                        | Capaciteit   |       | 2850mAh     |       |
|                        | Stroom       |       | 28,50A(10C) |       |
| ATSAMD21               | Werkspanning | 1,62V |             | 3,63V |
|                        | Fcpu         |       |             | 48MHz |
| SDS011                 | Werkspanning | 4,7V  | 5V          | 5,3V  |
|                        | Stroom       | <4mA  |             | 80mA  |
| Zonnepaneel            | Werkspanning |       | Ongekend    |       |
|                        | Stroom       |       | Ongekend    |       |
##### Argumentatie en alternatieven tabel
###### Argumentatie
| Blok      | Pro's/contra's                                                                                                |
|-----------|---------------------------------------------------------------------------------------------------------------|
| ATSAMD21G | Genoeg pinnen om eventueel uitbreiding te ondersteunen                                                        |
| SDS011    | <ul><li>Geen soldeerwerk</li> <li>Plug-and-play</li> <li>Libraries om waarden uit te lezen</li></ul>                                            |
| HIH8120   | <ul><li>I²C communicatie</li> <li>Enige communicatie pinnen op de SAMD21 die over zijn in samenwerking met de andere sensoren</li></ul> |
| ATSAMD21E | Te weinig pinnen voor eventuele uitbreiding                                                                   |
| RFM95W    |<ul><li>SPI connectie</li><li>Compact</li><li>beschikbaar in het labo</li><ul>                                                             |
| L7805     | Voltage regulator is sterk genoeg om de sensoren te voeden.                                                   |
| LM317     | Voltage regulator is sterk genoeg om de ATSAMD21 en de RFM95W te voeden.                                      |
| Li-Ion Batterij - 18650 - 3,7V 2900mAh                                | <ul><li>Grote capaciteit</li> <li>Snelladen</li> <li>Lage self-discharge</li> <li>Gebruikstemperatuur -20 <==> 60 graden Celcius</li> <li>oplaadtemperatuur 4 <==> 45 graden Celsius</li> |
| Batterijhouder voor 18650 batterijen                                  | <ul><li>Geen soldeerwerk op de batterijen</li> <li>Makkelijk accu te vervangen</li> <li>Makkelijk extern op te laden</li></ul>                                               |
###### Alternatieven

| Part                                                                  | Pro's en contra's                                                                                                                        |
|-----------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------|
| Adafruit Feather M0                                                   | <ul><li>Usb programmeerbaar</li> <li>Genoeg CPU-kracht</li> <li>Zuinig</li></ul>                                                                                           |
| BME680 Breakout - Air Quality, Temperature, Pressure, Humidity Sensor | <ul><li>Compact</li>  <li>Grote input-voltage range</li> <li>I2C (0x76 \| 0x77)</li>  <li>4 in 1</li>  <li>Nadeel: lange settle-time</li>|
| ATSAMD21E | <ul><li>Te weinig pinnen voor eventuele uitbreiding</li></ul> |
#### Software Analyse
##### Data In- en Outputs
| Blok     | Data In            | Data Out                                            |
|----------|--------------------|-----------------------------------------------------|
| ATSAMD21G | Sensor data (alle) | Sensor data (alle)                                  |
| SDS011   | N.V.T.             | Sensor data (fijnstof)                              |
| HIH8120  | N.V.T              | <ul><li>Sensor data (temperatuur)</li> <li>Sensor data (vochtigheid)</li></ul> |
| RFM95W   | Sensor data (alle) | Sensor data (alle                                   |
##### State diagram
###### ATSAMD21
![Statediagram ATSAMD21G](img/Statediagram_ATSAMD21.jpg)
###### RFM95W
![Statediagram RFM95W](img/Statediagram_RFM95W.jpg)
##### Flowchart
![Flowchart](img/Flowchart.jpg)
##### Mockup
###### Homepagina
![Mockup Homepage](img/HomePage.jpg)
###### Historiek
![Mockup History page](img/HistoryPage.jpg)
###### Kaart
![Mockup Map page](img/MapPage.jpg)
## Bronnen
