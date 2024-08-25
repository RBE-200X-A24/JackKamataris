# Specify the minimum required version of CMake
cmake_minimum_required(VERSION 3.13)

# Include the Pico SDK setup script
include(pico_sdk_import.cmake)

# Define the project name and supported languages
project(jacks_test C CXX ASM)

# Set the C and C++ standards to use
set(CMAKE_C_STANDARD 11)
set(CMAKE_CXX_STANDARD 17)

# Initialize the Pico SDK (requires the path to the SDK, typically set in your environment)
pico_sdk_init()

# Define the executable target and specify the source files
add_executable(jacks_test
  my_project.c
)

# Link the target with necessary libraries for the Pico SDK
target_link_libraries(jacks_test
	pico_stdlib          # Standard library for the Pico
	pico_cyw43_arch_none # No wireless support (useful if not using Wi-Fi/Bluetooth)
)

# Generate additional output formats (e.g., .uf2, .elf)
pico_add_extra_outputs(jacks_test)

