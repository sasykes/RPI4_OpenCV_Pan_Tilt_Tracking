# RPI4_OpenCV_Pan_Tilt_Tracking
Python code for Tracking Objects using Raspberry  Pi 4 and OpenCV

Raspberry Pi 4 Visual Tracking Using OpenCV and Python3

Main python code here:
https://github.com/sasykes/RPI4_OpenCV_Pan_Tilt_Tracking

Running in virtual environment:

pi@raspberrypi:~ $ cd CodeDir/

pi@raspberrypi:~/CodeDir $ workon cv

$(cv) pi@raspberrypi:~/CodeDir $ sudo pigpiod

(cv) pi@raspberrypi:~/CodeDir $ python3 main.py

Standard practice when working with Python is to create a virtual environment, please search google for installing OpenCV install virtual environment for details, there are a several tutorials on this but I have used this tutorial developed by Adrian Rosebrock: Raspsudo pigpiodbian Stretch: Install OpenCV 3 + Python on your Raspberry Pi (https://www.pyimagesearch.com/2017/09/04/raspbian-stretch-install-opencv-3-python-on-your-raspberry-pi/) you may run into some issues with RPI 4 and the latest version of OpenCV, but these can be solved by searching google for your particular error(s). You do not need to run a VE if you do not want to and is what I started with then changed over to VE after getting object tracking working, in this case follow Will Price's instuctions on his github here - https://gist.github.com/willprice/abe456f5f74aa95d7e0bb81d5a710b60

Once you have OpenCV and python3 installed, you can follow ElectronicHobbyists.com tutorial (https://electronicshobbyists.com/raspberry-pi-pan-tilt-object-tracker-using-opencv/) with working pan code, I am having issues with tilt, it just goes straight back and loses tracking, so I disconnect the data pin for that servo after running "python3 main.py" and only use pan tracking for now. I hope to find a solution to the tilt issue soon, seems to be a code error because there is little that can go wrong with servos, if you find a solution please let me know, as I can control both pan and tilt using console...

Power servo from the Pi, ensure the Pi ground and the servo ground are connected.

To generate servo pulses on any GPIO you may use the following commands...

The examples are for GPIO19 (pin 35) and GPIO26 (pin 37).

start pigpio daemon:

sudo pigpiod

pigs s 19 1000 # counterclockwise
pigs s 19 1500 # centre
pigs s 19 2000 # clockwise

pigs s 26 1000 # counterclockwise
pigs s 26 1500 # centre
pigs s 26 2000 # clockwise

Switch servo pulses off:

pigs s 19 0 
pigs s 26 0
