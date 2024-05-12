# MobileRobot-Openloopcontrol
## Aim:

To develop a python control code to move the mobilerobot along the predefined path.

## Equipments Required:
1. RoboMaster EP core
2. Python 3.7

## Procedure

### 1. Import Necessary Libraries:
Import the robot, time, and camera modules from the robomaster library to interact with the robot's components.

### 2. Initialize the Robot:
Create an instance of the robot.Robot() class to represent the robot. Initialize the robot's connection using ep_robot.initialize(conn_type="ap").

### 3. Access Robot Components:
Create objects for the robot's chassis, LEDs, and camera: ep_chassis = ep_robot.chassis ep_led = ep_robot.led ep_camera = ep_robot.camera

### 4. Perform Actions:
Start video stream: Start streaming video from the robot's camera using ep_camera.start_video_stream(display=True, resolution=camera.STREAM_360P).

Move and change LEDs:
Execute a series of movements in a pre-defined pattern using ep_chassis.move(). Simultaneously change LED colors using ep_led.set_led() to create visual effects.

Stop video stream:
After a delay of 4 seconds, stop the video stream using ep_camera.stop_video_stream().

### 5. Close the Connection:
Terminate the connection to the robot using ep_robot.close().

## Program
```python

# Developed By  : SANJAY M
# Register No  : 212223230187

from robomaster import robot
import time
from robomaster import camera

if _name_ == '_main_':
    ep_robot = robot.Robot()
    ep_robot.initialize(conn_type="ap")

    ep_chassis = ep_robot.chassis
    ep_led = ep_robot.led
    ep_camera = ep_robot.camera

    print("Video streaming started.....")
    ep_camera.start_video_stream(display=True, resolution = camera.STREAM_360P)

    ep_chassis.move(x=2.5, y=0, z=0, xy_speed=1).wait_for_completed()
    ep_led.set_led(comp = "all",r=0,g=0,b=0,effect="on")

    ep_chassis.move(x=0.5, y=0, z=80, xy_speed=1).wait_for_completed()
    ep_led.set_led(comp = "all",r=0,g=255,b=255,effect="on")

    ep_chassis.move(x=1, y=0, z=0, xy_speed=1).wait_for_completed()
    ep_led.set_led(comp = "all",r=128,g=0,b=0,effect="on")

    ep_chassis.move(x=0, y=-1.7, z=0, xy_speed=1).wait_for_completed()
    ep_led.set_led(comp = "all",r=204,g=255,b=255,effect="on")

    ep_chassis.move(x=0, y=0, z=50, xy_speed=1).wait_for_completed()
    ep_led.set_led(comp = "all",r=102,g=0,b=102,effect="on")

    ep_chassis.move(x=1.4, y=0, z=0, xy_speed=1).wait_for_completed()
    ep_led.set_led(comp = "all",r=204,g=204,b=255,effect="on")

    ep_chassis.move(x=0, y=0, z=55, xy_speed=1).wait_for_completed()
    ep_led.set_led(comp = "all",r=153,g=153,b=255,effect="on")

    ep_chassis.move(x=1.5, y=0, z=0, xy_speed=1).wait_for_completed()
    ep_led.set_led(comp = "all",r=153,g=51,b=102,effect="on")
    
    ep_chassis.move(x=0, y=-2.15, z=0, xy_speed=1).wait_for_completed()
    ep_led.set_led(comp = "all",r=0,g=102,b=204,effect="on")

    ep_chassis.move(x=0, y=0, z=175, xy_speed=1).wait_for_completed()
    ep_led.set_led(comp = "all",r=0,g=0,b=102,effect="on")

    ep_chassis.move(x=0.6, y=0, z=0, xy_speed=1).wait_for_completed()
    ep_led.set_led(comp = "all",r=0,g=128,b=128,effect="on")
    
    ep_chassis.move(x=0, y=0, z=0, xy_speed=1).wait_for_completed()
    ep_led.set_led(comp = "all",r=255,g=100,b=0,effect="on")


    time.sleep(4)
    ep_camera.stop_video_stream()
    print("Stopped video streaming.....")

    ep_robot.close()
```

## MobileRobot Movement Image:

![robo](./img/robomaster.png)

![alt text](<Screenshot 2024-05-12 091316.png>)
![alt text](<Screenshot 2024-05-12 091345.png>)
![alt text](<Screenshot 2024-05-12 091359.png>)


## MobileRobot Movement Video:

## url:https://youtu.be/mR6rekA3uik

## Result:
Thus the python program code is developed to move the mobilerobot in the predefined path.

```
Mobile Robotics Laboratory
SANJAY M - 212223230187
Department of Artificial Intelligence and Data Science
Saveetha Engineering College
```
