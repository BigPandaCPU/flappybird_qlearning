cmake_minimum_required(VERSION 2.8)

project(fql)
set (CMAKE_CXX_STANDARD 11)

set(CMAKE_BINARY_DIR ${CMAKE_SOURCE_DIR}/build)
set(EXECUTABLE_OUTPUT_PATH ${CMAKE_BINARY_DIR})
set(LIBRARY_OUTPUT_PATH ${CMAKE_BINARY_DIR})

find_package(SDL2)

add_executable(app ${CMAKE_SOURCE_DIR}/src/main.cpp
			   ${CMAKE_SOURCE_DIR}/src/flappybird/game.hpp 
			   ${CMAKE_SOURCE_DIR}/src/flappybird/game.cpp
			   ${CMAKE_SOURCE_DIR}/src/flappybird/bird.hpp
			   ${CMAKE_SOURCE_DIR}/src/flappybird/bird.cpp
			   ${CMAKE_SOURCE_DIR}/src/flappybird/background.hpp
			   ${CMAKE_SOURCE_DIR}/src/flappybird/land.hpp
			   ${CMAKE_SOURCE_DIR}/src/flappybird/digit.hpp
			   ${CMAKE_SOURCE_DIR}/src/flappybird/pipe.hpp
			   ${CMAKE_SOURCE_DIR}/src/engine/eg.hpp
			   ${CMAKE_SOURCE_DIR}/src/engine/screen.hpp
			   ${CMAKE_SOURCE_DIR}/src/engine/gameobject.hpp
			   ${CMAKE_SOURCE_DIR}/src/engine/atlas.hpp
			   ${CMAKE_SOURCE_DIR}/src/engine/timer.hpp
			   ${CMAKE_SOURCE_DIR}/src/engine/sprite.hpp
			   ${CMAKE_SOURCE_DIR}/src/engine/transform.hpp
			   ${CMAKE_SOURCE_DIR}/src/engine/utils.hpp
			   ${CMAKE_SOURCE_DIR}/src/engine/math.hpp
			   ${CMAKE_SOURCE_DIR}/src/model/ql.hpp
)


target_include_directories(app PUBLIC ${SDL2_INCLUDE_DIRS})
target_link_libraries(app
					  ${SDL2_LIBRARIES} 
					  "C:/Program Files/SDL2/lib/SDL2_image.lib"   
					  )
#if release  "C:\Program Files\SDL2\lib\SDL2_image.lib"
#if debug    "C:\Program Files\SDL2\lib\SDL2_imaged.lib"
