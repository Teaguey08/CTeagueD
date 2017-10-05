# CTeagueD

This is an atlernative CTD design from the CTDizzle it is basically the same but the wiring is slightly different and in a Larger 3” Bluerobotics watertight enclosure.
This design also features 3D printed parts in the form of an Parts Include a protector for the ends of the probes and an electronics sled complete with mounting points for components, a battery holder for the 1s lipo 1000mah and a sleave for potting the conductivity probe from the other side so it cannot be pushed through the epoxy base.
![alt text](https://github.com/Teaguey08/CTeagueD/blob/master/CTD%20Protector%20v10.jpg)

This guide is to be used in conjuction with CTDizzle https://github.com/Teaguey08/CTDizzle/blob/master/MKRZero/MKRZero_UserGuide.mddesign but it does deviate at certain points such as circuit diagram and the extra of the 3D printed parts so i suggest you follow his guide and subsitute out the circuit diagram and follow the rest of the guide. 

## UK based Parts list
This CTD will cost around £540 (before postage or shipping). UK Parts (Where possible).

|Part	|Vendor	 |Price 	|Note|
|-----|--------|-------|------|
|Conductivity Kit 1.0|	http://www.robotshop.com/uk/atlas-scientific-conductivity-sensor-k-10-kit.html| £ 194.74 |	Includes EC EZO, probe, and calibration solutions.|
|MKRZero|	https://store.arduino.cc/arduino-mkrzero |£18.60 |	This will be euros|
|MKR ProtoShield|	https://store.arduino.cc/mkr-proto-shield| £5.20 |	This will be euros|
Cable Penetrator Blank (No Hole)|	https://www.bluerobotics.com/store/connectors/penetrator-blank-10-25-a-r2/|£10.20 |	You will need 3 of these (You also get 15% off for 3-9 units) This will be Dollars.|
Bar30 High-Res Depth Sensor	|https://www.bluerobotics.com/store/electronics/bar30-sensor-r1/| £57.00| 	This will be Dollars|
Celsius Fast-Response Temp Sensor|	https://www.bluerobotics.com/store/electronics/celsius-sensor-r1/| £42.30| 	0.1 accuracy. This will be Dollars.|
Penitrator Switch |	https://www.bluerobotics.com/store/electronics/switch-10-5a-r1/| £10.60| 	This will be Dollars|
2" Water Tight Enclosure Kit - 6"|	https://www.bluerobotics.com/store/watertight-enclosures/wte3-asm-r1/#configuration| £170.00 |	Select the 3" aluminum main tube, two flanges, and two aluminum end caps with the four holes pre-drilled. Includes o-rings and screws. This will be Dollars.|
12mm Coin Cell|	https://www.proto-pic.co.uk/coin-cell-battery-12mm-cr1225.html| £0.77| 	Needs to be replaced annually.|
DeadOn RTC|	https://www.proto-pic.co.uk/deadon-rtc-ds3234-breakout.html|£15.25| +/- 2 min drift per year|
MicroSD Card with Adapter|	https://www.proto-pic.co.uk/kingston-sdc44gb-4gb-sdhc-micro-memory-card.html| £6.80| 4GB card|
3.7V 1000mAh Li-Ion Battery|https://www.proto-pic.co.uk/polymer-lithium-ion-battery-37v-1ah.html| £7.80| 	Last for about 60 hours if sampling at 1Hz|

## Ardunio MRK Zero
Mine came with headers and pins extending from the bottom. Snip the produding pins away so it can sit flush the correct way up.
The MRK Protoshield came with headers so solder these in place making sure the board is correctly aligned and the headers are flush to the board. Test fit these together to make sure no pins are missalgined or bent. Be careful when soldering not to damage these.
Soldering compoents

### Tools
- Soldering iron
- Solder
- Wire cutters
- Patience
- Multimeter

This differs from CTDizzles Design as he made the Protoboard removable from the compoents via connectors and has a lot of jumpers to do. This design the protoboard is not removable but the MRK Zero is. I have included a picture/ diagram of the solder points, most wires come through from the bottom of the board for tidyness. 

## PIN Outs (Adpated from CTDizzle)
I have grouped the wiring and pin connections rather than compeoents, this helped me to plan out a soldering pattern. Many of these compoents have shared pin outs on the MKR Zero, I soldered along in lines and connected solder points together to achieve a breadboard effect as the protobaord is all separate connections. (This can be quite tricky and fustrating so I suggest doing on line (Row) at a time as the solder wants to attach collumns and rows, which you don’t want). Note if you are using the 3D printed sled you have to pass wires and probe through one of the end cap parts. One hole is for wires the other for conductivity probe.

|Part	|Pad / Wire|	MKRZero|	Circuit Diagram |
|-----|-----|------|-----|
|DeadOn RTC	|GND|	GND	|Black|
|TSYS01 Temperature Sensor|	Black|	GND|	Black|
|MS5837 Pressure Sensor|	Black|	GND	|Black|
|EC EZO|	GND|	GND	|Black|
|DeadOn RTC|	VCC|	VCC	|Red|
|TSYS01 Temperature Sensor	|Red|	VCC	|Red|
|MS5837 Pressure Sensor|	Red|	VCC|	Red|
|EC EZO	|VCC	|VCC|	Red|
|DeadOn RTC|	SS|	D7	|Blue|
|DeadOn RTC|	MOSI|	8 (MOSI)|	Yellow|
|DeadOn RTC	|CLK|	9 (SCK)	|Purple|
|DeadOn RTC|	MISO|	10 (MISO)|	Orange|
|TSYS01 Temperature Sensor	|White	11| (SDA)|	White|
|MS5837 Pressure Sensor	|White|	11 (SDA)|	White|
|TSYS01 Temperature Sensor|	Green|	12 (SCL)	|Green|
|MS5837 Pressure Sensor|	Green	|12 (SCL)|	Green|
|EC EZO	|Tx|	13 (Rx)|	Cyan|
|EC EZO|	Rx	|14 (Tx)	|Lime|
|Atlas-Scientific EC K1.0 Probe|	Red	|PRB1 (on EC EZO)	|Conduct RED|
|Atlas-Scientific EC K1.0 Probe|	Black|	PRB2 (on EC EZO)|	Conduct BLK|

![alt text](https://github.com/Teaguey08/CTeagueD/blob/master/circuit%20diagram%20CTD.PNG)

Make sure to use a multimeter at the end to check continuity and especially make sure the VCC and GND are not connected before powering on as they are very close together and this will blow your electronics should it be incorrect.
For the EC EZO circuit I used jumper wires to go into the headers as a pose to soldering into the board so if that’s part breaks it could be replaced.

## 3D Printing
Parts are available online: https://www.thingiverse.com/thing:2567901
Parts Include a protector for the ends of the probes, this attaches to the 3” BlueRobotics face plate that you will pot the sensors through. It protects from knocking and hitting them on bottom of your sampling areas.
There is also an electronics sled complete with mounting points for components, a battery holder for the 1s lipo 1000mah. The batter holder is separate so you can use any batteries you choose, this can be glued onto the back of the sled and the battery held in place with a small tie wrap through the slots provided.
Finally, a sleeve for potting the conductivity probe from the other side so it cannot be pushed through the epoxy base. This is an extra on the potting of the CTDizzle as pressure is being exerted from the outside inwards. An epoxy puck behind will not necessarily keep the conductivity probe from being pushed through, however if there’s epoxy on the other side it will be compressed under pressure making a tighter and tighter fit. The ring is slightly larger than the probe and the inside of the sleeve is a truncated cone. 
Components on electronics sled.

![alt text](https://github.com/Teaguey08/CTeagueD/blob/master/CTD%20JT%20tray%20in%20place.PNG)
![alt text](https://github.com/Teaguey08/CTeagueD/blob/master/CTD%20JT%20tray.PNG)

### Tools
- Hot Glue Gun
- Zip Ties
- Superglue

The sled slots together but will require glue plastic or just super glue, test fir it together first you need the side with the holes to line up with the conductivity probe cradle piece, the other hole is for the temperature and pressure wires.
The components go in their labelled places, the MRK Zero goes with the SD card facing towards the end of the sled and the RCT the battery needs to be facing upwards to allow for replacement. The probe has holes for tie wraps to secure it in place. Hot glue is used to secure the MRK Zero and RCT in place just a dab underneath and the corners should so the trick.
I then super glued the bottom plate of the sled to the bottom flange this will stop it rattling as the aluminium tube (BlueRobotics) is not a consistent diameter internally it has a shoulder.
