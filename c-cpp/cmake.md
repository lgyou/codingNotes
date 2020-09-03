#### cmake

# 1.基本语法

## 1.1基本信息
```
# CMake 最低版本号要求
cmake_minimum_required (VERSION 2.8)

# 项目信息
project (Demo1)

# 指定生成目标
add_executable(Demo main.cc)
```

如果代码文件很多,可以用`aux_source_directory(<dir> <variable>)`指定源代码路径,会把里面的所有源文件进行编译

比如修改为这样:
```
# 并将名称保存到 DIR_SRCS 变量
aux_source_directory(. DIR_SRCS)

# 指定生成目标
add_executable(Demo ${DIR_SRCS})
```


## 1.3多目录编译

需要每个文件夹都编写一个cmake文件

在根目录,添加`add_subdirectory(math)`和`target_link_libraries(Demo MathFunctions)`,其中后面的MathFunction是待会子目录的链接库的名字
在子目录,编写内容:
```
# 查找当前目录下的所有源文件
# 并将名称保存到 DIR_LIB_SRCS 变量
aux_source_directory(. DIR_LIB_SRCS)

# 生成链接库
add_library (MathFunctions ${DIR_LIB_SRCS})
```


# 2.测试代码
- 

