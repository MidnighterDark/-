cmake_minimum_required(VERSION 3.10)
project(Game)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

set(URHO3D_HOME "C:/Users/4770/Downloads/Urho3D-master/build")

set(CMAKE_MODULE_PATH ${URHO3D_HOME}/../CMake/Modules)
find_package(Urho3D REQUIRED)
include_directories(${URHO3D_INCLUDE_DIRS})

add_executable(Game Source/main.cpp Source/mutant08.cpp)
# target_link_libraries(Game ${URHO3D_LIBRARIES})
target_link_libraries(Game
    ${URHO3D_LIBRARIES}
    winmm.lib
    imm32.lib
    setupapi.lib
    version.lib
    d3d11.lib
    d3dcompiler.lib
    dxgi.lib
    dxguid.lib
)


# Указываем, где искать заголовки Urho3D
target_include_directories(Game PRIVATE
    ${URHO3D_HOME}/../include
)