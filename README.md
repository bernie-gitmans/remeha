# Remeha Boiler connectivity using ESP8266
Connect ESP8266 directly to Remeha CV/Boiler to read data using PHP.

The current PHP code uses an Adafruit Huzzah ESP8266 to connect to and read data from a Remeha Tzerra boiler. The Huzzah ESP8266 was chosen as it is a 5VDC device and does not require any level shifter or additional circuits to deal with the higher voltage. It connect to the Remeha X13 connector using a 4P4C (RJ10) connector with the following pinouts:

1. Remeha............>ESP8266
2. Pin1 (GND)........>GND
3. Pin2 (RX).........>TX
4. Pin3 (TX).........>RX
5. Pin4 (VDC)........>VCC+

The ESP8266 is running and has been tested with the ESP-Link firmware/software loaded (also on GitHub)

Currently this is a 'read only' script and provides the following functionality:

1. Connects ESP to Tzerra
2. Sends Hex to Tzerra and reads the responses (for "Sample Data", "Counter Data" and "Parameters")
3. Maps response to more 'logical' variables
4. Translates various 'bits' to provide correct messages
5. Writes information received to Domoticz server using cURL
6. The remeha-tzerra-xxxxx.php scripts can be run from within a browser, while the remeha-tzerra.php script is best run as a daemon or in the background

To do:

1. clean up code
2. find corrert timing for the remeha-tzerra.php script so there are less checksum errors.

