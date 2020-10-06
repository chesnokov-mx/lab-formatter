# Устанавливаем минимальную версию CMake 3.4
cmake_minimum_required(VERSION 3.4)

# Устанавливаем версию стандарта C++11
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED 11)

# Указываем название проекта
project(hello_world_application)

# Подключаем директорию с необходимым хедером
include_directories(${CMAKE_HOME_DIRECTORY}/../formatter_ex_lib/)

# Указываем исполняемый класс
add_executable(hello_world_application ${CMAKE_HOME_DIRECTORY}/hello_world.cpp)

# Указываем используемые собранные библиотеки
target_link_libraries(hello_world_application ${CMAKE_HOME_DIRECTORY}/../formatter_ex_lib/build/libformatter_ex_lib.a)
target_link_libraries(hello_world_application ${CMAKE_HOME_DIRECTORY}/../formatter_lib/build/libformatter_lib.a)