# Argumentatie
| Blok      | Pro's/contra's                                                                                                |
|-----------|---------------------------------------------------------------------------------------------------------------|
| ATSAMD21G | Genoeg pinnen om eventueel uitbreiding te ondersteunen                                                        |
| SDS011    | <ul><li>Geen soldeerwerk</li> <li>Plug-and-play</li> <li>Libraries om waarden uit te lezen</li></ul>                                            |
| HIH8120   | <ul><li>I²C communicatie</li> <li>Enige communicatie pinnen op de SAMD21 die over zijn in samenwerking met de andere sensoren</li></ul> |
| RFM95W    |<ul><li>SPI connectie</li><li>Compact</li><li>beschikbaar in het labo</li><ul>                                                             |
| L7805     | Voltage regulator is sterk genoeg om de sensoren te voeden.                                                   |
| LM317     | Voltage regulator is sterk genoeg om de ATSAMD21 en de RFM95W te voeden.                                      |
| Li-Ion Batterij - 18650 - 3,7V 2900mAh                                | <ul><li>Grote capaciteit</li> <li>Snelladen</li> <li>Lage self-discharge</li> <li>Gebruikstemperatuur -20 <==> 60 graden Celcius</li> <li>oplaadtemperatuur 4 <==> 45 graden Celsius</li> |
| Batterijhouder voor 18650 batterijen                                  | <ul><li>Geen soldeerwerk op de batterijen</li> <li>Makkelijk accu te vervangen</li> <li>Makkelijk extern op te laden</li></ul>     