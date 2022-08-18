# InstallROS1ANDinstall-ROS2-on-Jetson-Nano
Steps to install ROS1 and ROS2 :
# Oacle VM VirtualBox
The first step is download Oacle VM VirtualBox from https://www.virtualbox.org
# Ubunto
Second step is download Ubunto Desktop 22.04LTS from https://ubuntu.com/download/desktop#download
-open Oacle VM VirtualBox and then click on NEW To start with the steps of running Ubunto on the virtual box.
# Ubuntu install of ROS Noetic
Enter the following commands in CMD:
1-sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list
2-sudo apt install curl
3-curl -s https://raw.githubusercontent.com/ros/rosdistro/master/ros.asc | sudo apt-key add -
4-sudo apt update
5-sudo apt install ros-noetic-desktop-full
6-source /opt/ros/noetic/setup.bash
7-sudo apt install python3-rosdep python3-rosinstall python3-rosinstall-generator python3-wstool build-essential
8-sudo apt install python3-rosdep
9-sudo rosdep init
rosdep update

ROS is sucessfully installed.

# install xubuntu in Jetson Nano
https://github.com/Discombobulated88/Xubuntu-20.04-L4T-32.3.1/releases/download/v1.0/Xubuntu-20.04-l4t-r32.3.1.tar.tbz2

# Download balena
https://www.balena.io/etcher/
-after we download both Should be write xubuntu to a flash memory using balena

# ROS2 installation
#Set locale

sudo apt update && sudo apt install locales
sudo locale-gen en_US en_US.UTF-8
sudo update-locale LC_ALL=en_US.UTF-8 LANG=en_US.UTF-8
export LANG=en_US.UTF-8


# Setup Sources
apt-cache policy | grep universe

-If you don’t see the right output line, then enable the Universe repository with these instructions.

sudo apt install software-properties-common
sudo add-apt-repository universe

-Now add the ROS 2 apt repository to your system.

sudo apt update && sudo apt install curl gnupg2 lsb-release
sudo curl -sSL https://raw.githubusercontent.com/ros/rosdistro/master/ros.key  -o /usr/share/keyrings/ros-archive-keyring.gpg

-Then add the repository to your sources list.

echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/ros-archive-keyring.gpg] http://packages.ros.org/ros2/ubuntu $(source /etc/os-release && echo $UBUNTU_CODENAME) main" | sudo tee /etc/apt/sources.list.d/ros2.list > /dev/null

# Install ROS2 packages
1-sudo apt update
2-sudo apt upgrade
3-sudo apt install ros-foxy-desktop
4-echo "source /opt/ros/foxy/setup.bash" >> ~/.bashrc
source ~/.bashrc

