# RoboKings - WRO Future Engineers 2024
RoboKings (Pakistan)
- **School Name:** MindCortex 
### Member Details :
1. Moeez Anwar (**Software Developer**)
2. Fateh Zeeshan (**Hardware Developer**)
3. Muhammad Dayyan (**Software Developer**)



# Project Overview
We're the RoboKings, a passionate team from Pakistan on a mission to conquer the WRO Future Engineers 2024 challenge by building a fully autonomous self-driving car! Inspired by the magic of Santa's industrious elves, our car is designed to navigate a designated track and complete three laps without human intervention. This project embodies our commitment to robotics, innovation, and the future of intelligent transportation.

### The WRO Challenge and Our Focus
The WRO Future Engineers category emphasizes the entire engineering process. Teams earn points for their final product and for documenting their journey within a public GitHub repository. This year's exciting challenge features a randomly changing track, testing our car's adaptability!

We're focusing on these key areas to build our autonomous car:

- **Sensor Fusion and Computer Vision:** We'll use LiDAR, cameras, and computer vision to give our car a real-time understanding of its surroundings.
- **Open-Source Hardware:** We're building with readily available components like a Jetson Nano, an RC chassis, and the Adafruit Motor Shield.
- **Action Planning and Kinematic Control:** Sophisticated algorithms will enable the car to make decisions and execute maneuvers beyond simple differential drive.
- **Optimization for Stability:** Our goal is to create a consistently reliable car capable of navigating the various track layouts.
- **Teamwork and Documentation:** Strong collaboration, communication, and a detailed engineering journal will be critical to our success.
# Track Details :
![Track ](Track-Picture.png)

## Technical Specifications

### Hardware

| Component | Description | Image | Link 
|---|---|---|---|
| **NVIDIA Jetson Nano** | Provides processing power for complex deep learning models. | ![image-removebg-preview (5)](https://github.com/MoeezAnwar/RoboKings/assets/116732848/1dd911b8-c91a-4631-95df-8684bb978abf) | <https://bit.ly/3wKg5TG>
| **LiDAR Sensor** | Creates a detailed 3D map of the environment for precise navigation and obstacle detection. | ![image-removebg-preview (6)](https://github.com/MoeezAnwar/RoboKings/assets/116732848/2bff55ed-4e26-40d4-92c5-fb1c7ce7ac35) |<https://amzn.to/3SXeS2I>
| **2-3 Raspberry Pi Cameras** | Capture rich visual data used for object detection, lane tracking, and path planning. | ![image-removebg-preview (7)](https://github.com/MoeezAnwar/RoboKings/assets/116732848/bf8420fb-db4a-40f1-aea0-3e7068d7ce46) |<https://amzn.to/4c0Tv9o>
| **RC Car Chassis** | The physical foundation for our self-driving elf car. | ![71GffrS4wsL _AC_SX679_-removebg-preview](https://github.com/MoeezAnwar/RoboKings/assets/116732848/a55f7e87-181b-406d-88d0-e1d41bb70d0d)|<https://amzn.to/3uPM0Bz>
| **Adafruit Motor Shield** | Enables precise motor control for smooth and reliable movements and steering. | ![image-removebg-preview (9)](https://github.com/MoeezAnwar/RoboKings/assets/116732848/dcf58b72-aea9-4db2-9e2a-3df08da5f890) |<https://bit.ly/4a2cHle>

### Software
- **C++:** Forms the core of our development, allowing for efficient code and optimal performance.
- **Open-Source Libraries:** We'll utilize established deep learning libraries like TensorFlow or PyTorch for training our autonomous driving model, plus libraries for sensor integration and motor control.

# Project Structure
- **Documentation:** Comprehensive guides on project goals, hardware setup, software design, the WRO challenge, our engineering journey, and more!
- **Code:** Well-structured C++ code with clear modularity, informative comments, and adherence to best practices.
- **Data:** Curated training data for the deep learning model.
- **3D Design Files (Optional):** Files used for customized parts or modifications.

## Collaboration, Contribution, and Community
The RoboKings welcome collaboration! Reach out to us through discussions, pull requests, or issues to share your expertise, suggest improvements, or report any challenges you encounter. We're excited to be part of the WRO community and are committed to sharing our progress and lessons learned.

> [!IMPORTANT]
>  We may not be able to disclose certain implementation details related to our deep learning model or proprietary algorithms to safeguard our competitive edge.


# Installation 
### Vscode & C++ Installation: 
**Installing Visual Studio Code**

Since the Jetson Nano has an ARM-based architecture, you'll need to get VS Code in a few different ways:

1. **Remote Development:**
   * This is the recommended approach for complex development.  Install VS Code on a more powerful desktop computer (Windows, macOS, or Linux).
   * On your Jetson Nano, install the Remote Development extensions for VS Code: [https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.vscode-remote-extensionpack](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.vscode-remote-extensionpack)
   * Connect to your Jetson Nano from your desktop VS Code for a seamless development experience.

2. **Install VS Code Server (Less Recommended):**
    * You can install a lightweight version of VS Code that runs directly on the Jetson Nano   

**Setting Up for C++ Development**

1. **Install C/C++ Extension:** Follow the same instructions as the general guide.

2. **Install a C++ Compiler:**
   * Use Ubuntu's package manager:
     ```bash
     sudo apt-get install g++
     ```

**Testing Your Setup:**

* Follow the same steps as the general guide for creating a test C++ file, compiling, and running it.
>[!NOTE]
>**Additional Considerations for Jetson Nano**
>* **Performance:** The Jetson Nano has limited resources compared to a desktop. You might experience some limitations in terms of speed for large projects.
>* **Cross-Compilation:** If you prefer working on a desktop PC, you can set up cross-compilation to build code specifically targeting the Jetson Nano's ARM architecture.

## ROS installation guide for NVIDIA jetson

>[!IMPORTANT]
>**Prerequisites**
>* **Operating System:** Ubuntu 18.04 (Bionic Beaver) or Ubuntu 20.04 (Focal Fossa). Check your OS version using `lsb_release -a`.
>* **NVIDIA Hardware:** A compatible NVIDIA device (e.g., Jetson Nano, Jetson Xavier NX, etc.).
>* **NVIDIA JetPack:** If you're using a Jetson device, ensure you have JetPack installed appropriately for your hardware.

**Installation Steps**

1. **Set Up Sources**

   * Configure your Ubuntu repositories to allow "restricted," "universe," and "multiverse."
   * Add the ROS repository:

     ```bash
     sudo apt-key adv --keyserver 'hkp://keyserver.ubuntu.com:80' --recv-key C1CF6E31E6BADE8868B172B4F42ED6FBAB17C654
     sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'
     ```

2. **Install ROS**

   * Update your package lists:

     ```bash
     sudo apt update
     ```

   * Choose your desired ROS installation:

     * **Desktop-Full Install:** (Recommended for comprehensive use)

       ```bash
       sudo apt install ros-YOUR-DISTRO-desktop-full
       ```

     * **Desktop Install:** (Core tools and libraries)

       ```bash
       sudo apt install ros-YOUR-DISTRO-desktop 
       ```

     * **Base Install:** (Bare bones ROS)

       ```bash 
       sudo apt install ros-YOUR-DISTRO-ros-base 
       ```

   * Replace `YOUR-DISTRO` with either `melodic` (Ubuntu 18.04) or `noetic` (Ubuntu 20.04) 

3. **Initialize `rosdep`**

   ```bash
   sudo rosdep init
   rosdep update
   ```

4. **Environment Setup**

   ```bash
   echo "source /opt/ros/YOUR-DISTRO/setup.bash" >> ~/.bashrc
   source ~/.bashrc
   ```

5. **(Optional) Build Tools**

   ```bash
   sudo apt install python3-rosdep python3-rosinstall python3-rosinstall-generator python3-wstool build-essential
   ```

**Testing Your Installation**

1. **New Terminal:** Open a new terminal.
2. **`roscore`:** 

   ```bash
   roscore
   ```

## Auto Install Script 
Here's a bash script that automates the installation of ROS, Visual Studio Code (using the Remote Development approach), and the C++ setup on an Ubuntu-based NVIDIA Jetson Nano. 
>[!IMPORTANT]
>* **Customization:** You'll likely need to adjust paths and versions based on your specific requirements.
>* **JetPack:** I'm assuming you have JetPack installed.
>* **Remote Machine:** This script assumes you have a desktop machine ready for remote development with VS Code installed.
>* **ROS Distribution:** I've used 'melodic' (for Ubuntu 18.04). Replace with 'noetic' if you're using Ubuntu 20.04.

**The Script (`jetson_setup.sh`)**

```bash
#!/bin/bash

# ROS Installation
echo "== Installing ROS =="
sudo apt-key adv --keyserver 'hkp://keyserver.ubuntu.com:80' --recv-key C1CF6E31E6BADE8868B172B4F42ED6FBAB17C654
sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'
sudo apt update
sudo apt install ros-melodic-desktop-full -y
sudo rosdep init
rosdep update
echo "source /opt/ros/melodic/setup.bash" >> ~/.bashrc
source ~/.bashrc

# VS Code Remote Development Setup
echo "== Setting up VS Code Remote Development =="
sudo apt install openssh-server -y  # Install SSH server if not already present 
sudo apt install -y libssl-dev libxkbfile-dev build-essential # Install dependencies

# Install the Remote Development Extensions on your Jetson Nano (refer to the official documentation for the latest URLs)
wget -O vscode_remote.deb "https://update.code.visualstudio.com/latest/linux-arm64-deb/stable" # Replace with the latest version URL
sudo apt install ./vscode_remote.deb

# C++ Setup
echo "== Installing C++ Compiler =="
sudo apt install g++ -y

echo "== Installation Complete =="
echo "**Important:**"
echo "- On your desktop VS Code, connect to your Jetson Nano using Remote Development."
echo "- Ensure necessary C++ build tools are configured on your desktop machine."
```

**How to Use**

1. **Create the Script:** Copy the code above and save it as `jetson_setup.sh` on your Jetson Nano.
2. **Make it Executable:**
   ```bash
   chmod +x jetson_setup.sh
   ```
3. **Run the Script:**
   ```bash
   ./jetson_setup.sh
   ```

>[!NOTE]
>**Remember to adjust versions, paths, and setup your desktop VS Code for Remote Development to complete the process!**




## Stay Tuned!
This repository is a work in progress. Follow our development journey as we build and refine our self-driving car for the WRO Future Engineers 2024 challenge!
