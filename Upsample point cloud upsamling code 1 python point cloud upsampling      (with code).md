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

