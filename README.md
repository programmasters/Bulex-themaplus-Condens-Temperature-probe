# Bulex-Themaplus-Condens
Information regarding the Bulex Themaplus condens, should also be applicable to Themfast, Isotwin and thema condens.
I did not wanted to use the Mipro or any other type of thermastat, since I wanted to integrate the boiler into a BMS(building management system) via either a openthem or on/off relay. The problem is then, how to use the heating cruve, based on enableing option D.162 in the diagnostic menu (installer level code 96) When weather dependant operation is enabled, the temperature is measured and using the heating curve setting of D.043, a hot water departure temperature is set. 
# Outside Temperature sensor
The basis of the outside temperature sensor is a 1 kOhm NTC with two limiting resistors on either side. At 21.1°C, the resistance equals 1118 Ohm, at 20.5°C it equals 1085 Ohm. Presumably a quasi linear.
The reference part number of the outside sensor is **0020266792**
# Measurement by Bulex
Connected on port X41 between pin 1 and 5, the boiler puts a 5V reference voltage over the NTC. Presumably using a voltage divide using another 1kOhm resitor in series with a voltage measurement over pin 1 and 5 (no mA measurement) So by putting a reference voltage on these pins, it is possible to fool the Bulex into thinking the outside temperature is 0°C by putting around 2.500V on these pins. The higher the voltage, the lower the interpreted temperature. Given a heating curve, it is possible to calculate the departing water temperature, and influencing it. Possible to create a PI(D) controller to get to a steady state heating system.


##Dutch

#Bulex-Themaplus-Condens

Informatie met betrekking tot de Bulex Themaplus condens zou ook van toepassing moeten zijn op Themfast, Isotwin en thema condens. Ik wilde geen gebruik maken van de Mipro of een ander type thermostaat, omdat ik de boiler wilde integreren in een BMS (gebouwbeheersysteem) via een openthem of aan/uit-relais. Het probleem is dan hoe de verwarmingscurve te gebruiken, op basis van het inschakelen van optie D.162 in het diagnostische menu (installateur niveau code 96). Wanneer de weerafhankelijke werking is ingeschakeld, wordt de temperatuur gemeten en wordt op basis van de verwarmingscurve-instelling van D.043 een gewenste vertrektemperatuur voor warm water ingesteld.

#Buitentemperatuursensor

De basis van de buitentemperatuursensor is een 1 kOhm NTC met twee begrenzende weerstanden aan weerszijden. Bij 21,1°C bedraagt de weerstand 1118 Ohm, bij 20,5°C bedraagt deze 1085 Ohm. Waarschijnlijk quasi-lineair. Het referentieonderdeelnummer van de buitensensor is 0020266792.

#Meting door Bulex

Aangesloten op poort X41 tussen pen 1 en 5, levert de ketel een referentiespanning van 5V over de NTC. Waarschijnlijk wordt een spanningsdeling toegepast met nog een 1 kOhm weerstand in serie met een spanningsmeting over pen 1 en 5 (geen mA-meting). Door een referentiespanning op deze pinnen te zetten, is het mogelijk om de Bulex te laten denken dat de buitentemperatuur 0°C is door ongeveer 2.500V op deze pinnen te zetten. Hoe hoger de spanning, hoe lager de geïnterpreteerde temperatuur. Met behulp van een verwarmingscurve is het mogelijk om de vertrektemperatuur van het warme water te berekenen en te beïnvloeden. Het is dan mogelijk om een PI(D)-regelaar te creëren om een stabiel verwarmingssysteem te bereiken.
