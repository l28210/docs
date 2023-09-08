# 动态链接实验

- 生成目标文件(*.o)
```
gcc -c -fPIC main.c test.c
```

ps.若使用的头文件是自己编写的头文件，应该使用双引号
    -fPIC可不加

- 生成动态库

```
gcc -shared -o libtest_d.so test.o
```

- 使用动态连接库的方式生成可执行程序

```
gcc main.o -L. -ltest_d -o test_d.out
```

-L指定库文件所在目录，“.”表示当前目录
-ltest_d 告诉编译器要链接名为 libtest_d.so 的共享库

- 运行
```
./test_out
```


报错“./test_d.out: error while loading shared libraries: libtest_d.so: cannot open shared object file: No such file or directory”

由于linux在/usr/lib路径搜索要用的库，.so不在那里

1)将这个文件拷贝过去（一般不用）
2)把当前路径增加设置为动态库搜索路径

```
export LD_LIBRARY_PATH=/path/to/directory:$LD_LIBRARY_PATH
```

可成功运行

ps.
.h文件为类声明，包含类的结构和接口
.cpp文件为类定义，提供实际功能和行为

