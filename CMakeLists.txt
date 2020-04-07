project(office_mate)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED True)

add_compile_options(/experimental:module /MP)

add_subdirectory(thirdparty)

# install(
# 	TARGETS sfml-window sfml-system
# 	RUNTIME DESTINATION ${CMAKE_CURRENT_BINARY_DIR}/Debug
# )

set(CMAKE_MODULE_PATH ${CMAKE_CURRENT_LIST_DIR}/build/thirdparty/SFML-2.5.1/)
set(SFML_DIR ${CMAKE_CURRENT_LIST_DIR}/build/thirdparty/SFML-2.5.1/)
find_package(SFML 2.5 COMPONENTS system window REQUIRED)

include_directories(${CMAKE_CURRENT_LIST_DIR}/include)
include_directories(${SFML_INCLUDE_DIR})

add_executable(office_mate src/main.cpp)

target_link_libraries(office_mate sfml-window)