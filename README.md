# Overview
This repository contains the code that implements the Particle Filter project for the Localization course in Udacity's Self-Driving Car Nanodegree.


## Project Introduction
A robot has been kidnapped and transported to a new location! Luckily it has a map of this location, a (noisy) GPS estimate of its initial location, and lots of (noisy) sensor and control data.

This project implements a 2 dimensional particle filter in C++. The Particle filter is given a map and some initial localization information (analogous to what a GPS would provide). 
At each time step the particle filter gets an observation and a control data. 

## Running the Code
This project uses the Term 2 Simulator which can be downloaded [here](https://github.com/udacity/self-driving-car-sim/releases)

This repository includes two files that can be used to set up and install uWebSocketIO for either Linux or Mac systems. 
For windows you can use either Docker, VMware, or even Windows 10 Bash on Ubuntu to install uWebSocketIO.

Once the install for uWebSocketIO is complete, the main program can be built and ran by doing the following from the project top directory.

mkdir build
cd build
cmake ..
make
./particle_filter

Note that the programs that need to be written to accomplish the project are src/particle_filter.cpp, and particle_filter.h

The program main.cpp has already been filled out, but feel free to modify it.

Here is the main protocol that main.cpp uses for uWebSocketIO in communicating with the simulator.

INPUT: values provided by the simulator to the c++ program

// sense noisy position data from the simulator

1. ["sense_x"] 

2. ["sense_y"] 

3. ["sense_theta"] 

// get the previous velocity and yaw rate to predict the particle's transitioned state

1. ["previous_velocity"]

2. ["previous_yawrate"]

// receive noisy observation data from the simulator, in a respective list of x/y values

1. ["sense_observations_x"] 

2. ["sense_observations_y"] 


OUTPUT: values provided by the c++ program to the simulator

// best particle values used for calculating the error evaluation

1. ["best_particle_x"]

2. ["best_particle_y"]

3. ["best_particle_theta"] 

//Optional message data used for debugging particle's sensing and associations

// for respective (x,y) sensed positions ID label 

1. ["best_particle_associations"]

// for respective (x,y) sensed positions

1. ["best_particle_sense_x"] <= list of sensed x positions

2. ["best_particle_sense_y"] <= list of sensed y positions


The main target of the project is to implement the methods in `particle_filter.cpp` until the simulator output says:

```
Success! Your particle filter passed!
```

# Implementing the Particle Filter
The directory structure of this repository is as follows:

```
root
|   build.sh
|   clean.sh
|   CMakeLists.txt
|   README.md
|   run.sh
|
|___data
|   |   
|   |   map_data.txt
|   
|   
|___src
    |   helper_functions.h
    |   main.cpp
    |   map.h
    |   particle_filter.cpp
    |   particle_filter.h
```


## Inputs to the Particle Filter
The inputs to the particle filter project can be found in the `data` directory. 

#### The Map
`map_data.txt` includes the position of landmarks (in meters) on an arbitrary Cartesian coordinate system. Each row has three columns
1. x position
2. y position
3. landmark id

### All other data the simulator provides, such as observations and controls.

> * Map data provided by 3D Mapping Solutions GmbH.

## Success Criteria

1. **Accuracy**: particle filter successfully localized the vehicle position and yaw to within the values specified in the parameters `max_translation_error` and `max_yaw_error` in `src/main.cpp`.

2. **Performance**: particle filter successfully completed execution within the time of 100 seconds.





