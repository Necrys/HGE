cmake_minimum_required ( VERSION 3.0 )

set ( ZLIB_SRC
  ZLIB/adler32.c
  ZLIB/crc32.c
  ZLIB/inffast.c
  ZLIB/inflate.c
  ZLIB/inftrees.c
  ZLIB/ioapi.c
  ZLIB/trees.c
  ZLIB/uncompr.c
  ZLIB/unzip.c
  ZLIB/zutil.c
)

set ( HGE_SRC
  demo.cpp
  graphics.cpp
  #hge.def
  ini.cpp
  input.cpp
  power.cpp
  random.cpp
  resource.cpp
  sound.cpp
  system.cpp
  timer.cpp
)

set ( HGE_HDR
  ../../include/hge.h
  hge_impl.h
)

add_library ( hge STATIC
  ${HGE_SRC}
  ${ZLIB_SRC}
)

target_include_directories ( hge
  PRIVATE
    ${DXSDK_PATH}/include
)

if ( NOT ( "${CMAKE_GENERATOR_PLATFORM}" STREQUAL "Win32" ) )
  set ( DX9LIB_PATH ${DXSDK_PATH}/lib/x64 )
else ()
  set ( DX9LIB_PATH ${DXSDK_PATH}/lib/x86 )
endif ()

target_link_libraries ( hge 
  INTERFACE
    ${DX9LIB_PATH}/d3d9.lib
    ${DX9LIB_PATH}/d3dx9.lib
)

source_group ( hge FILES ${HGE_SRC} ${HGE_HDR} )
source_group ( zlib FILES ${ZLIB_SRC} )