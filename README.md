# Robotic-programinig-assessment
Step-1

  The workspace should be updated and upgraded first 


        sudo apt-get update && sudo apt-get upgrade


Step-2

Install Topologiagal-Navigation package: To work in a upto date environment.

   
 sudo apt-get install \
    ros-melodic-topological-utils \
    ros-melodic-topological-navigation \
    ros-melodic-topological-navigation-msgs \
    ros-melodic-strands-navigation


First, make sure that you have a working copy  The code is included in the uol_cmp9767m_tutorial folder. If you have your workspace set up already in the previous workshops, please pull the recent update from the repository as some of the workshop files have been updated recently or Create your own workspace and build package and pull the code from


Step-3:   In this task, we will run the topological navigation. The topological map for the assessment is available in uol_cmp9767m_tutorial/maps/test_mod.yaml. Create a folder (named mongodb) in your user home directory. MongoDB will store all database files required to run our topological map. This step is required only once. Launch the simulation setup


        roslaunch bacchus_gazebo vineyard_demo.launch world_name:=vineyard_small
        
        
        
 To open the topological navigation use:
        
        
        roslaunch uol_cmp9767m_tutorial topo_nav.launch
        
                               
                              
If you work with a dockerised distribution (e.g. at home or using a remote access) please use the following line instead which will help to address some issues with the MongoDB database: HOSTNAME=0.0.0.0 roslaunch uol_cmp9767m_tutorial topo_nav.launch.You will see some warnings in the terminal where you launched topo_nav.launch saying the pointset is not found in the message_store. This is because we haven't loaded the topological map to the mongodb yet. Once you do the next step, that warning should stop.

        rosrun topological_utils load_yaml_map.py $(rospack find uol_cmp9767m_tutorial)/maps/test_mod.yaml. 
        
This step is required only once.Open the topological map visualisation config for RVIZ in uol_cmp9767m_tutorial/config/topo_nav.rviz.click the green arrows at the nodes seen in RVIZ to send topological_navigation goals to the robot.Navigate between different nodes and note the robot's behaviour on edges with a different directionality.


step-4

   Action client Follow the steps in Task 1 to launch the topological_navigation stack.In another terminal 
    
      rosrun uol_cmp9767m_tutorial set_topo_nav_goal.py 
    
 And see what is happening.Look at the script (uol_cmp9767m_tutorial/scritps/set_topo_nav_goal.py) to see how the goals are sent.

step-5 : To run the python program goto uol_cmp9767m_tutorial/scripts

        python2 objtracking.py
        
        
github link: https://github.com/sujithk1999/Robotic-programinig-assessment.git
