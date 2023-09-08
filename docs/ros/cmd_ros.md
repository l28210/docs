# ROS命令

## rostopic

- 查看当前活跃话题
```
rostopic list
```

- 查看话题，节点间的关系
```
rqt_graph
```

- 查看话题消息类型
```
rostopic type file/topic
```

- 查看消息类型的结构和字段
```
rosmsg show <message_type>
```

- 显示指定ros话题消息的命令

```
rostopic echo <topic_name>
```


## 创建工作空间与包
- 工作空间目录
```
mkdir -p ~/ros_workspace/src
```

- 初始化工作空间
```
cd ~/ros_workspace/src
catkin_init_workspace
```
在工作空间的根目录创建一个CMakeLists.txt文件，用于告诉ROS工具如何构建工作空间

- 构建工作空间
```
cd ..
catkin_make
```

- 创建包
在src下
```
catkin_create_pkg package_name [dependencies]
```

## ros节点通讯分析
- 可视化
```
rqt_graph
```

- 节点日志
```
cd ~/.ros/log
ls
```

- rosnode
```
rosnode list 
rosnode info /node
```

