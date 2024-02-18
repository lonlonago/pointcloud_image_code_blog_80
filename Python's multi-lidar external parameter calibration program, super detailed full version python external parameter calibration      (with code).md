After consulting some information and existing code, I found that the calibration procedures between the current multiple lidars are all under the ROS framework, and they are all C++ code. The dependencies that need to be installed are also more complicated, so I wrote a python version of the calibration program. The dependency is very simple, and the Windows system can also run. And the code is simple and scalable. It is also very convenient to expand if you want to calibrate more than 2 radars at the same time in the future; 

 It can solve the above three problems: 

 The calibration process is as follows: 

#  Adjust the point cloud pose with the following buttons: 

#  Q, a yaw adjustment 

#  W, s roll roll angle adjustment 

#  E, d pitch adjustment 

#  R, f X axis adjustment 

#  T, g Y axis adjustment 

#  Y, h Z axis adjustment 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574661980
  ```  
