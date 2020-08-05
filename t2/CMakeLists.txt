cmake_minimum_required(VERSION 3.10)
PROJECT (HELLO)
ADD_SUBDIRECTORY (src bin)



# 普通文件的安装
INSTALL (FILES COPYRIGHT README DESTINATION share/doc/cmake/t2 )

# 非目标文件的可执行程序的安装
INSTALL (PROGRAMS runhello.sh DESTINATION bin )

# 目录的安装
INSTALL (DIRECTORY doc/ DESTINATION share/doc/cmake/t2 )
#SET(SRC_LIST main.c)
#MESSAGE(STATUS "This is BINARY dir " ${HELLO_BINARY_DIR})
#MESSAGE(STATUS "This is SOURCE dir " ${HELLO_SOURCE_DIR})
#ADD_EXECUTABLE(hello ${SRC_LIST})
