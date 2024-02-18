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

