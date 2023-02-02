cmake_minimum_required(VERSION 4.4.0)
project(Template VERSION 0.1.0) # THIS NEEDS TO BE SET TO THE NAME OF YOUR PROJECT

include_directories(C:/Users/aiden/Documents/cxxtest-4.4/)
set(CXXTEST_PYTHON_TESTGEN_EXECUTABLE C:/Users/aiden/Documents/cxxtest-4.4/bin/cxxtestgen)
find_package(CxxTest REQUIRED)
enable_testing()

CXXTEST_ADD_TEST(unittest # name of the test
    runner.cpp  # THIS IS GENERATED BUT YOU NEED TO ADD IT HERE
    ${CMAKE_CURRENT_SOURCE_DIR}/Functions.cpp  # add source files
    ${CMAKE_CURRENT_SOURCE_DIR}/Tests.h  # YOUR TEST DESCRIPTION FILE
)

add_executable(Template main.cpp Classes.h App.cpp Tests.h) # SET THIS TO THE NAME OF YOUR PROJECT AND ADD ALL SOURCE FILES

set(CPACK_PROJECT_NAME ${PROJECT_NAME})
set(CPACK_PROJECT_VERSION ${PROJECT_VERSION})
include(CPack)