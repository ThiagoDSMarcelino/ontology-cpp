cmake_minimum_required(VERSION 3.14)

set(This OntologyTests)

set(SRCS
  calculus_test.cpp
  operations_test.cpp
)

add_executable(${This} ${SRCS})

include(FetchContent)
FetchContent_Declare(
  googletest
  URL https://github.com/google/googletest/archive/03597a01ee50ed33e9dfd640b249b4be3799d395.zip
)
FetchContent_MakeAvailable(googletest)


target_link_libraries(${This} PUBLIC
  GTest::gtest_main
  Ontology
)

add_test(
  NAME ${This}
  COMMAND ${This}
)
