# TCS34725 RGB-Color-Sensor

The TCS3472 sensor provides a digital return of red, green, blue (RGB), and clear light sensing values. An RGB Color sensor helps you accurately detect an object’s colour in your Arduino projects.

----
**TCS34725 board LED**

Use to provide constant illumination. 

The LED pin can be pulled low to turn off the LED. This can be done by:

  1. Wiring directly to ground to turn it off completely.
     
  2. Wiring to a spare digital pin and control it with digitalWrite().



----
# TUTORIAL
----
### HARDWARE

- Arduino UNO
- TCS3472 sensor
----
### WIRING
Reference image [here](https://github.com/kingston-hackSpace/TCS34725_RGB-Color-Sensor/blob/main/WiringDiagram_RGB-Sensor.png)

Arduino UNO|RGB Sensor
-|-
GND | GND
5V | VIN
A4 | SDA
A5 | SCL (I2C Clock signal)

----
### CODE AND INSTRUCTIONS

- Download the corresponding libraries [Adafruit_TCS34725](https://github.com/adafruit/Adafruit_TCS34725)

- Install the libraries via "Importing a .zip Library". Instructions [here](https://docs.arduino.cc/software/ide-v1/tutorials/installing-libraries/)

- Open Arduino IDE and find the sensor examples:
   - File > Examples > Adafruit TCS34725 > tcs34725

- Upload the code to your Arduino board.

- Open Arduino's Serial Monitor to see the incoming data.

----
### UNDERSTANDING THE VALUES

Based on the TCS34725 library, we can use specific functions to read the following parameters:

**1) Color Temperature (measured in Kelvin)**

  Typical range:

      1,500–3,000 K → warm / yellow

      3,000–5,000 K → neutral white

      5,000–7,000 K → cool daylight

      7,000–10,000+ K → very blue-ish light
  
**2) Lux (Lumens per Square Meter)**

*The TCS34725 can read up to about 40k–50k lux before saturating*, depending on settings.

    Typical range:

      0–10 lux → very dark

      10–100 lux → dim indoor light

      100–1,000 lux → normal indoor light

      1,000–10,000 lux → outdoors shade

      10,000–100,000 lux → bright sunlight


  
**3)Clear Light (unfiltered) value**

The TCS34725 measures light using a 16-bit ADC (analogue-to-digital converter).

A 16-bit number can count from:

    - 0 (no light detected)

    - to 65,535 (maximum)

  Typical range:

    0–2,000 → dim or dark

    2,000–10,000 → normal indoor lighting

    10,000–40,000 → bright room or daylight

    40,000+ → very bright / outdoor sun

    65,535 → too bright (saturation)


**4) R, G and B values**

----
### Colour reading TIPS

- Place different objects in front of the sensor to perform colour readings. See reference [here](https://www.youtube.com/watch?v=FQnzRW4XukA&t=5s)
  
- The closer and more centred, the more accurate the colour reading.

- If your object is too far or at an angle, readings may be weak or uneven.

- The TCS34725 LED helps reduce ambient light interference. The LED provides constant and stable illumination. 

----
### MORE TUTORIALS

- [Interfacing a TCS34725 RGB Color Sensor With Arduino – A Complete Guide](https://www.makerguides.com/tcs34725-rgb-color-sensor-with-arduino/)

- [LED lighting based on colour readings](https://learn.adafruit.com/adafruit-color-sensors/arduino-code)
