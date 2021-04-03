cmake_minimum_required ( VERSION 3.0 )
project ( HGE CXX )

set( DXSDK_PATH "" CACHE STRING "DirectX 9 SDK installation path" )

add_subdirectory ( src/core )
add_subdirectory ( src/helpers )