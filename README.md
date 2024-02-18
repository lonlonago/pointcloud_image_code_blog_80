 Before, many people asked me for the PCL python language PCL installation package for point cloud data processing, but I put it in Baidu Netdisk uniformly, so I didn't reply one by one. 

 Currently only Python 3.6 and 3.7 versions are supported. 

 python_pcl-0.3.0rc1-cp37-cp37m-win_amd64.whl 

 python_pcl -0.3-cp36-cp36m-win_amd64 whl Download address: 

 Link: https://pan.baidu.com/s/1WQQ8kaDilaagjoK5IrYZzA Extraction Code: 1111  



--------------------------------------------------------------------------------

I mainly use the pcap file parsed by dpkt, and then parse the UDP data according to the velodyne protocol. Without further ado, let's go directly to the code. 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574639362
  ```  


--------------------------------------------------------------------------------

I used to use C++ version of the Euclidean distance clustering algorithm, but later when I wrote some Python code, I found that there was no library or other people who had written a Python version of this algorithm, so I had to write one myself. 

 I have used this code in my project and have found no problems so far. 

 Previously, I wrote an article analyzing the Euclidean distance clustering of PCL source code: 

 PCL's European-style distance clustering - Zhihu spent a little time today looking at the relevant algorithms and making a simple note. The clustering code is as follows: from paper_1_v0. my_ransac import my_ransac_v5 import numpy as np img_id = 1 #Read your kitti radar data here path = r'D:\ KITTI\ O... https://zhuanlan.zhihu.com/p/75117664 

 Without further ado, just put in the code: 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574620137
  ```  
 If you have any questions, you can leave a message. I have used this code in the project and have not found any problems so far; 



--------------------------------------------------------------------------------

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


--------------------------------------------------------------------------------

Compared to the data structure of a point cloud, mesh data has triangles that define three-dimensional surfaces.

By default, Open3D attempts to infer the file type by file extension. The following mesh file types are supported:

ply    ;

stl    ;

obj;

off    ;

gltf; 

 ![avatar]( ad89dfdfaf2b405f888dc3130291f5f4.png) 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574694401
  ```  


--------------------------------------------------------------------------------

 The monitoring idea is very simple. It is to use a counter to continuously count the amount of data from the lidar and IMU. If it changes, it means that there has been data coming in. If it stops, it means that there is a problem with the sensor data access. 

 The code is as follows: 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574669253
  ```  


--------------------------------------------------------------------------------

 Rosbag extracts images in compressed format and images in non-compressed format, and only needs to modify the image saving path in the code and the rosbag file path to run; 

 When running, first create a scripts folder under the src directory under the project, then create a new python file to save the following code, such as get_img.py, and finally remember to change the file permissions sudo chmod 777 get_img.py, then run rosrun xxx get_img.py, xxx is your ros project name. 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574699388
  ```  


--------------------------------------------------------------------------------

     A ros program, the original startup mode is rosrun start, need to change to roslaunch start, one advantage of this change is that there is no need to open a separate end point to start roscore, change the way as follows: 

 For example, there is a program, the original start command is to open a separate end point to start roscore, and then open an end point to run rosrun messager talk;  

 In the src level directory, create a new launch folder, create a new xxxx.launch file in the folder, and write the following: 

  <launch> 

   <node pkg="messager" type="talk" name="messager1" output="screen" >    </node> 

  </launch> 

  The name field is not important. 

  You can launch the program through roslaunch messager xxxx.launch; 



--------------------------------------------------------------------------------

I recently encountered a computational geometry problem that requires reconstructing a roughly reasonable geometric shape from a set of points. Find a plane polygon that reflects the contours of these scatter points to a certain extent, and give the connection methods of the edges. For example, reconstruct the shape from the scatter point of the left graph in the figure below to the shape of the right graph: 

 ![avatar]( 18c9abfa9330b7da9c7a27439d1eaf26.png) 

 The versions circulating on the Internet are all convex packages, not concave packages, so I wrote a version of the code myself, which has flaws, but it can basically be used; 

 Idea: randomly take a point as the origin A, calculate the tangent of the connection between point A and the rest of the points in turn, take point A as the origin, divide it into sections with multiple tangent values, and take one of the farthest points in the interval of each tangent as the edge point, and connect the edge points in turn to form a rough concave packet pattern. 

 ![avatar]( bafcf011128faaccdc82bc17ba9ccd7c.png) 

 As shown in the figure above, with point A as the origin, divide its 360 area into 4 areas according to the tangent value, and find the farthest point in each area as the edge point. Here only 4 areas are divided as a schematic diagram, and in fact many areas can be divided, and the effect will be much better. 

 C++ code is as follows: 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574665625
  ```  
 The final renderings are as follows, which is rather satisfactory: 

 ![avatar]( 9f83da1c73c0b3667e0aa4168a5922ba.png) 



--------------------------------------------------------------------------------

WeChat 394467238 

 Using PCL to sample from CAD model (stl, ply format) to obtain point cloud (pcd format) 

 Sampling from multiple perspectives, including only one side of the original CAD model from a certain perspective, is more convenient for registration, because the depth cameras we use generally shoot from one perspective 

 Then finally, the point cloud data from multiple angles are mixed into one, and the complete surface point cloud data of the CAD model can be obtained 

 The effect is as shown in the figure, and the code article is finally released: 

 ![avatar]( 7c156abffe2949bfb2a262211a1bbaf8.png) 

 ![avatar]( 837c1b7820934a5e8a063b15cbc578f7.png) 

 ![avatar]( 78fd4ff6933a42daabd32f5509c67d5e.png) 

 The following code has actually been tested and can be run. If you have any questions, please contact me: 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574684725
  ```  


--------------------------------------------------------------------------------

 By listening to rostopic, analyze and save the three-dimensional data of velodyne lidar, and then save it in txt format; 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574622612
  ```  


--------------------------------------------------------------------------------

Classify the trunk branches and leaves of the scanned tree point cloud, and then release the program code 

 ![avatar]( 38e859a9021445c79911377da641083b.png) 



--------------------------------------------------------------------------------

![avatar]( 5c339d0ed4b64365b978d93b7d016e83.png) 

 These two filters are very useful and must be used well.

Radius filtering:

The radius filter is relatively simple and crude. Draw a circle with a point as the center to calculate the number of points that fall in the circle. When the number is greater than a given value, the point is retained, and if the number is less than a given value, the point is rejected. This algorithm runs fast, and the points left by sequential iterations must be the densest, but the radius of the circle and the number of points in the circle need to be manually specified;

Statistical filtering:

First Scan: For each point, we calculate the average distance from it to all N points in its vicinity. Calculate the mean and standard deviation of these distances

Second scan: Points with an average distance outside the M standard deviations range (defined by the global distance mean and variance) can be defined as outliers and removed from the dataset.

The code is as follows: 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574654444
  ```  


--------------------------------------------------------------------------------

TypeError: can't unbox heterogeneous list: int64 != float64 

 When using numba to accelerate the program, this error may be reported. The general reason is that the elements in a list have multiple data types, such as int and float data at the same time, which will cause this error. 

 Solution: 

 Open the debugging mode, look at the element types in each variable, and change the variable with multiple data types to contain only one data type, which can solve this problem. 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574618423
  ```  
 I report an error here because vis_point_range is [1, 2.0, 3.0], the first element in front is int, and the last two are of type float, so I report an error. If I change it to [1.0, 2.0, 3.0], I will not report an error. 



--------------------------------------------------------------------------------

WeChat 394467238 

 This series of articles will compare different upsampling methods of PCL and explore the differences in the impact of different parameters. 

 And compare the effect of a point cloud sampling method written by myself; 

 All the code will be given in the article, and the code has been run by itself, so you can be sure that there is no problem. 

 The first is PCL's MLS upsampling method, local surface fitting SAMPLE_LOCAL_PLANE 

 The effect is as shown in the picture: 

 ![avatar]( 546380786e2c49bca7f0f85b946252d3.png) 

 The blue point is the point after sampling, and the white point is the original point. It can be seen that the density of the points has increased a lot after sampling, and the increased points are also very evenly distributed. 

 The code is as follows: 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574643176
  ```  
 If//vs version 2019, pcl version 1.9.1//error : // // Unresolvable external symbol LZ4_resetStreamHC//Unresolvable external symbol LZ4_setStreamDecode//Unresolvable external symbol LZ4_decompress_safe_continue//Unresolvable external symbol LZ4_decompress_safe//Unresolvable external symbol LZ4_compress_HC_continue///Resolve: Add flann.lib 

 Add in Project Properties - > Configuration Properties - > Linker - > Input - > Additional Dependencies 



--------------------------------------------------------------------------------

WeChat 394467238 

 This series of articles will compare different upsampling methods of PCL and explore the differences in the impact of different parameters. 

 And compare the effect of a point cloud sampling method written by myself; 

 All the code will be given in the article, and the code has been run by itself, so you can be sure that there is no problem. 

 In this article, I will write my own ideas and code for sampling on a point cloud: 

 Transform a point cloud into an ordered collection of points in three-dimensional space 

 2 Use an image-like method to interpolate three-dimensional ordered points 

 3 Re-convert the three-dimensional ordered points back to the point cloud 

 The code is as follows: 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574681612
  ```  
##  Implementation of upsampling in PCL 

 Decide how to project and upsample based on upsample_method_. 

###  RANDOM_UNIFORM_DENSITY 

 In a range of points, if there are enough points, no resampling is performed. If there are not enough, then randomly add points to the range and project them onto the calculated surface until enough points are reached. 

###  SAMPLE_LOCAL_PLANE 

 This method is more direct, adding points neatly one by one according to a certain step size. 



--------------------------------------------------------------------------------

Red is the true value trajectory, green is the odometer trajectory with deviation, and blue is the optimized trajectory. It can be seen that after the loop is optimized, the blue trajectory has been greatly improved compared with the green trajectory; 

 We used Python's factor graph optimization library g2opy; the specific code is as follows: 

 ![avatar]( 7f1868aa3180475b8525b03032e085ba.png) 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574622859
  ```  


--------------------------------------------------------------------------------

