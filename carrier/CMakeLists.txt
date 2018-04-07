message("Process Project: ${CMAKE_CURRENT_SOURCE_DIR}")

file(GLOB_RECURSE SRC_LIST
    "${CMAKE_CURRENT_SOURCE_DIR}/src/*.cpp"
)

ADD_EXECUTABLE(carrier ${SRC_LIST})
