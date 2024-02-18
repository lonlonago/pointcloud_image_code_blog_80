     A ros program, the original startup mode is rosrun start, need to change to roslaunch start, one advantage of this change is that there is no need to open a separate end point to start roscore, change the way as follows: 

 For example, there is a program, the original start command is to open a separate end point to start roscore, and then open an end point to run rosrun messager talk;  

 In the src level directory, create a new launch folder, create a new xxxx.launch file in the folder, and write the following: 

  <launch> 

   <node pkg="messager" type="talk" name="messager1" output="screen" >    </node> 

  </launch> 

  The name field is not important. 

  You can launch the program through roslaunch messager xxxx.launch; 

