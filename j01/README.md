# First Journal Entry...

ROS: Robotics Operating System

In my robotics class, we are interacting with robots that are able to manuver and map the 3D space around them. This requires us to interact and talk with the onboard Raspberry Pi and the micro controlers in order to do the tasks that we want the robot to do. 

![Robot](https://github.com/UsabilityEngineering/ux-portfolio-Clemensstrigl/blob/master/assets/IMG_5656.jpg?raw=true)

For one of our labs we were tasked with driving the robot around in a loop in the Oconnell and map out the 3d space for autonomus driving in the next labs. When working with ROS, we have to interact with multiple services that they provide in order to make our robot do what we want it to do. This makes getting everything set up **extremely inefficient** because we have to launch 4 services alone in order to even be able to talk to the robot. One service is soley used as a server that will connect all other services together called ROS core. This process is run on the host machine where all the telecommunication will originate from. All it will do is quietly run in the background while the user will interact with all other serves that will have to be run seperately in different terminals. On the robot it self, one has to start the ROS client side service so that allows the robot to talk to ther server, our personal laptop, recieve and send data. Here we have to take multiple steps before everything will work correctly by configuring the correct IP address from both the robot and the host machine in both machines configuration files. This greatly reduces down on the **error tollerence** of the program since IP address can change every time a device connects and/or reconnects 


![Software and robot](https://github.com/UsabilityEngineering/ux-portfolio-Clemensstrigl/blob/master/assets/IMG_5658.jpg?raw=true)
