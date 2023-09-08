# ROS joy

## 手柄配置

- 查看
```
ls /dev/input
```
应有一个jsX

- 测试

```
sudo jstest /dev/input/jsX/
```

- 手柄许可
```
ls -l /dev/input/jsX
```

显示
```
crw-rw-r--+ 1 root input 13, 0 9月   7 09:27 /dev/input/js0
```
c 表示这是一个字符设备文件，rw-rw-r-- 表示该文件的权限，即读写权限

1：这表示连接到该设备的链接数

crw-rw-rw- ：
这表示文件或设备的所有者、所属组和其他用户都具有读写权限。
任何用户都可以读取和写入该设备，无需特权。
这通常用于让多个用户或进程能够共享对设备的访问权限

crw-rw-r--+ 权限（包含ACL）：

这表示文件或设备的所有者和所属组都具有读写权限，但带有附加访问控制列表（ACL）。
ACL允许进一步细化对文件的访问权限，可以指定特定用户或组是否可以访问文件，并以何种方式访问。
ACL可以用于更精细地控制文件的访问

```
sudo chmod 664 /dev/input/js0
```
可改为crw-rw-r--+

```
sudo chmod a+rw /dev/input/js0 
```
反之

- 为joy_node设置路径

```
rosparam set joy_node/dev "/dev/input/js0"
```

- 运行节点

```
rosrun joy joy_node
```

- 查看手柄数据
```
rostopic echo joy
```

