# cs7785-lab-2-solved
**TO GET THIS SOLUTION VISIT:** [CS7785 Lab 2 Solved](https://www.ankitcodinghub.com/product/cs7785-cs-me-ece-ae-bme7785-solved-2/)


---

📩 **If you need this solution or have special requests:** **Email:** ankitcoding@gmail.com  
📱 **WhatsApp:** +1 419 877 7882  
📄 **Get a quote instantly using this form:** [Ask Homework Questions](https://www.ankitcodinghub.com/services/ask-homework-questions/)

*We deliver fast, professional, and affordable academic help.*

---

<h2>Description</h2>



<div class="kk-star-ratings kksr-auto kksr-align-center kksr-valign-top" data-payload="{&quot;align&quot;:&quot;center&quot;,&quot;id&quot;:&quot;115216&quot;,&quot;slug&quot;:&quot;default&quot;,&quot;valign&quot;:&quot;top&quot;,&quot;ignore&quot;:&quot;&quot;,&quot;reference&quot;:&quot;auto&quot;,&quot;class&quot;:&quot;&quot;,&quot;count&quot;:&quot;2&quot;,&quot;legendonly&quot;:&quot;&quot;,&quot;readonly&quot;:&quot;&quot;,&quot;score&quot;:&quot;5&quot;,&quot;starsonly&quot;:&quot;&quot;,&quot;best&quot;:&quot;5&quot;,&quot;gap&quot;:&quot;4&quot;,&quot;greet&quot;:&quot;Rate this product&quot;,&quot;legend&quot;:&quot;5\/5 - (2 votes)&quot;,&quot;size&quot;:&quot;24&quot;,&quot;title&quot;:&quot;CS7785 Lab 2 Solved&quot;,&quot;width&quot;:&quot;138&quot;,&quot;_legend&quot;:&quot;{score}\/{best} - ({count} {votes})&quot;,&quot;font_factor&quot;:&quot;1.25&quot;}">

<div class="kksr-stars">

<div class="kksr-stars-inactive">
            <div class="kksr-star" data-star="1" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="2" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="3" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="4" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="5" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>

<div class="kksr-stars-active" style="width: 138px;">
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>
</div>


<div class="kksr-legend" style="font-size: 19.2px;">
            5/5 - (2 votes)    </div>
    </div>
Overview

The objective of this lab is to get you familiar with writing ROS code for the Turtlebot 3. In this lab you will create your own ROS2 package containing two communicating nodes that enable the robot to turn in place to follow an object. You can also create one debugging node that allows your computer to display the processed image from the Turtlebot. You can use your image processing code from Lab 1 that enables the robot to identify the location of an object in the frame or create a new one for this task.

scp -r &lt;Directory on your cpu to copy&gt; burger@&lt;ip-of-burger&gt;:&lt;Directory to copy to on robot&gt;

Additionally, the robots have GIT installed to pull and push code to and from repositories if you prefer to use version control for your code. Alternatively, you can use VScode remote ssh and there is a guide on how to set this up availabe on Canvas.

Lab

find_object: This node should subscribe to receive images from the Raspberry Pi Camera on

the topic /image_raw/compressed. Example code in Python:

self._img_subscriber = self.create_subscription(CompressedImage, ’/image_raw/compressed’, self._image_callback, qos_profile)

Note: The self.&lt;variable&gt; is present because this subscriber is created within a class. Additionally, the qos_profile is a networking setting that is discussed later in this document. For more information see the example file provided with this lab view_img_raw.py and view_img_raw2.py. If you would like to clone the packages that use these scripts, you can clone the following ROS2 package into your ROS2 workspace on your computer,

https://github.gatech.edu/swilson64/camera_viewer

If you wish, you can use GIT to clone this repository,

git clone https://github.gatech.edu/swilson64/camera_viewer.git

To view compressed image topics on your computer you will need to install an additional transport package. You can do this with the following command on Linux,

sudo apt-get install ros-humble-image-transport-plugins

rotate_robot: This node should subscribe to the object coordinate messages from your find_object

node and publish velocity commands to the robot:

self._vel_publish = self.create_publisher(Twist, ’/cmd_vel’, 5)

Configure your code to have the robot turn to follow the object in the image (turn right when the object is on the right of the image, turn left when it is on the left, and stand still if the object is directly in front of the robot). The robot should not drive forward or back, only turn.

For this lab, the object can be at any distance from the robot that you choose within reason. You algorithm cannot require the object to take up the entire frame and there must be some tolerance to the distance (i.e. you cannot tell us the object must be exactly 30cm from the robot to work, you can say it should be around 30cm from the robot).

Simulation

For this lab, the Gazebo simulation environment can be used for code development and initial testing. The tutorial on simulating the Turtlebot in Gazebo can be found at,

https://emanual.robotis.com/docs/en/platform/turtlebot3/simulation/

Note: When cloning the repository to your computer in step 6.1.1.1 make sure you clone the ROS2 Humble branch into your current workspace (ros2_ws or whatever you named it, you can install it to a turtlebot3_ws but will need to source and build that new workspace appropriately). This can be done with the command, git clone -b humble-devel https://github.com/ROBOTIS-GIT/turtlebot3_simulations.git

If you wish, you can use GIT to clone this repository,

git clone https://github.gatech.edu/swilson64/turtlebot3_sim_update.git

Tips, Tricks, and Suggestions

here, https://docs.ros.org/en/humble/Tutorials/Intermediate/Launch/Creating-Launch-Files.html

• To capture images from the Raspberry Pi camera attached to the robot, please use the v4l2_camera_node for image acquisition in this lab

ros2 run v4l2_camera v4l2_camera_node –ros-args –params-file ./v4l2_camera.yaml

This ROS2 node grabs images from the camera on the robot and publishes them to the

/image/compressed topic. The parameters that effect the resolution of the camera are found in the v4l2_camera.yaml file in the run command above. If you choose to operate at a different resolution, please make a new yaml file. Do not change the default yaml file. Alternatively, you can use a custom launch file we have created that brings up the robot with the camera, ros2 launch turtlebot3_bringup camera_robot.launch.py.

Networking and Quality of Service Profiles

The computational ability of the Raspberry Pi is much weaker than your computer’s, meaning you most likely cannot process a high resolution image in real time. The launch file provided brings up the camera at 320×240 resolution.

https://docs.ros.org/en/humble/Concepts/About-Quality-of-Service-Settings.html and

https://docs.ros2.org/latest/api/rclpy/api/qos.html

The following code snippets can be used as a starting point to generate different QoS profiles within the __init__ function your subscriber is declared in,

from rclpy . qos import QoSProfile , QoSDurabilityPolicy , QoSReliabilityPolicy , QoSHistoryPolicy

custom_qos_profile = QoSProfile ( r e l i a b i l i t y=QoSReliabilityPolicy .BEST_EFFORT,

history=QoSHistoryPolicy .KEEP_LAST, durability=QoSDurabilityPolicy .VOLATILE,

depth=1

)

sub = Subscriber (

self ,

Image ,

“cool_image_topic” , qos_profile=custom_qos_profile

)

or

from rclpy . qos import QoSProfile , QoSDurabilityPolicy , QoSReliabilityPolicy , custom_qos_profile = QoSProfile (depth=1)

custom_qos_profile . r e l i a b i l i t y = QoSReliabilityPolicy .BEST_EFFORT custom_qos_profile . history = QoSHistoryPolicy .KEEP_LAST custom_qos_profile . durability = QoSDurabilityPolicy .VOLATILE

sub = Subscriber (

self ,

Image ,

“cool_image_topic” , qos_profile=custom_qos_profile

) QoSHistoryPolicy

Grading Rubric

The lab is graded out of 100 points, with the following point distribution:

Successfully run all codeo on the robot 15%

Robot rotates in the direction of the object consistantly* 50%

Communicate information between your two nodes 35%

o All code does not include any debugging code you write for your personal computer.

Submission

2. Put the names of both lab partners into the header of the python script. Put your python script and any supplimentary files, in a single zip file called

Lab2_LastName1_LastName2.zip and upload on Canvas under Assignments–Lab 2.

3. Only one of the partners needs to upload code.
