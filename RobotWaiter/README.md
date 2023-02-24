*****The following description is for the server side program used to create a database,
*****receive robot status via MQTT and send control instructions to control the robot.

(Download mosquitto, MQTT, and sqlite3 first)

1. Change the ADDRESS  in mymqtt.h to your own IP address
2. Compile the app and server programs
3. Open a terminal and enter mosquitto -v to run the mosquitto server
4. Run the server program, connect to the MQTT server, and create a database
5. The client runs the app, enters the table number, menu number, and enters 0 to confirm the order
___________________________________________________

*****The following description is for the robot Arduino code "robot code" which includes mode switching,
*****receiving instructions from PC, sending robot status and tracking.

1. Modify the WIFI SSID and password, and the IP address of the MQTT server.

2. The development environment this program runs in is Arduino Uno.

3. Independent test method:
   1) First, download the mosquito from https://mosquitto.org/.
   2) Run in the installed directory: mosquitto -v to open the server.
   3) Then execute: mosquitto_pub -t "robot" -m "1" to control the robot, go to table 1.
   4) You can also switch to Bluetooth mode by sending the instruction mosquitto_pub -t "robot" -m "B".

4. We can combine MQTT program on PC side with Arduino's program.
   It means the robot will automatically send the status to the PC, then wait for the PC to send control instructions.
