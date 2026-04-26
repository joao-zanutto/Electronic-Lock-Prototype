


https://github.com/joao-zanutto/Fechadura-Eletrica-WiFi/assets/11475695/eda2953e-1172-402a-984b-237fb1f6270f


# Electronic Lock Prototype
System architecturd with the ESP32 development board for the Electronics class that is part of the Bachelor's in CS program at University of São Paulo (USP).

## The project:

The project was designed with the objective of building a working prototype for a Smart Electronic Lock that could be remotelly activated. To achieve this I've chosed to host a web server directly in the development board, making the project extremelly simple, but prone to vulnerabilities as no security mechanisms were addressed during the project development.

## The setup:
1- ESP32 development board\
1- Relay module\
1- PP Cable 10 meters\
1- AC adaptar\
Some Jumpers

The circuit works in a very simple way, connecting the relay module to the ESP32 board in 3 different pins:\
ESP-32 | Relay Module\
3V3====| VCC\
GND====| GND\
GPIO4==| IN

Also, the positive wire from the AC source must be connected to the relay common, and the negative should be connected directly to the black wire on the PP cable. The red wire from the PP cable was plugged to the relay connector that is usually closed, and both remaining extremities connected to their correspondent poles in the commercial HDL electronic lock.

## The Code:

The code is all embedded in the ESP32 board and is extremelly simple. It'll first connect to a pre-defined WiFi network, print its IP to the connected workstation via serial monitor, and then will open up a local web server and wait for requests. Whenever a request comes in to the board IP, it'll serve a page with a single button labeled "Abrir" (Open). Whenever the button is pressed by the user, it should trigger a new requisiton to the board that will end up activating the relay module, which will open the lock, and then disarm the relay after 1 second.

https://drive.google.com/open?id=1Kkgbdy1Nei6g84ACyjCBLXT5Bhxe0Kb0
