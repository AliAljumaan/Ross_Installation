# Ross_Instalation
## Instal linux
It is necessary to provide the required environment for the installation of Ross, which is Linux. With Linux, you have two options: either you download it into your computer or you use a virtual machine. In this case, a virtual box will be used. Below are the steps for downloading Linux using Virtual Box.

* visit The following website.
```
https://www.virtualbox.org/
```
* Download the virtualBox.
```
Downloads>windows hosts
```
* Visit the following website and download ubentu 20.04 the Desktop image virsion.
```
https://releases.ubuntu.com/20.04/
```
* Install Virtualbox by normally presseing next.
* From the main Virtualbox page press new and add a proprite name and location for the virtual box machine.
* Choose the virtual box machine and prees Settings>Storage.
* Press emptiy and alocate the upento 20.04.
## Install Ross
### Configure your Ubuntu repositories
The following commands must be typed inside the Linux terminal in order to install Ross.
### Setup your sources.list
Setup your computer to accept software from packages.ros.org.
```
sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'
```
### Set up your keys
```
sudo apt install curl # if you haven't already installed curl
curl -s https://raw.githubusercontent.com/ros/rosdistro/master/ros.asc | sudo apt-key add -
```
### Installation
First, make sure your Debian package index is up-to-date:
```
sudo apt update
```
Desktop-Full Install: (Recommended) : Everything in Desktop plus 2D/3D simulators and 2D/3D perception packages
```
sudo apt install ros-noetic-desktop-full
```
There are even more packages available in ROS. You can always install a specific package directly.
```
sudo apt install ros-noetic-slam-gmapping
```
### Environment setup
You must source this script in every bash terminal you use ROS in.
```
echo "source /opt/ros/noetic/setup.bash" >> ~/.bashrc
source ~/.bashrc
```
### Dependencies for building packages
Up to now you have installed what you need to run the core ROS packages. To create and manage your own ROS workspaces, there are various tools and requirements that are distributed separately. For example, rosinstall is a frequently used command-line tool that enables you to easily download many source trees for ROS packages with one command.

To install this tool and other dependencies for building ROS packages, run:
```
sudo apt install python3-rosdep python3-rosinstall python3-rosinstall-generator python3-wstool build-essential
```
#### Initialize rosdep
Before you can use many ROS tools, you will need to initialize rosdep. rosdep enables you to easily install system dependencies for source you want to compile and is required to run some core components in ROS. If you have not yet installed rosdep, do so as follows.
```
sudo apt install python3-rosdep
```
With the following, you can initialize rosdep.
```
sudo rosdep init
rosdep update
```
