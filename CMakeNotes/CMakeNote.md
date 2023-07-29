[TOC]

#  使用CMake编译

> ```cmake
> PROJECT (HELLO) #工程名
> 
> SET(SRC_LIST main.cc) #源文件，可以有多个
> 
> MESSAGE(STATUS "This is BINARY dir " ${HELLO_BINARY_DIR})
> 
> MESSAGE(STATUS "This is SOURCE dir " ${HELLO_SOURCE_DIR})
> 
> ADD_EXECUTABLE hello ${SRC_LIST}
> ```



# CMake语法介绍

## PROJECT 关键字

> 默认是支持所有语言， `NAME`代表工程名
>
> `PROJECT (NAME)` 指定了工程的名字，并且支持所有语言
>
> `PROJECT (NAME CXX)` 指定了工程的名字，并且支持的语言是C++
>
> `PROJECT (NAME C CXX)` 指定了工程的名字，并且支持语言是C和C++

## SET关键字

> 用来显示的指定变量，源文件可以有多个
>
> `SET(SRC_LIST main.cc)` SRC_LIST变量就包含了 main.cc

## MESSAGE关键字

> 向终端输出用户自定义的信息
>
> 主要包含三种信息：
>
> + SEND_ERROR：产生错误，生成过程被跳过
> + SATUS：输出前缀为“–”的信息
> + FATAL_ERROR，立即终止所有 cmake 过程

## ADD_EXECUTABLE关键字

> 生成可执行文件
>
> `ADD_EXECUTABLE(hello ${SRC_LIST})` 生成的可执行文件名是“hello”，源文件读取变量 SRC_LIST 中的内容
>
> 也可以直接写成 `ADD_EXECUTABLE(hello main.cc)`

## 取值规则

> + 变量使用 `${}` 方式取值，但是在 IF 控制语句中是直接使用变量名
> + 指令（参数1， 参数2…）参数

