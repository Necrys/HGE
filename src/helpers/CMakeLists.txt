cmake_minimum_required ( VERSION 3.0 )

set ( HGEHELP_SRC
  hgeanim.cpp
  hgecolor.cpp
  hgedistort.cpp
  hgefont.cpp
  hgegui.cpp
  hgeguictrls.cpp
  hgeparticle.cpp
  hgepmanager.cpp
  hgerect.cpp
  hgeresource.cpp
  hgesprite.cpp
  hgestrings.cpp
  hgevector.cpp
  parser.cpp
  resources.cpp
)

set ( HGEHELP_HDR
  ../../include/hgeanim.h
  ../../include/hgecolor.h
  ../../include/hgedistort.h
  ../../include/hgefont.h
  ../../include/hgegui.h
  ../../include/hgeguictrls.h
  ../../include/hgeparticle.h
  ../../include/hgerect.h
  ../../include/hgeresource.h
  ../../include/hgesprite.h
  ../../include/hgestrings.h
  ../../include/hgevector.h
  parser.h
  resources.h
)

add_library ( hgehelp STATIC ${HGEHELP_SRC} )

source_group ( hgehelp FILES ${HGEHELP_SRC} ${HGEHELP_HDR} )