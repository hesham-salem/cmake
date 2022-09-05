cmake_minimum_required(VERSION 3.16)
project(test)
set(SRC_FILES
    main.cpp
    src/calc.cpp)
message(STATUS "the src files is :${SRC_FILES}")
message("PASS IS " ${CMAKE_SOURCE_DIR})

# if(EXISTS ${CMAKE_SOURCE_DIR}/main.cpp)
# message(FATAL_ERROR "missing the main file")
# else()
# message("test2")
# endif()
add_subdirectory(${CMAKE_SOURCE_DIR}/lib)
add_executable(main main.cpp ${SRC_FILES})
target_include_directories(main PUBLIC include/ lib/)
target_link_libraries(main PUBLIC wifi_lib)