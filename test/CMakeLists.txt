project(blitztest)

if (WIN32)
 set(CMAKE_DEBUG_POSTFIX "d")
endif (WIN32)

include_directories(
${CMAKE_SOURCE_DIR}
${blitztest_BINARY_DIR}
${blitz_lib_SOURCE_DIR}
)

set(blitztest_SRCS main.cpp mainwindow.cpp scaledialog.cpp)

set(CMAKE_AUTOMOC ON)

if(COMMAND cmake_policy)
  cmake_policy(SET CMP0003 NEW)
endif(COMMAND cmake_policy) 

add_executable(blitztest ${blitztest_SRCS})

target_link_libraries(blitztest Qt4::QtCore Qt4::QtGui qimageblitz)

install(TARGETS blitztest DESTINATION ${BIN_INSTALL_DIR})

