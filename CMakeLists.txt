cmake_minimum_required(VERSION 3.15)

project(sqlite LANGUAGES CXX)

# Create the static library
add_library(sqlite STATIC "src/sqlite3.c")
add_library(sqlite::sqlite ALIAS sqlite)

target_include_directories(sqlite PUBLIC
	$<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/include>
)

set_property(TARGET sqlite PROPERTY CXX_STANDARD 11)

# Installation rules
install(TARGETS sqlite
	EXPORT sqlite
	LIBRARY DESTINATION lib
	ARCHIVE DESTINATION lib
	RUNTIME DESTINATION lib/include
)

install(DIRECTORY include/ DESTINATION include)

install(EXPORT sqlite
	FILE sqlite.cmake
	NAMESPACE sqlite::
	DESTINATION lib/cmake/sqlite
)
