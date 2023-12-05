# First Journal Entry...

ROS: Robotics Operating System

In my robotics class, we interact with robots that can maneuver and map the 3D space around them. This requires us to interact and talk with the onboard Raspberry Pi and the microcontroller in order to do the tasks that we want the robot to do. 

![Robot](https://github.com/UsabilityEngineering/ux-portfolio-Clemensstrigl/blob/master/assets/IMG_5656.jpg?raw=true)

# In this image we can see the robot on the ground waiting for connection from our latop which is acting as the robot server. At that stage is just finished map the Ocnnel second floor.

For one of our labs, we were tasked with driving the robot around in a loop in the Oconnell and map out the 3D space for autonomous driving in the following labs. When working with ROS, we have to interact with multiple services that they provide in order to make our robot do what we want it to do. 


![Software and robot](https://github.com/UsabilityEngineering/ux-portfolio-Clemensstrigl/blob/master/assets/IMG_5658.jpg?raw=true)

In this image we can see the robot attempting to navigate based on a map that the robot created in the previous image.

This makes getting everything set up **extremely inefficient** because we have to launch four services alone to even be able to talk to the robot. One service is solely used as a server that will connect all other services together, called ROS core. This process is run on the host machine where all the telecommunication will originate from. All it will do is quietly run in the background while the user will interact with all other servers that will have to be run separately in different terminals.

![Config Terminal](https://github.com/UsabilityEngineering/ux-portfolio-Clemensstrigl/blob/master/assets/IMG_5670.jpg?raw=true)

![Multiple terminals](https://github.com/UsabilityEngineering/ux-portfolio-Clemensstrigl/blob/master/assets/IMG_5667.jpg?raw=true)

![Launch Terminal](https://github.com/UsabilityEngineering/ux-portfolio-Clemensstrigl/blob/master/assets/IMG_5673.jpg?raw=true)

On the robot itself, one has to start the ROS client-side service that allows the robot to talk to the server and our personal laptop and receive and send data. Here, we have to take multiple steps before everything will work correctly by configuring the correct IP address from both the robot and the host machine in both machines' configuration files. This dramatically reduces down on the **error tolerance** of the program since the IP address can change every time a device connects and/or reconnects. Error tolerance entails that the program knows what to do if it encounters any issues or wrong inputs from servers or users. In my case ros would have to be able to better handle incorrect ip adresses by looping through the list of available ip addresses pinging devices if they are either the robot or the robot server. A nother solution which might be a bit less work would be by making all IP addresses static, but in our case, there are hundreds of people logging in and out of the network, so there have to be enough available addresses for everyone. 

Another massive unconventional design in the software is the actual driving. To maneuver the robot, you would use AWSD and X to move the robot in all directions and S to stop it all together. In almost all applications that employ the AWSD movability model, if no key is pressed, no movement will be detected, but if a button is pressed, then its 100% movement. With the robot, it is vastly different. Instead of the buttons controlling the position of the robot, it controls the velocity. Each button press increases or decreases the velocity, meaning that in order to get back down to 0 velocities, one would either have to entirely stop the robot or hope that the velocity step size is accurate enough to bring one back to 0. 

Finally, the robot does not have a camera installed, forcing us to have to walk around with the robot in order for us to see where the robot is going accurately. In our case, we thankfully had a laptop, which made all that possible. Still, even other groups that did not have one were forced to use a desktop, which made remote telecommunications extremely hard to do precisely. 

