project (iniparser C)

add_library (${PROJECT_NAME}
 src/iniparser.c
 src/iniparser.h
 src/dictionary.c
 src/dictionary.h)

set (INIPARSER_INCLUDE_DIR ${CMAKE_CURRENT_SOURCE_DIR}/src CACHE INTERNAL "IniParser headers")
set (INIPARSER_LIBRARIES iniparser CACHE INTERNAL "IniParser libraries")

include_directories (src)

add_executable(inifile example/inifile.c)
target_link_libraries(inifile ${INIPARSER_LIBRARIES})
install(TARGETS inifile DESTINATION "bin")

IF (MSVC)
    include (MSVC)
    MSVC_CRT_SECURE_NO_WARNINGS (${PROJECT_NAME})
    MSVC_CRT_SECURE_NO_WARNINGS (inifile)
ENDIF (MSVC)
