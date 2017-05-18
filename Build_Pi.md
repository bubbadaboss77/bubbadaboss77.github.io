# Autonomous RC Car 
## Bates Raspberry Pi Short Term Class 2017
###Total Cost = $150 (includes shipping)


### May 3 2017
This is the first day we have really begun to work on the project. The goal for today was to take apart the RC car we bought and begin to understand how it works. Because some of our parts were still in the mail we spent a good portion of the day reading tutorials and working with OpenCV. By the end of the session our Pi's camerea could recognize faces using OpenCv.
- Tutorial we used for OpenCv [Link](https://pythonprogramming.net/loading-images-python-opencv-tutorial/)


### May 8 2017
Since our last update we have ordered all the parts and successfully taken apart the car. We have taken apart the car so we can control both the motor that turns the front wheels, and the motor that controls forward and reverse.

    (Insert Photo here)
    
Our next goal is to setup our Raspberry Pi to the Bates network. Once that is done we are following this tutotial to control our car using a blue tooth keyboard.

- Tutorial we are using for the seting up the car - [Link](http://www.instructables.com/id/Controlling-a-Raspberry-Pi-RC-Car-With-a-Keyboard/)
- Other Tutorial we are using for setting up the car - [Link](http://www.instructables.com/id/Raspberry-Pi-2-WiFi-RC-Car/)
- Tutorial with helpful diagrams - [Link](http://forums.parallax.com/discussion/156410/how-to-use-a-l298n-dual-h-bridge-with-a-microcontroller-quickstart-board)

Once we took apart the car we started to hookup the L298D chip to the motors and batteries from the car.

    (Insert Photo Here)

As today wraps up our goals are to connect the bluetooth keyboard and the pi to the car. Most of our wires are now set up and good to go. 

Notes: We are being extremely careful to label and track all the screws we are using. Each RC car is different...to do this project we need to be careful with the car and its parts since there is no clear way to take it apart and put it back together. When playing with the batteries be careful with the livewires...if the battery isn't disconnected this could cause a spark'

### May 9, 2017

Today we had a breakthrough. We finally configured all the motors, pi and L298D chip. 

(Insert Photo Here)

Once this was done we set up a python file to run each motor for a set period of time. Using this file we can get the car to run the motors using the pi.

- Tutorial we used for code [link](http://deepaksinghviblog.blogspot.com/2014/08/raspberrypi-to-run-dc-motor-using-l298n.html)
- This tutorial was helpful with the coding but we had to add extra lines for the second motor

The next step is to rebuild the car and set up the sensor.  

Here is a video of Reed running the python file to start each motor. Notice how the motors go in each direction for 3 seconds. 

(Insert Video Here)




### May 10, 2017
We rebuilt the car...this took a lot of troubleshooting and time, therefore we were limited by what we could accomplish today. The car is now ready to drive using our python script. We corrupted our first SD card so...we will need to buy a new one.

GPIO pins (for just the motors):

2(red)
4
6(gray)
8
10
12
14
16
1
3
5
7(purple)
9
11(blue)
13(green)
15(yellow)



###May 11, 2017

Brown-red-red is 330 Ohms

Resistor color code: https://sub.allaboutcircuits.com/images/11066.png

### May 11, 2017

We attached our first sensor to the car. This proved to be extremely challenging because we had to use the bread baord, wires, and resistors.

(Insert some photos)

We are using an HC-SR04 sensor...we are using two main tutorials to hook up the sensor
- The first is [Linkl(https://www.modmypi.com/blog/hc-sr04-ultrasonic-range-sensor-on-the-raspberry-pi)
- The second is [Linkl(https://www.raspberrypi.org/learning/physical-computing-with-python/distance/)


### May 12, 2017 

We got the sensor working today using the code in following link. We disconnected the pi from the L298D chip, so that the sensor was the only thing connected to the pi. Once we got the sensor working, we connected the chip back to the pi and made sure that the sensor and motors were working. 

[Link](http://www.knight-of-pi.org/ultrasonic-range-detection-with-the-raspberry-pi/)

We are now working on combining both our functions to run them through one script. 

### May 15, 2017


Sensor now works while motor is running. However, we encountered some bugs when stopping the program (the wheel was still turning after the program was killed).

In our picar.py file we controlled the car as such.  If object detected using HC-Sr04 sensor within 10cm, the car will reverse.  If object detected within 10-20cm, the car will turn right.  If object detected at a greater than 20cm distance, continue straight.  This worked as anticipated, however we were unable to break out of the while loop.  

To fix this, matt implemented a function which starts/stops the program from running using the keyboard.  We will finalize the object detection tomorrow.  

### May 16 and 17, 2017
May 16th was tough because some of our wires started to melt. We spent most of the day rewiring and trouble shooting

May 17 was a much more successful day. We used the code file test1.py to get the car to run. Using the sensor which is now much more accurate and our newly re-wired motors we were able to get the car to move forward on its on and stop if it detected something infront of the car within 50cm it stops.

[insert video here]

###May 18, 2017:

Installed OpenCV using this installation guide: http://www.pyimagesearch.com/2016/04/18/install-guide-raspberry-pi-3-raspbian-jessie-opencv-3/

Installing OpenCV on Raspberry Pi takes a little over an hour.  We are still waiting for installation to finish.  

While waiting, we mounted the Picamera onto the front of the car 

(insert picture)  

Tomorrow we will use OpenCV and Picamera to recognize a printed stop sign on a wall.  When the car ‘sees’ the sign, the car will stop moving forward.  


