# EPSO Library
# author: amirabbas asadi
# email: amir137825@gmail.com
cmake_minimum_required(VERSION 2.8)
project(EPSO_Optimizer)
# library info
set(info "EPSO\nC++ Enhanced Particle Swarm Optmization Library\nAuthor: Amirabbas Asadi\nEmail: amir137825@gmail.com")
# library development
# ON: development
# OFF: release
set(development ON)
# library version
set(version 0.0.1)
set(CMAKE_CXX_STANDARD 11)
set(lib_sources src/Optimizer.cpp)
add_library(EPSO STATIC ${lib_sources})
# development mode
if(development)
    message(${info})
    message("Development Version: ${version}")
    # build test files
    set(test_sources tests/main.cpp)
    add_executable(app ${test_sources})
    target_include_directories(app PRIVATE "includes/")
    target_link_libraries(app EPSO)
endif(development)
