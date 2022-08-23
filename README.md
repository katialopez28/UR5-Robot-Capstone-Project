# UR5-Robot-Capstone-Project
The Human Assistance For Robot Arm (HAFRA) project consists of a Universal Robot, specifically the UR5, an Intel RealSense depth camera, and software programs. 

Team Members: Katia Lopez, Richard Tran, Cesar Rea, Resha Adhikari, Nishan Pathak
Professor: Christopher McMurrough

The purpose of the application is for the robot to picks up envelopes from a conveyor belt and place them into a bin. Industries will be able to use this robot in product lines to perform packaging or other tasks. The project includes human assistance that oversees and fixes any mistakes the robot has made remotely. This allows the robot to have a success rate of close to 100%. This solution increases overall productivity and ultimately reduces any errors or mistakes. The computer vision program detects an AruCo tag and calculates the center pixel coordinate of the tag. Then, it converts the pixel coordinate to a real world (x,y) coordinate and sends it to the 
movement program. The movement program moves the robot to the given pickup position, then to the drop-off position, and back to the start position to be ready to pick up the next envelope. In addition, if the vision program is not able to detect an AruCo tag, it sends an image to the human assistance portion of the program. This allows a human to enter a pixel coordinate which is converted to a real world (x,y) coordinate and passed to the movement program so the robot can continue operating as normal.


This GitHub contains the two main python files of the application. The vision program helps the robot have a view of the world, and the movement program moves the robot and also activates the vacuum that is used by the suction gripper to pick up the envelopes.

"vision.py" contains the functionality for turning on the camera, capturing an image and placing it into a variable, then using this image to detect arUco markers. Depending on whether a marker is detected in the image, then human assitance will also be done here. Either way, coordinates will be sent from this file to the movement program.

"movement.py" contains the functionality for moving to start, pickup, and dropoff state. Vacuums are turned off and on at specific points of the movement as well. The pickup state is dependent on the coordinates received from vision.py.

Further research is required on the following:
* Universal Robot ROS Drivers GitHub (https://github.com/UniversalRobots/Universal_Robots_ROS_Driver)
* rospy communication (nodes, subscribers, listeners, talkers, etc.)
* ArUco GitHub (https://github.com/GSNCodes/ArUCo-Markers-Pose-Estimation-Generation-Python) (https://stackoverflow.com/questions/64700551/rgb-image-captured-by-intel-realsense-camera-is-dark-using-python-code)
* Setting up local network with the UR5 Touch Pendant
* librealsense (https://github.com/IntelRealSense/librealsense/blob/master/doc/installation.md) (https://www.mouser.com/applications/getting-started-with-realsense-d455/)
