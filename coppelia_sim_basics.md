
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