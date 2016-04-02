# open-dobot-gui
GUI Application to control a Dobot robotic arm via an Arduino Mega 2560 and a RAMPS 1.4 board. 

Inverse Kinematics Implemented! I will write up more about this some other time. There's a link in the code to a youtube video that explains most of it.

100% open source hardware and software

MIT License

NOTE: This repository is literally just getting started. As such, the application is not quite yet ready for those who don't know how to code or as a standalone release. It's fairly close though. The major value of this software is the inverse kinematics functions at the moment.

Videos:

[Set up and move to point demo](https://youtu.be/FjHylzeWPgg)

[Inverse Kinematics Quick Explanation](https://youtu.be/Nsgcq8Uz_Vc)

[Inverse Kinematics C++ 3D simulation Demo](https://youtu.be/5oExIlkn5EA)


The gui app is written in python and uses pyqt. It is not yet completely functional, but works enough for testing purposes (if you know how to code). Most of the remaining work on it is fairly easy to do, just takes time, which I am a bit short on due to school. Most updates will probably happen on weekends. Also included in this repository is a c++ qt project which performs a 3d simulation of the inverse kinematics, which is useful in verifying that the inverse kinematics are correctly implemented. Currently, I'm having trouble defining the work area limits. I need to do that somehow. The lower arm angle limits is what's tripping me up. The inverse kinematics on the robot itself seems to work. Just be careful about transforming angles to the correct orientation. I might have messed that up a bit. If I did, it's subtle. 

IMPORTANT: For everything to work properly, before you send move commands, you need to position the upper arm completely vertical (defined as 90 degrees) and the lower arm completely horizontal (defined as 0 degrees). Doesn't matter where the base is. Wherever it starts is defined as 0.

![ScreenShot](https://raw.githubusercontent.com/mikef522/open-dobot-gui/master/opendobotgui1.PNG)
![ScreenShot](https://raw.githubusercontent.com/mikef522/open-dobot-gui/master/inversekinematicssimulationc%2B%2Bqt.PNG)
![ScreenShot](https://raw.githubusercontent.com/mikef522/open-dobot-gui/master/opendobotgui2.PNG)

TO DO:

-Need a way to check that connection to a port is proper, i.e. when it sends commands it's using the right firmware. Right now, I can connect to other arduinos without the correct firmware or even any old random open port. Sending commands to these ports causes errors and the application to crash.

-Need to prevent user from being able to send commands when serial port not connected

-Verify inverse kinematics and fix any problems

-A way to "teach" the robot (i.e. save a sequence of moves/actions)

-support for standard effectors included with the dobot (very low priority for me (Mike), may not get done since I don't have enough time in the day)

-Greatly improve the serial communication protocol. I just used the quickest method I could find that works so I could get testing the inverse kinematics.

-Get angles from IMUs

-3D print IMU holder

-3D print endstop holder and connect end stops

-Implement emergency stop function in GUI

-implement incrememntal move functions

-much more, too lazy to list it all

