cmake_minimum_required(VERSION 3.5)
project(calculator C)

# Inclure le dossier contenant calculator.h
include_directories(include)

# Créer une bibliothèque à partir de calculator.c
add_library(calculator_lib src/lib/calculator.c)

# Créer l'exécutable principal (calculator)
add_executable(calculator src/main.c)
target_link_libraries(calculator calculator_lib)

# Activer les tests
enable_testing()

# Tests automatisés sur l’exécutable calculator
add_test(t1 calculator add 2 3)
add_test(t2 calculator sub 3 -2)
add_test(t3 calculator mul 5 5)
add_test(t4 calculator div 1 5)
add_test(t5 calculator car 4)
