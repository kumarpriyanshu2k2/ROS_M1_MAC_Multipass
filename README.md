# ROS_M1_MAC_Multipass

steps to install robot operating system on m1 mac using multipass


1. install multipass https://multipass.run/https://multipass.run/

to read more about multipass https://multipass.run/docs

### 2. after installing multipass start a ubuntu instance in terminal.

    $ multipass launch -n ros-neotic --disk 15G 20.04

you can check the status of your instance using $ multipass info ros-neotic

### 3. activate your instance shell 

    $ multipass shell ros-neotic

### 4. Run the following commands in your instance shell

    $ sudo apt update
    $ sudo apt upgrade
    $ sudo apt install curl
    $ sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'

### 5. set-up your keys

    $ curl -s https://raw.githubusercontent.com/ros/rosdistro/master/ros.asc | sudo apt-key add -

### 6. installation

    $ sudo apt update
    $ sudo apt upgrade --fix-missing
    $ sudo apt install ros-noetic-desktop-full --fix-missing
  
### 7. Environment setup

    $ source /opt/ros/noetic/setup.bash
    $ echo "source /opt/ros/noetic/setup.bash" >> ~/.bashrc
    $ source ~/.bashrc

### 8. install dependencies
  
    $ sudo apt install python3-rosdep python3-rosinstall python3-rosinstall-generator python3-wstool build-essential

### 9. initialize ros

    $ sudo apt install python3-rosdep
    $ sudo rosdep init
    $ rosdep update
    
## All done ! 🥳🎉

to test if it is working properly visit http://wiki.ros.org/ROS/Tutorials 


  
