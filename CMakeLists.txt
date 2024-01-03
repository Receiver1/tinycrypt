cmake_minimum_required(VERSION 3.26)

project(tinycrypt LANGUAGES C)

# Enable tests
set(ENABLE_TESTS true)

# Add include directories
include_directories(
    lib/include
    tests/include
)

# Check if the OS is Windows
if(WIN32)
    set(DOTEXE ".exe")
endif()

add_subdirectory(lib)

# Define ENABLE_TESTS macro based on the ENABLE_TESTS variable
if (ENABLE_TESTS)
    enable_testing()
    add_compile_definitions(ENABLE_TESTS)
    add_subdirectory(tests)
else()
     add_compile_definitions(DISABLE_TESTS)
endif()