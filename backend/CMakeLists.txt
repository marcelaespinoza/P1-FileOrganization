cmake_minimum_required(VERSION 3.10)

project(backend_bd)

set(CMAKE_CXX_STANDARD 14)

# Añadir los directorios de inclusión
include_directories(include)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -g")

# Añadir el ejecutable
add_executable(backend_bd src/main.cpp src/avl_handler.cpp src/sequential_handler.cpp)

# Encontrar y vincular cpprestsdk y OpenSSL
find_package(cpprestsdk REQUIRED)
find_package(OpenSSL REQUIRED)

target_link_libraries(backend_bd cpprest OpenSSL::SSL OpenSSL::Crypto)

