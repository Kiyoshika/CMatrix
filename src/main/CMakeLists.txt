set(ROOT_INCLUDE ${CMatrix_SOURCE_DIR}/include)

add_library(util util/util.c)
target_include_directories(util PUBLIC ${ROOT_INCLUDE}/util)

add_library(vector vector/vector.c)
target_include_directories(vector PUBLIC ${ROOT_INCLUDE}/vector)
target_link_libraries(vector util)

add_library(matrix matrix/matrix.c)
target_include_directories(matrix PUBLIC ${ROOT_INCLUDE}/matrix)
target_link_libraries(matrix util vector)

# KEEPING FOR CONVENIENCE
add_executable(testing testing.c)
target_include_directories(testing PUBLIC ${ROOT_INCLUDE})
target_link_libraries(testing matrix util vector)
