---


date: "2016-04-20T00:00:00Z"
draft: false
featured: true
image:
  focal_point: "Left"
  placement: 2
  preview_only: false
lastmod: "2020-01-28T00:00:00Z"
projects: []
subtitle: 'Object detection and tracking using Faster-RCNN and SORT algorithm'
summary: Object detection and tracking using Faster-RCNN and SORT algorithm
tags:
- Academic
title: 'Tracking fish in complex backgrounds using machine learning'
---

After labelling more than thousand images of fish in the videos with complex backgrounds, uneven lighting and bubbles, I trained a faster-RCNN model using the object detection API and then tested the frozen model on video recordings using OpenCV. The results? Pretty solid detection of both fish in most frames of the recording. However, the aerator in the tank and some background objects are also detected on occasion as fish.

{{<figure src="/analysis-tools/fish-tracking/featured1.gif" title="">}}

To identify and track individual fish across frames in the video, I implemented the SORT algorithm (Simple and Online Real-Time Tracking) and modified it to limit the number of possible detected objects to two. The individual trajectories can survive mild occlusions (like the one shown here) using the current algorithm. 

{{<figure src="/analysis-tools/fish-tracking/featured2.gif" title="">}}

From the trajectories, we can visualize space use or exploration in the tank of each fish. We can also measure sociability as the distance between the two fish, the average speed and the similarity of direction of movement of the two fish as an indicator of coordination. Many of these features are available in the movekit repository developed by Eren Cakmak, Arjun Majumdar, and Jolle Jolles at the University of Konstanz.

