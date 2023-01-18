
This tutorial will explore coppelia sim and understand basic interactions
using the ZeroMQ remote API

The tutorial was made on ubuntu 20.04

After studyuing this tutorial you will understand how to:

- install Coppelia Simulator
- add and manipulate basic shapes 
- add and manipulate joints
- setup ZeroMQ remote api 
- interact with the simulator and simulation using the ZeroMQ API


Installing the simulator
---

1. Visit the coppelia simulator website and go to downloads section.
   https://www.coppeliarobotics.com/downloads

2. Download the edu version (since we are not using it for commercial purposes)
3. Extract the downloaded folder and copy to desired location

    I am going to assume that we have renamed the extracted folder to `CoppeliaSim` and placed it at  `/home/<user>/coppelia/CoppeliaSim`

4. Test the installation by going to `/home/<user>/coppelia/CoppeliaSim` and running ./coppeliaSim 

    Once the simulator starts up, you should see the following screen.
    >The version of the simulator used here is `4.4.0 rev 0`, if you are using another version , there could be slight differences. 

    ![Start Screen](/images/coppelia/coppelia_start_screen.png)

5. If you saw the screen,  coppelia simualtor has successfully been installed on your system.


Creating a simple robot
---

Before proceeding further, you should familiarize with the interface of the simuator so that you know what the terms beign talked about are referring to.
you can find the refrence in the  `User Interface` section of https://www.coppeliarobotics.com/helpFiles/index.html


Now that the simulator is ready for use, we will create our own simple robot arm to explore and understand how robot/models are represented in CoppeliaSim.

Our robot is going to be a 2 DOF robot arm. It is going to consist of :

- A tall cuboidal base 
- One cylindrical link attached to the base by a revolute joint.

1. Go to Menu --> Add --> Primitive Shape --> Cubiod, set dimensions
x = 0.1, y = 0.1 and z = 0.2, rename the shape to 'robot_base'. you should see an object like this

    ![Robot Base](/images/coppelia/bot_base_screen.png)

2. Next , we will add a revolute joint.
   Go to Menu --> Add --> Joint --> Revolute and rename it to `shoulder_joint`. This will create a joint at the origin, to place the joint at our desired position (i.e top of the cuboid) we need to apply translation to the joint.

   - Select the joint from scene hierarchy
   - click on the translation button 

        ![](/images/coppelia/translation_button.png)
   - A pop up window will appear, select the position tab and you should see options like this.

        ![](/images/coppelia/translation_pop_up.png)

   - Keep the `Relative to:` option set to `World` and set value of Z to 0.25 so that the joint origin is slightly above the robot 
   base

   - The default axis of rotation for the revolute joint in coppelia sim is the z-axis, so we do not need to modify orientation since the axis of rotation we want is along z as well.
   
   This should give you a result like this.

   ![Shoulder Joint](/images/coppelia/shoulder_joint.png)



