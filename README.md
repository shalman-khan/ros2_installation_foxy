# ros2_installation_foxy 

### LOCALE SETUP

Defines User's Language, Region, Preferences for user interface

```
locale
```
Before Installation, get updated list of packages

```
sudo apt update
```

Install latest version of locales

```
sudo apt install locales
```

Locale Configuration after installation

```
sudo locale-gen en_US en_US.UTF-8

sudo update-locale LC_ALL=en_US.UTF-8 LANG=en_US.UTF-8

export LANG=en_US.UTF-8

locale

```
![Locale](https://github.com/shalman-khan/ros2_installation_foxy/blob/main/images/Screenshot%20from%202022-09-01%2010-27-50.png)
### ROS2 DOWNLOAD

Update Available Package Index again
```
sudo apt update
```
Download Key to verify packages from Standard Release

```
sudo apt install curl gnupg2 lsb-release

curl -s https://raw.githubusercontent.com/ros/rosdistro/master/ros.asc | sudo apt-key add -

sudo sh -c 'echo "deb [arch=$(dpkg --print-architecture)] http://packages.ros.org/ros2/ubuntu $(lsb_release -cs) main" > /etc/apt/sources.list.d/ros2-latest.list'

```


### ROS2 INSTALLATION

Update and Install ROS2 Foxy Desktop

```
sudo apt update && sudo apt install ros-foxy-desktop
```

Configure Environment Variable [To avoid sourcing the setup file everytime a new terminal is opened]

```
echo "source /opt/ros/foxy/setup.bash" >> ~/.bashrc
```

### INSTALLATION VERIFICATION

Check the distribution opening a Terminal. Ouput: "foxy"
```
echo $ROS_DISTRO
```
![Distro](https://github.com/shalman-khan/ros2_installation_foxy/blob/main/images/Screenshot%20from%202022-09-01%2010-58-25.png)

#### Verify- ROS2 Pub-Sub communication

Open Terminal 1 and Run

```
ros2 run demo_nodes_cpp talker
```

Open Terminal 2 and Run

```
ros2 run demo_nodes_cpp listener
```
![Talker](https://github.com/shalman-khan/ros2_installation_foxy/blob/main/images/Screenshot%20from%202022-09-01%2011-38-22.png)
![Listener](https://github.com/shalman-khan/ros2_installation_foxy/blob/main/images/Screenshot%20from%202022-09-01%2011-38-25.png)





