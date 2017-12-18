# Reflection

This is a reflection on how to generate paths
-----
The project began with learning of Walkthrough and Q&A, the Started video helped me to get the car moving straight, moving in the lane, and the other function mentioned in the video are also very useful to develop the project. I use the S function to get the help localization data and map the waypoints. For a vehicle lane change, I use the cost function instead of hybrided star to iterately analyze the other vehicles on the road. The lane change opportunities are checked from left lane to right lane.

I designed with three bool variables to check the status to finish a lane change: `too_close`, `right_blocked` and `left_blocked`. The too_close is used to consider lane change, the right_blocked is used to check whether it's availabe in right lane change, so as to left_blocked.
Three conditions are consided in speed control:
- Have Vehicles in front of more than 40 meters
- Have vehicles between 20 meters and 40 meters
- Have vehicles less than 20 meters
The car should run at the speed limit in the first condition, in the second condition the car will run at the same speed of the closest car, and in the third condition, the car should brake the speed to avoid of collision. If the closest car in front of us is too close, we should set the too_close to true and consider whether it is avaiable to perform a lane change, and if the left lane change cost is less than right lane change cost, we will consider to perform a left lane change, otherwise, we will consider to perform a right lane change.

[image1]: ./build/term3-p1.png "EKF"