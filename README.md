# WordClock_Stencil

WordClock stencil for the project described in
https://smarthome.family.blog/2018/12/10/ikea-ribba-wordclock-bussystem/


WordClock Bausatz – Bussystem
Qlocktwo Nachbau
Click here for English version


Motivation zum Bau einer WordClock
Eine WordClock oder Wortuhr ist eine wirklich ansprechende Uhr, die die Uhrzeit in Wörtern als Satz anzeigt. Eine kommerzielle WordClock kann leicht über 1000 EUR kosten wie zum Beispiel die qlocktwo, was eher die Originalität zum Ausdruck bringt als den wirklichen Warenwert. Nachdem wir ein Bussystem verwenden, sollte jeder, der etwas Erfahrung beim Löten und Basteln hat, sollte diese Uhr eigentlich in ca 8h günstig bauen können. Zum Glück kann man die LEDs ansteuern und muss nicht pro LED zwei Lötstellen plus Vorwiderstand (3×144) erstellen.

Aus dem Grund habe ich eine WordClock nach einigen Anleitungen nachgebaut und möchte gerne meine Erfahrung weitergeben, da einige Kleinigkeiten zu beachten sind

Wie baue ich eine Wortuhr?
Material kaufen, wie Rahmen, LEDs & Arduino
LED Streifen aufkleben und verlöten
Trennstege für die LEDs erstellen
Frontplatte erstellen
Arduino Code aufspielen
Die Schritte im einzelnen.

Materialliste
Bauteil	Bezugsquelle	Alternative Bezugsquelle	Weitere Bezugsquelle
Ikea Ribba Rahmen 23x23cm	Amazon	Ikea
Arduino Nano	Amazon	Ebay	 Aliexpress
RTC DS3231 Modul	Amazon	Ebay	Aliexpress
Netzteil, 3A	 Amazon	Ebay	 Aliexpress
144 (5M) x 60led/m WS2812B LED	 Amazon	eBay	Aliexpress
zwei Reedkontakte (optional)	 Amazon	Ebay	Aliexpress
300 Ohm Widerstand	
Amazon	Ebay	Aliexpress
3D Drucker (optional)	 Amazon	 eBay	 AliExpress
Bausatz Wordclock
Ribba Rahmen mit Gitter
LED Streifen aufkleben und löten
Zunächst wird die Rückseite aus dem Ribba Rahmen entnommen. Auf dieser wird ein Hilfsgitter mit Bleistift aufgezeichnet um später die LED Streifen besser befestigen zu können. Die Abstände der Linien sind

– 15mm, 31.67mm, 48.33mm, 65mm, 81.67mm, 98.33mm, 115mm, 131.67mm, 148.33mm, 165mm, 181.67mm, 198.33mm, 215.00mm

Danach werden die LED Strips aufgeklebt. Dabei wird unten rechts mit dem ersten Streifen begonnen. Auf den Streifen sind kleine Pfeile, die Pfeile auf dem ersten Streifen unten weisen also von rechts nach links. Der zweite Streifen geht von links nach rechts, also genau entgegen dem ersten Streifen. Wir fahren fort bis zum letzten, den 12. Streifen.

Wir erhalten somit eine Zig Zag Linie. Man kann dadurch die Streifen ideal miteinander verlöten, jeweils mit einem recht dicken Draht jeweils Minus mit Minus und Plus mit Plus. Die Datenleitungen verbinden wir auch im Zig Zag Muster.

Am Anfang des LED Streifens unten rechts wird eine Zuleitung für den Strom sowie die Datenleitung gelegt. Am Ende des Streifens wird lediglich Plus und Minus nochmals mit einer Stromleitung verbunden. So kann man den Streifen von zwei Seiten mit Strom versorgen.

LED WS2812B aufgeklebt
WS2818b auf Ribba Pappe
Trennstege der LEDs erstellen
Auf die LED Streifen wird nun ein Rahmen von 12×12 gesetzt um die einzelnen LEDs voneinander abzuschirmen. Das kann man entweder dadurch geschehen, daß man den Schaumstoff in 13×13 Streifen  schneidet, wobei man alle 16.67mm  Platz für die Überlappungen braucht. Alternativ druckt man sich einen solchen Rahmen mit einem 3D Drucker aus.

LEDs mit 3d gedruckten Trennstegen
LEDs mit 3D Druck der Trennstege
Frontplatte erstellen
Die Buchstaben können mit einem Laserdrucker auf eine transparente Folie gedruckt werden. Wir benötigen dazu ca. 3 Folien um genügend Abdeckung zu erhalten. Am besten erstellt man die Buchstabenvorlage in Excel.

Alternativ kann man sich auch eine Maske mit dem 3D Drucker ausdrucken und danach lackieren. Ich habe dafür ein 3D Modell erstellt. Da ich dazu einen ganzen Tag benötigt habe, wäre es toll, wenn Ihr mir ein Bier PayPal spendiert, falls ihr die Vorlage nützlich findet. Dann gibt es auch Zugang zu den Original 3D Modellen.

https://github.com/MarcBoettinger/WordClock_Stencil

3d Sketch Buchstaben
3D Modell der Frontplatte
3D printed front cover wordclock
3D printed front cover wordclock
Danach habe ich die vier 3D Platten miteinander verklebt und einem Schleifpapier glatt geschliffen. Um  die Optik anprechend zu machen habe ich die Front mit einem Zink-Spray lackiert.

Elektronik verdrahten
Die Verdrahtung der Elektronik ist relativ simpel

Wir verbinden die Datenleitung des LED Streifens über den 300 Ohm Widerstand an Arduino Pin 6
Arduino PINs A4  an DS3231 SDA
Arduino A5 an DS3231  SCL
Wir schließen +5V and GND des Arduino an den DS3231
Wir verbinden das Netzteil mit den 5V+ des LED Streifens und den Arduino mit einer Zuleitung, die 3A verträgt
PIN D8 und PIN D10 verbinden wir jeweils über einen Reedkontakt oder Taster mit VCC
PIN D8 und PIN D10 verbinden wir mit einem 10k Widerstand auf GND
Optional habe ich noch eine 2000uF Kondensator an die Spannungsquelle gehängt um Spannungsspitzen abzufangen
WordClock Wiring

Unterbringung Arduino
Ribba Rahmen Rückseite mit Arduino
Code aufspielen
Den Code schicke ich Euch bei Interesse gerne per Email. Meine Emailadresse steht im Impressum.

Test
Zunächst werden einmal alle LEDs in den drei Grundfarben RGB ausgetestet. Wenn man alles an ein Netzgerät mit Leistungsanzeige angeschlossen hat, kann man sehen wie bis zu 3A gezogen werden, wenn alle LEDs angeschaltet sind. Im laufenden Betrieb wird deutlich weniger Strom verbraucht, allerdings sollte das Netzteil leistungsfähig sein.

Viel Spass beim Basteln!

English Version

Idea to build a WordClock
A WordClock is a truly appealing clock that displays the time in one sentence. A commercial WordClock can easily cost over 1000 EUR, which expresses originality rather than the real value of the goods. As we use a bus system, anyone with some experience in soldering and handicrafts should be able to build this clock in about 8 hours. Fortunately, you can control the LEDs and don’t have to create two solder joints plus a series resistor (3×144) per LED.

For this reason I have built a WordClock after some instructions and would like to pass on my experience, as there are a few small things to keep in mind.

How do I make a word clock?
Buy material such as frames, LEDs & Arduino
Glue LED strips and wire them
Create separators for the LEDs
Create the front panel
Compile Arduino Code and flash it
The steps in detail.

Material list
Table

Part	Source	Alternative Source	Additional Source
Ikea Ribba Frame 23x23cm	Amazon	Ikea
Arduino Nano	Amazon	Ebay	 Aliexpress
RTC DS3231 Modul	Amazon	Ebay	Aliexpress
Power, 3A	 Amazon	Ebay	 Aliexpress
144 (5M) x 60led/m WS2812B LED	 Amazon	eBay	Aliexpress
two reed relays (optional)	 Amazon	Ebay	Aliexpress
300 Ohm resistor	
Amazon	Ebay	Aliexpress
3D printer (optional)	 Amazon	 eBay	 AliExpress
Bausatz Wordclock
Installing the LED Strip
First remove the rear side from the Ribba frame. On this frame draw an auxiliary grid with a pencil in order to be able to fix the LED strips later better. The distances of the lines are

– 15mm, 31.67mm, 48.33mm, 65mm, 81.67mm, 98.33mm, 115mm, 131.67mm, 148.33mm, 165mm, 181.67mm, 198.33mm, 215.00mm

Then the LED strips are glued on. Start with the first strip at the bottom right. There are small arrows on the strips, so the arrows on the first strip at the bottom point from right to left. The second strip goes from left to right, exactly against the first strip. We continue to the last, the 12th strip.

We get a zig zag line. One can solder the strips ideally with each other, in each case with a quite thick wire minus with minus and plus with plus. We also connect the data lines in the zig zag pattern.

At the beginning of the LED strip at the bottom right a supply line for the current as well as the data line is laid. At the end of the strip only plus and minus is connected again with a power line. So the strip can be supplied with power from two sides.

LED WS2812B aufgeklebt
Separators of the LEDs
A 12×12 frame is now placed on the LED strips to shield the individual LEDs from each other. This can be done either by cutting the foam into 13×13 strips, where you need all 16.67mm space for the overlaps. Alternatively you can print such a frame with a 3D printer.

LEDs mit 3d gedruckten Trennstegen
The Front Cover
The letters can be printed on a transparent foil with a laser printer. We need about 3 foils to get enough coverage. The best way is to create the letter template in Excel.

Alternatively, you can print out a mask with the 3D printer and then varnish. I have created a 3D model. Since it took me a whole day, it would be great if you could buy me a beer (PayPal) if you find the template useful.

https://github.com/MarcBoettinger/WordClock_Stencil

3d Sketch Buchstaben
3D Modell der Frontplatte
3D printed front cover wordclock
3D printed front cover wordclock
Then I glued the four 3D plates together and sanded them smooth with sandpaper. For an appealing look I painted the front with a zinc spray.

Electronics
The wiring of the electronics is relatively simple

We connect the data line of the LED strip via the 300 Ohm resistor to Arduino Pin 6.
Arduino PINs A4 to DS3231 SDA
Arduino A5 to DS3231 SCL
We connect +5V and GND of the Arduino to the DS3231
We connect the power supply with the 5V+ of the LED strip and the Arduino with a 3A compatible lead.
We connect PIN D8 and PIN D10 each via a reed contact or a push button to +5V
Pin D8 and pin D10 are connected via an 10k resistor with GND
Optionally I have attached a 2000uF capacitor to the voltage source to intercept voltage peaks.
WordClock Wiring

Unterbringung Arduino
Ribba Rahmen Rückseite mit Arduino
Code
If you are interested I will send you the code by email. My email address is in the imprint.

Test
First of all, all LEDs in the three basic colours RGB are tested. If you have connected everything to a power supply with power indicator, you can see how up to 3A are drawn when all LEDs are switched on. During operation the power consumption is much lower, but the power supply should be powerful.

Have fun tinkering!

 
