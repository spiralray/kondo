# kondo
ROS package for runnning KONDO servo motors

[![](http://img.youtube.com/vi/7zwGp7oLmdg/0.jpg)](https://www.youtube.com/watch?v=7zwGp7oLmdg)

## How to use
* Clone this project into your catkin workspace

```Bash
cd ~/catkin_ws/src
git clone https://github.com/spiralray/kondo.git
```
    
* Build to generate original rosmsg "kondo/servo"

```Bash
cd ~/catkin_ws
catkin_make
```

* Set the path of USB serial device. For example

```Bash
rosparam set /kondo/port /dev/ttyUSB0
```

* Run kondo.py

```Bash
rosrun kondo kondo.py
```

* To set angles of servo motors, send message to /servo/tx

```Bash
rostopic pub /kondo/tx kondo/servo "stamp:
  secs: 0
  nsecs: 0
id: 1
angle: 1.0"
```

* To read angles, recieve /kondo/rx

```Bash
rostopic echo /kondo/rx
```
