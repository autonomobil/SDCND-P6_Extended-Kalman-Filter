[//]: # (Image References)

[img1]: ./images/finished.png "finished.png"
[img2]: ./output_images/example_images2.png "example_images2.png"
[img3]: ./output_images/hog_car1.png "hog_car1.png"
[img4]: ./output_images/hog_car2.png "hog_car2.png"

---
# SDCND Term 2 Project 6: Extended Kalman Filter
## Project for Udacity Self-Driving Car Engineer Nanodegree Program

In this project we will utilize a kalman filter to estimate the state of a moving object of interest with noisy lidar and radar measurements.

![img1]

Follow these steps for Windows setup:

* Follow these the [instructions](https://www.howtogeek.com/249966/how-to-install-and-use-the-linux-bash-shell-on-windows-10/) for setting up Ubuntu BASH.
* Download Windows simulator [here](https://github.com/udacity/self-driving-car-sim/releases).
* Open Ubuntu Bash
* ``sudo apt-get update``
* ``sudo apt-get install git``
* ``sudo apt-get install cmake``
* ``sudo apt-get install openssl``
* ``sudo apt-get install libssl-dev``
* ``git clone https://github.com/autonomobil/SDCND-P6_Extended-Kalman-Filter``
* ``sudo rm /usr/lib/libuWS.so``
* navigate | cd to ``SDCND-P6_Extended-Kalman-Filter/``
* ``./install-ubuntu.sh``
* ``mkdir build && cd build``
* ``cmake .. && make``
* Launch the ``term2_sim.exe`` from Windows simulator
* Execute ``./ExtendedKF``
* If you see ``Listening to port 4567 Connected!!!``, it is working
* Press ``Start``

These files were modified compared to the [original repository](https://github.com/udacity/CarND-Extended-Kalman-Filter-Project):  
* src/FusionEKF.cpp
* src/kalman_filter.cpp
* src/tools.cpp

INPUT: values provided by the simulator to the c++ program

["sensor_measurement"] => the measurement that the simulator observed (either lidar or radar)


OUTPUT: values provided by the c++ program to the simulator

["estimate_x"] <= kalman filter estimated position x
["estimate_y"] <= kalman filter estimated position y
["rmse_x"]
["rmse_y"]
["rmse_vx"]
["rmse_vy"]

---
