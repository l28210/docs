# VScode编译运行调试C++

```
code .
```

当前工作文件夹打开vscode


在 C++ 中，main 函数是程序的入口点，它有一个整数类型的返回值，通常用于指示程序的退出状态。当 main 函数没有显式的 return 语句时，C++ 编译器会自动添加一个 return 0; 语句

写好源码后，添加调试配置，选择g++，生成launch.json与tasks.json

g++ 是 GNU Compiler Collection（GCC）中的 C++ 编译器。它是一个用于编译 C++ 代码的命令行工具，通常在 Linux 和类 Unix 操作系统中使用

用g++编译daim
```
g++ your_program.cpp -o output_executable
g++ my_program.cpp -o my_program
./my_program
```


tasks.json (compiler build settings) ，负责编译
launch.json (debugger settings)，负责调试
c_cpp_properties.json (compiler path and IntelliSense settings)，负责更改路径等设置

- task.json

command: 要运行的程序，此处是g++
args： args 数组包含将传递给 g++ 的命令行参数（必须按照编译器预期的顺序指定）。"${file}"表示当前打开的待编译的活动文件，对它进行编译，并在当前路径${fileDirname}生成与活动文件同名无后缀的可执行文件"${fileDirname}/${fileBasenameNoExtension}"。

label: 标签值是将在任务列表中看到的内容；可以随意命名它
group中的isDefault: 值为true表示支持通过快捷键ctrl+shift+B来执行该编译任务


执行编译注意选择g++

完成编译在终端输入
```
ls
./file
```
即可查看结果

修改task.json可满足特定需求
比如 将"${file}"替换“${workspaceFolder}/*.cpp”来构建多个 C++ 文件; 将“${fileDirname}/${fileBasenameNoExtension}”替换为硬编码文件名（如“helloworld.out”）来修改输出文件名。


## debug

launch.json
program: 指带调试的程序,其值对应程序的路径。在这里设置为"${fileDirname}/${fileBasenameNoExtension}"
stopAtEntry: 默认情况下，C++拓展不会向源代码添加任何断点，stopAtEntry 值设置为 false。 将stopAtEntry值更改为 true 将使调试器在开始调试时停止在 main 方法上

- 开始一个调试会话
在main函数所在行设置断点
F5/
F11逐步调试

## C/C++配置

左下角设置图标选择命令
运行命令 C/C++: Edit Configurations (UI) 来查看 C/C++ 配置 UI
vscode下会自动生成c_cpp_properties.json 文件）

若程序不在工作区或标准库路径中的头文件
只需要修改包含路径Include path 设置

