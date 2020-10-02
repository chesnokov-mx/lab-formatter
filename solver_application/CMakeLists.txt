# Устанавливаем минимальную версию CMake 3.4
cmake_minimum_required(VERSION 3.4)

# Устанавливаем версию стандарта C++11
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED 11)

# Указываем название проекта
project(solver_application)

# Добавляем библиотеку solver_lib
add_library(solver_lib ${CMAKE_HOME_DIRECTORY}/../solver_lib/solver.h ${CMAKE_HOME_DIRECTORY}/../solver_lib/solver.cpp)
# Подключаем директории с необходимыми хедерами
include_directories(${CMAKE_HOME_DIRECTORY}/../formatter_ex_lib/)
include_directories(${CMAKE_HOME_DIRECTORY}/../solver_lib/)

# Указываем исполняемый класс
add_executable(solver_application ${CMAKE_HOME_DIRECTORY}/equation.cpp)

# Указываем используемые библиотеки
target_link_libraries(solver_application solver_lib)
# Указываем используемые собранные библиотеки
target_link_libraries(solver_application ${CMAKE_HOME_DIRECTORY}/../formatter_ex_lib/build/libformatter_ex_lib.a)
target_link_libraries(solver_lib ${CMAKE_HOME_DIRECTORY}/../formatter_lib/build/libformatter_lib.a)