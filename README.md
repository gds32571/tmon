#tmon

A program to monitor MQTT publications

shows:

topic

how much time has elapsed since last transmission,

the largest gap between successive transmissions

how many 1 minute periods the sensor has not responded after 120 seconds

It subscribes to the Home Assistant sensors associated with the RTL SDR output. Those individual sensor values have data collected on the timing of their transmissions.

The program displays how long it has been since that topic was received, the longest period of time it has ever taken to be received, and finally, the number of 1 minute periods past the maximum that it has been missing.

This allows you to see if any of your Acurite sensors are flaky or are having trouble.

Added runtime to screen output.

Program now also subscribes to admin topic tmon/dump. If you send MQTT message to this topic, tmon will dump currently recorded data to a disk file, and keep running. Filename will be some permutation of the main topic and the date and time.
Example: for main topic rtl433/# you get filename rtl433-#-20190701-110442.dat
