
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

    ![Start Screen](/images/coppelia_start_screen.png)

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
x = 0.1, y = 0.1 and z = 0.2, rename the shape to 'bot_base'.
you will notice that even though we gave a height of 0.2 m the base looks small.
That is because objects are created with origin as (0, 0, 0). So to see the full object , we should move (apply translation) to the object.

2. Click on the `bot_base` model from the scene hierarchy and then click on the translation button from the tool bar.
It looks like this.

    ![translation](/images/translation_button.png)

    Once you click on the button you should see a small window pop up, in the window , go to the `positions` tab and make sure the `Relative to` option is set to `World`. Then set the value of Z to 0.1, this will set the absolute postion (position relative to world frame) of the `bot_base` object to (0, 0, 1) and we can see the entire model above the floor like seen in the below image.

    ![Robot Base](/images/bot_base_screen.png)



