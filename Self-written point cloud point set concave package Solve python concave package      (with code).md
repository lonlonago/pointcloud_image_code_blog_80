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

