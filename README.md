# Sensor Board V1

## Platine in Betrieb nehmen:
1. Keine Fuses einlöten, reverse polarity testen (Q1201)
	- Q1201 Pin 3 liegt Versorgungsspannung an
	- V_IN LED (D1210) leuchtet
	- F_Vdrive einlöten, Vdrive LED (D1206) leuchtet
2. Buck converter:
	- F_BUCK (F1201) einlöten
	- U1201 Pin 1 liegen 6V an
	- U1202 Pin 2 liegen 5V an
	- U1203 Pin 2 liegen 5V an
3. LDOs:
	- F_5VA, F_5V und F_3V3 nacheinander einlöten und Ausgänge testen
	- 5VA, 5V und 3.3V LEDs leuchten auf
	- Versorgung wegnehmen und F_USB einlöten
	- USB Versorgung anschließen
	- V_IN, Vdrive und 5VA LEDs bleiben aus, 5V und 3.3V leuchten
	- USB Jumper links setzen (Pins 2+3), 5VA LED leuchtet
	- Spannung an U1203 Pin 2 ist ~0V
	- USB Jumper alle Pins verbinden
	- Spannung an U1202 Pin 2 ist ~0V
	- Eingangsspannung verbinden, V_IN und Vdrive leuchten, Stromverbrauch normal
	- Spannung über D1204 und D1205 messen, danach USB Jumper rechts setzen (Pins 1+2)
	- USB Versorgung trennen, Ausgangsspannung U1202 vergleichen zwischen USB und ohne -> D1204 überbrücken? Wenn ja, Jumper USB nur noch wechseln zwischen 1/2 und 2/3
4. STM32:
	- ST-Link verbinden und Testprogramm aufspielen
	- STATUS LED blinkt
	- Versorgungsspannung wegnehmen
	- USB Versorgung verbinden und erneut Testprogramm aufspielen
	- STATUS LED blinkt immer noch
	
## Prüfen:
- 74HC595 Ausgangsspannung an PU/PD Widerständen!
- Flankensteilheit Halbbrücken einstellen

## Für V2:
- Halbbrücken näher an Stecker (Halbbrücken, 1A-Profets, Buck converter)
- STM um 90° drehen
- USB Stecker weiter herausstehen lassen
- kleinere Gehäuse für ICs nutzen
- Level shifter für 74HC595 nicht notwendig
- 3.3V Outputs??
- Umschalten Ausgangsspannung per Software
- Umschalten USB Versorgung per Software?? (Falls keine Eingangsspannung messbar)
- CAN schaltbare Terminierung
- Vierundzwanzig24 Logo!!!
- AMPSEAL um 0.8mm (0.7mm?) nach innen verschieben