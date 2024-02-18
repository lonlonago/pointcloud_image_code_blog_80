TypeError: can't unbox heterogeneous list: int64 != float64 

 When using numba to accelerate the program, this error may be reported. The general reason is that the elements in a list have multiple data types, such as int and float data at the same time, which will cause this error. 

 Solution: 

 Open the debugging mode, look at the element types in each variable, and change the variable with multiple data types to contain only one data type, which can solve this problem. 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574618423
  ```  
 I report an error here because vis_point_range is [1, 2.0, 3.0], the first element in front is int, and the last two are of type float, so I report an error. If I change it to [1.0, 2.0, 3.0], I will not report an error. 

