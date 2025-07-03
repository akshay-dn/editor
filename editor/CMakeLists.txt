# CMakeList.txt : CMake project for editor, include source and define
# project specific logic here.
#
cmake_minimum_required(VERSION 3.16)

find_package(Qt6 REQUIRED COMPONENTS Widgets)
set(CMAKE_AUTOMOC ON)
set (SOURCES
     src/main.cpp
     src/gui/MainWindow.cpp 
)
set (HEADERS
     src/gui/MainWindow.h 
)

# Add source to this project's executable.
add_executable (editor  
	${SOURCES} ${HEADERS}
)



#find_package(Qt6 REQUIRED COMPONENTS Widgets)
if (CMAKE_VERSION VERSION_GREATER 3.12)
  set_property(TARGET editor PROPERTY CXX_STANDARD 20)
endif()
target_link_libraries(editor PRIVATE Qt6::Widgets)
# TODO: Add tests and install targets if needed.
