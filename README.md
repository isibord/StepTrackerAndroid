# StepTrackerAndroid
Basic Step Tracking using Android Accelerometer

## Overview
My step tracker app uses the Android accelerometer signal to detect when user takes a step using a basic peak detection algorithm. It comprises of two views. The main view [see Fig 1] that shows the user the progress on how many steps they’ve taken based on a pre-set goal of 500 steps. The second view is the debug view [see Fig 2] which shows the number of steps calculated by my algorithm, the number of steps by Android’s step counter, a plot of the raw magnitude of the accelerator values and finally, the smoothed net magnitude of the accelerator signal used for calculating the number of steps.
To use the app, hold the phone in a portrait orientation and walk. You’ll observe the step count progressions. Pause walking to observe the discontinuation of step counting. 

## Signal Processing Approach
My algorithm using signal processing of Android’s accelerometer comprises of the following steps:
1.	Calculate raw magnitude of accelerometer signal
2.	Smooth signal using running average with window size of 20
3.	To exclude gravity from magnitude value, net magnitude is calculated by subtracting average magnitude
4.	Derived from Mladenov et al [1]’s paper, peak detection is used for step count. Peak threshold calculated by prior average of step peak values, plus additional high noise threshold value were selected to prime algorithm.

## Feedback Interface
The feedback interface as shown in Fig 1, has two main components, the incremental step count value as well as the visualization of progress with respect to a goal using a circular progress bar.
The design rationale behind this interface were primarily – goal setting and progress representation using the rotating scale and color. This is intended to create user awareness of their personal physical activity relative to the average. 500 step goal was chosen for illustration purposes only. Lastly, when user has reached their goal, they get a congratulatory message to reinforce their success [see Fig 3].


![Fig1](https://github.com/isibord/StepTrackerAndroid/blob/master/blob/Fig1.PNG)

![Fig2](https://github.com/isibord/StepTrackerAndroid/blob/master/blob/Fig2.png)

![Fig3](https://github.com/isibord/StepTrackerAndroid/blob/master/blob/Fig3.png)
