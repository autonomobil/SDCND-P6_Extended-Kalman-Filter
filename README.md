[//]: # (Image References)

[img1]: ./images/finished.png "finished.png"
[img2]: ./images/finished_dataset2.png "dataset2.png"

---
# SDCND Term 2 Project 6: Extended Kalman Filter
## Project for Udacity Self-Driving Car Engineer Nanodegree Program
[![Udacity - Self-Driving Car NanoDegree](https://s3.amazonaws.com/udacity-sdc/github/shield-carnd.svg)](http://www.udacity.com/drive)

In this project we will utilize a kalman filter to estimate the state of a moving object of interest with noisy lidar and radar measurements.

This project includes  the implementation of an Extended Kalman filter with C++. A Udacity-provided simulator (available for download [here](https://github.com/udacity/self-driving-car-sim/releases) generates noisy RADAR and LIDAR measurements of an object's position and speed, and the Extended Kalman Filter [EKF] must merge these measurements to predict the object's position. Communication between the simulator and the EKF takes place via [uWebSocket](https://github.com/uNetworking/uWebSockets).

Udacity's project basis can be found [here](https://github.com/udacity/CarND-Extended-Kalman-Filter-Project).


![img1]

## Dependencies

* cmake >= 3.5
* make >= 4.1
* gcc/g++ >= 5.4
* Udacity's simulator

For instructions on how to install these components on different operating systems, visit [Udacity's project](https://github.com/udacity/CarND-Extended-Kalman-Filter-Project).


## Setup and Running
Follow these suggested steps for Windows setup:

* Follow these the [instructions](https://www.howtogeek.com/249966/how-to-install-and-use-the-linux-bash-shell-on-windows-10/) for setting up Ubuntu BASH.
* Download Windows simulator [here](https://github.com/udacity/self-driving-car-sim/releases).
* Open Ubuntu Bash (write all following commands to Ubuntu Bash command window)
* ``sudo apt-get update``
* ``sudo apt-get install git``
* ``sudo apt-get install cmake``
* ``sudo apt-get install gcc``
* ``sudo apt-get install g++``
* ``sudo apt-get install openssl``
* ``sudo apt-get install libssl-dev``
* navigate to where you want to clone this repository to, for example:
 ``cd /mnt/c/Users/"Bob"``
* ``git clone https://github.com/autonomobil/SDCND-P6_Extended-Kalman-Filter``
* ``sudo rm /usr/lib/libuWS.so``
* navigate to project folder: ``cd ./SCDND-P6_ExtendedKalmanFilter``
* ``./install-ubuntu.sh``
* ``mkdir build && cd build``
* ``cmake .. && make``
* Launch the **term2_sim.exe** from Windows simulator folder
* Execute ``./ExtendedKF``
* If you see ``Listening to port 4567 Connected!!!``, it is working
* Press **Start**

These files were modified compared to the [original repository](https://github.com/udacity/CarND-Extended-Kalman-Filter-Project):  
* src/FusionEKF.cpp
* src/kalman_filter.cpp
* src/tools.cpp

---

## Checking Rubric points
#### Your code should compile.
* The code compiles without errors on my setup following the instructions above.

#### px, py, vx, vy output coordinates must have an RMSE <= [.11, .11, 0.52, 0.52] when using the file: "obj_pose-laser-radar-synthetic-input.txt" which is the same data file the simulator uses for Dataset 1.
* Dataset 1 RMSE : [0.0964, 0.0853, 0.4154, 0.4316]
* Dataset 2 RMSE : [0.0727, 0.0966, 0.4400, 0.4755]

![img2]

#### Your Sensor Fusion algorithm follows the general processing flow as taught in the preceding lessons
* Sensor Fusion takes place at [./src/FusionEKF.cpp](./src/FusionEKF.cpp)
* [./src/FusionEKF.cpp](./src/FusionEKF.cpp) uses ``Predict``, ``Update`` and ``UpdateEKF`` from [./src/kalman_filter.cpp](./src/kalman_filter.cpp) kalman_filter.cpp

#### Your Kalman Filter algorithm handles the first measurements appropriately
* First measurement is handled in lines 54 - 101 [./src/FusionEKF.cpp](./src/FusionEKF.cpp)


#### Your Kalman Filter algorithm first predicts then updates
* Prediction: Lines 103 - 131 [./src/FusionEKF.cpp](./src/FusionEKF.cpp); using [./src/kalman_filter.cpp](./src/kalman_filter.cpp)
* Update: Lines 132 - 150 [./src/FusionEKF.cpp](./src/FusionEKF.cpp); using [./src/kalman_filter.cpp](./src/kalman_filter.cpp)

#### Your Kalman Filter can handle radar and lidar measurements
* In [./src/FusionEKF.cpp](./src/FusionEKF.cpp) if-statements decide how to initialize and process the data given the sensor type
