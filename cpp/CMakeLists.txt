# cpp/CMakeLists.txt

set(CMAKE_CXX_STANDARD 14)

#set(CMAKE_INCLUDE_CURRENT_DIR ON) I could use this instead of the following line, if I'm not mistaken

get_target_property(PROBLEM_GENERATOR_DIR problem_generator LOCATION)

include_directories(${PROBLEM_GENERATOR_DIR})
target_link_libraries(cpp ${PROBLEM_GENERATOR_DIR}/libproblem_generator.so)

set(SOURCE main.cpp)
add_executable(cpp ${SOURCE})

add_dependencies(cpp problem_generator)
