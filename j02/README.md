# Second Journal Entry...

ROS: Robotics Operating System

In my robotics class, we interact with robots that can maneuver and map the 3D space around them. This requires us to interact and talk with the onboard Raspberry Pi and the microcontroller in order to do the tasks that we want the Robot to do. 

![Robot](https://github.com/UsabilityEngineering/ux-portfolio-Clemensstrigl/blob/master/assets/IMG_5656.jpg?raw=true) 

<code style="color:gray;"> In this image, we can see the Robot on the ground waiting for connection from our laptop, which is acting as the robot server. Here, we are about to start navigation using the map displayed on the screen.</code>



For one of our labs, we were tasked with driving the Robot around in a loop in the Oconnell and mapping out the 3D space for autonomous driving in the following labs. When working with ROS, we have to interact with multiple services they provide to make our Robot do what we want it to do.


![Software and robot](https://github.com/UsabilityEngineering/ux-portfolio-Clemensstrigl/blob/master/assets/IMG_5658.jpg?raw=true)

<code style="color:gray;">In this image, we can see the Robot attempting to navigate based on a map that the Robot created in the previous image.</code>

This makes getting everything set up **extremely inefficient** because we have to launch four services alone to even be able to talk to the Robot. One service, called ROS core, is solely used as a server that will connect all other services together. This process is run on the host machine where all the telecommunication will originate from. All it will do is quietly run in the background while the user will interact with all other servers running separately in different terminals.

![Config Terminal](https://github.com/UsabilityEngineering/ux-portfolio-Clemensstrigl/blob/master/assets/IMG_5670.jpg?raw=true)

<code style="color:gray;">In this image, we can see the configuration values of the Robot for navigation. Here, the UI could be drastically improved to make everything more legible and allow easier edits of the actual values.</code>

![Multiple terminals](https://github.com/UsabilityEngineering/ux-portfolio-Clemensstrigl/blob/master/assets/IMG_5667.jpg?raw=true)

<code style="color:gray;">In this image, we can see the Robot attempting to navigate through the map, but it has somehow found itself within the map section that is not drivable and defined. Here, the program lacks the ability within the UI to readjust the map. We had to completely restart all navigation and hope that that issue does not occur again. No tools are available for such a correction.</code>

![Launch Terminal](https://github.com/UsabilityEngineering/ux-portfolio-Clemensstrigl/blob/master/assets/IMG_5673.jpg?raw=true)

<code style="color:gray;">In this final image, we can see the error codes coming in from the Robot, but status updates come in extremely frequently, flushing out the error codes almost immediately. If there were some better UI text box that only parses out the error codes, which would drastically assist the robot operator and supervisor with any issues the Robot encountered.</code>

On the Robot itself, one has to start the ROS client-side service that allows it to talk to the server and our personal laptop and receive and send data. Here, we have to take multiple steps before everything works correctly by configuring the correct IP address from both the Robot and the host machine in both configuration files. This dramatically reduces the **error tolerance** of the program since the IP address can change every time a device connects and/or reconnects. Error tolerance entails the program knowing what to do if it encounters any issues or wrong inputs from servers or users. In my case, ros would have to be able to better handle incorrect IP addresses by looping through the list of available IP addresses pinging devices if they are either the Robot or the robot server. Another solution that could be less work is making all IP addresses static, but in our case, hundreds of people are logging in and out of the network, so there must be enough available addresses for everyone. 

Another massive unconventional design in the software is the actual driving. To maneuver the Robot, you would use AWSD and X to move it in all directions and S to stop it altogether. In almost all applications that employ the AWSD movability model, no movement will be detected if no key is pressed, but if a button is pressed, then it is 100% movement. With the Robot, it is vastly different. Instead of the buttons controlling the Robot's position, it controls the velocity. Each button press increases or decreases the velocity, meaning that to get back down to 0 velocities, one would either have to entirely stop the Robot or hope that the velocity step size is accurate enough to bring one back to 0. 

Finally, the Robot does not have a camera installed, forcing us to have to walk around with the Robot for us to see where it is going accurately. In our case, we thankfully had a laptop, which made all that possible. Still, even other groups that did not have one were forced to use a desktop, which made remote telecommunications extremely hard to do precisely. 

