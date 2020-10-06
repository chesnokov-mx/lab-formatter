# Устанавливаем минимальную версию CMake 3.4
cmake_minimum_required(VERSION 3.4)

# Устанавливаем версию стандарта C++11
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED 11)

# Указываем название проекта
project(formatter_ex_lib)

# Подключаем файл `formatter_ex.cpp`, как статическую библиотеку
add_library(formatter_ex_lib STATIC ${CMAKE_HOME_DIRECTORY}/formatter_ex.cpp)

# Указываем директорию с библиотекой `formatter`
target_include_directories(formatter_ex_lib PUBLIC ${CMAKE_HOME_DIRECTORY}/../formatter_lib)