cmake_minimum_required(VERSION 3.18.4) # cmake --version
project (instagram_reverse_search
	VERSION 1.0.0
	DESCRIPTION ""
	HOMEPAGE_URL ""
	LANGUAGES CXX
)

file(GLOB SOURCES "src/*.cpp")

add_executable(${PROJECT_NAME} ${SOURCES})

target_include_directories(${PROJECT_NAME}
	PUBLIC
		${PROJECT_SOURCE_DIR}/include
)
