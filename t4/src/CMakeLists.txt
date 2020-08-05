# 向工程添加非标准头文件的搜索路径
# INCLUDE_DIRECTORIES (BEFORE /usr/include/hello)

FIND_PATH(myHeader hello.h)
IF (myHeader)
INCLUDE_DIRECTORIES(${myHeader})
ENDIF (myHeader)
ADD_EXECUTABLE (main main.c)


# 添加非标准的共享库搜索路径
# 由于usr/lib已经在搜索路径中，所以下面这条语句暂时用不到
# LINK_DIRECTORIES(/usr/lib)

# 为target添加需要链接的共享库
TARGET_LINK_LIBRARIES (main libhello.a)

EXEC_PROGRAM(ls ${PROJECT_SOURCE_DIR}/src ARGS "*.c" 
            OUTPUT_VARIABLE LS_OUTPUT 
            RETURN_VALUE LS_RVALUE)
IF(NOT LS_RVALUE)
MESSAGE(STATUS "ls result: " ${LS_OUTPUT})
ENDIF(NOT LS_RVALUE)
