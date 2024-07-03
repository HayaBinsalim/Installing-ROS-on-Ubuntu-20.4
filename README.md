# Installing-ROS-on-Ubuntu-20.4
# Description

Installation of ROS Noetic on Ubuntu 20.4. Make sure Ubuntu 20.4 is installed on your device. 

## 1. Open Ubuntu 20.4
From the virtual box, start Ubuntu 20.4 and login into your account. Start the ***terminal*** application. This is where all the following steps will be done. 

## 2. Set up your sources.list 
Start by ensuring that your package list is up to date: <br />
```
sudo apt update
sudo apt upgrade
```
Next, add the ROS repository to your sources list. This is to make your device accept software from the ROS packages. <br />

```
sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'
```
## 3. Set up your keys 
This step adds the ROS package signing key. <br />

```
sudo apt install curl
curl -s https://raw.githubusercontent.com/ros/rosdistro/master/ros.asc | sudo apt-key add -
```
After adding the ROS package, update the package index to include the new ROS repository in yours.  <br />

```
sudo apt update
```

## 4. Install ROS Noetic 
Choose how much ROS you need and want to install. You can install the base and any packages you need or install the ***desktop-full*** version that includes all the tools and simulators.  We will be installing the full version: <br />

```
sudo apt install ros-noetic-desktop-full
```

## 5. Initialize the ROS dependencies 
There are some tools and dependencies required to manage ROS workspaces and packages. You can install them by running the line below. <br />

```
sudo apt install python3-rosinstall python3-rosinstall-generator python3-wstool build-essential
```

To install these tools easily for any source, you can use the command-line tool ***rosdep***. You can install it by running the following: <br />

```
sudo apt install python3-rosdep
```

Then initialize ***rosdep***: <br />

```
sudo rosdep init
rosdep update
```

## 6. Setup the environment
When you install ROS, you need to set up your environment to include its environment variables. To ensure these environment variables are set every time you open a new terminal, you can add the command to source the ROS setup script to your ***.bashrc*** file. This will automatically set up the ROS environment every time you open a new terminal. <br />

```
echo "source /opt/ros/noetic/setup.bash" >> ~/.bashrc
source ~/.bashrc
```

## 7. Verification of the ROS installation 
To verify you have installed ROS correctly, run the following command. If it goes well with no errors, ROS is installed. <br />

```
roscore
```

The image below shows what should occur if the installation is done. <br />

![output](https://github.com/HayaBinsalim/Installing-ROS-on-Ubuntu-20.4/blob/main/rosInstall.png)

#### Reference 
https://wiki.ros.org/noetic/Installation/Ubuntu


