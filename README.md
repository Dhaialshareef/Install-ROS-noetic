# Install-ROS-noetic

# ROS Noetic Installation Guide on Ubuntu 20.04 

Step 1: Configure Ubuntu Repositories
Ensure your system allows restricted, universe, and multiverse repositories. Follow the Ubuntu guide if needed.

Step 2: Setup ROS Package Sources
Add the ROS repository:
sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'

Step 3: Set Up GPG Keys
Install curl and add the GPG key:
sudo apt install curl -y
curl -s https://raw.githubusercontent.com/ros/rosdistro/master/ros.asc | sudo apt-key add -
Step 4: Update Package Index
Ensure your package index is updated:
sudo apt update

Step 5: Install ROS Noetic
Choose the installation type:

Full Desktop : Includes all tools, libraries, and simulators
sudo apt install ros-noetic-desktop-full
Desktop Install: Includes core tools (rqt, rviz) but no simulators
sudo apt install ros-noetic-desktop

Base Install: Minimal version without GUI tools
sudo apt install ros-noetic-ros-base

Install Specific Packages:
sudo apt install ros-noetic-PACKAGE

sudo apt install ros-noetic-slam-gmapping

To search for available packages:
apt search ros-noetic
Step 6: Setup ROS Environment
ROS must be sourced in every new terminal session:
source /opt/ros/noetic/setup.bash
To make this automatic:
 For Bash Users:

echo "source /opt/ros/noetic/setup.bash" >> ~/.bashrc
source ~/.bashrc
For Zsh Users:
echo "source /opt/ros/noetic/setup.zsh" >> ~/.zshrc
source ~/.zshrc

Step 7: Install Dependencies for Building Packages
sudo apt install python3-rosdep python3-rosinstall python3-rosinstall-generator python3-wstool build-essential

Step 8: Initialize rosdep
 Install rosdep:
sudo apt install python3-rosdep

Initialize and update rosdep:
sudo rosdep init
rosdep update

Installation Complete
