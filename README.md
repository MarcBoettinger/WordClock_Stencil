# WordClock_Stencil

WordClock stencil for the project described in
https://smarthome.family.blog/2018/12/10/ikea-ribba-wordclock-bussystem/


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

 
