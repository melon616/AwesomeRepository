# 1. Ros命令
| 参数                         | 说明                                                                 |
|------------------------------|----------------------------------------------------------------------|
| roscore              | 启动ROS Master、参数服务器和rosout记录节点     |
| rostopic             | 打印ROS话题信息                             |
| rosservice           | 打印ROS服务信息                              |
| rosnode              | 打印ROS节点信息                              |
| rossrv               | 显示ROS服务类型                             |
| rosparam             | 获取设置和删除ROS参数服务器参数               |
| rosrun               | 启动单个功能包中的某个节点                    |
| roslaunch            | 启动多个ROS节点                             |
| rosbag               | 操作bag文件                                |
| catkin_make          | 编译功能包                                 |
| catkin_create_pkg    | 创建功能包                                 |
| rqt_graph            | 创建功能包                                 |

# 2. 示例
## 2.1 TurtleSim

``` shell
source /opt/ros/melodic/setup.bash
# Terminal-0
roscore

# Terminal-1
rosrun turtlesim turtlesim_node

# Terminal-2
rosrun turtlesim turtle_teleop_key
```

## 2.2 VinsMono
``` shell
#1. 确认环境是否正常
source /opt/ros/melodic/setup.bash
roscore

#2. 运行Vins-Mono
2.1 编译
cd /home/rubin/rubinFiles/catkin_ws/src
git clone https://github.com/HKUST-Aerial-Robotics/VINS-Mono.git
cd ../
catkin_make
source ~/catkin_ws/devel/setup.bash

#2.2 运行（打开三个命令行终端）
roslaunch vins_estimator euroc.launch 
roslaunch vins_estimator vins_rviz.launch
rosbag play YOUR_PATH_TO_DATASET/MH_01_easy.bag
```

## 2.3 项目从0到1示例 
<!-- declare ros workspace -->
mkdir -p example_ws/src  
cd example/src  
source /opt/ros/melodic/setup.zsh  
catkin_init_workspace   

cd ..
catkin_make

<!-- create pkg --> 
cd src  
catkin_create_pkg demo_pkg roscpp rospy std_msgs  
<!-- set envir -->
source devel/setup.zsh  
echo $ROS_PACKAGE_PATH  

<!-- build pkg -->
catkin_make  
source devel/setup.zsh

<!-- run node in pkg -->
rosrun demo_pkg velocity_publisher  
rosrun demo_pkg pose_subscriber  