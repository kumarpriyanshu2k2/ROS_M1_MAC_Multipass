# ROS_M1_MAC_Multipass

steps to install robot operating system on m1 mac using multipass


### 1. install [multipass](https://multipass.run/https://multipass.run/)

to read more: [multipass Docs](https://multipass.run/docs)

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
    
### 10. setup graphic desktop(optional)

    $ multipass shell ros-neotic
    $ sudo apt update
    $ sudo apt install ubuntu-desktop xrdp
    # setup password for your account
    $ sudo passwd ubuntu
    # enter your password twice
1. next you'll need to install parallels client from app store

![Screenshot 2022-05-20 at 8 26 34 PM](https://user-images.githubusercontent.com/93030904/169555511-302c7c25-f616-4932-ae98-02541b897807.jpg)

2. Obtain the ip address of your instance by running the command in your system terminal

        $ multipass info ros-neotic

![Screenshot 2022-05-20 at 8 29 26 PM](https://user-images.githubusercontent.com/93030904/169558171-db383a93-a9f6-46e8-906b-26330291a1be.jpg)


3. open parallels client and click on file>new connection if you don't get a prompt 

![Screenshot 2022-05-20 at 8 27 32 PM](https://user-images.githubusercontent.com/93030904/169555853-c3f095e8-eb19-4bf4-ab2a-4c84a9dd6b65.jpg)

4. create a standard RDP

![Screenshot 2022-05-20 at 8 32 09 PM](https://user-images.githubusercontent.com/93030904/169556586-282f1253-605e-4ae2-bbb1-228115ea2eb9.jpg)

5. Enter your instance's ip address in the server field

![image](https://user-images.githubusercontent.com/93030904/169557482-f60ddc63-3811-4d57-b7d9-820453c8c2a1.png)

6. login into your instance using the password you created in your instance

![Screenshot 2022-05-20 at 8 34 46 PM](https://user-images.githubusercontent.com/93030904/169557648-204b68bd-b088-4549-980f-da6ec68c1c93.jpg)

now you can access the gui of your instance

![Screenshot 2022-05-20 at 8 39 45 PM](https://user-images.githubusercontent.com/93030904/169557983-558efc6e-3ac2-4ad3-aba3-2681ae7c7d33.jpg)


## All done ! 🥳🎉

to test if it is working properly visit [ROS Tutorials](http://wiki.ros.org/ROS/Tutorials) 


  
