cmake_minimum_required(VERSION 3.18.4)
project (instagram_reverse_search
	VERSION 1.0.0
	DESCRIPTION ""
        HOMEPAGE_URL "github.com/BillionDollarMistake/instagram_reverse_search"
	LANGUAGES CXX
)

set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

add_library(face_detection_recognition STATIC src/face_detection_recognition.cpp)

target_include_directories(face_detection_recognition PRIVATE ${PROJECT_SOURCE_DIR}/include)
find_package(OpenCV REQUIRED)
target_link_libraries(face_detection_recognition PRIVATE ${OpenCV_LIBS})
include_directories(${OpenCV_INCLUDE_DIRS})

add_executable(${PROJECT_NAME} src/main.cpp)

target_include_directories(${PROJECT_NAME} PRIVATE ${PROJECT_SOURCE_DIR}/include)
target_link_libraries(${PROJECT_NAME} PRIVATE face_detection_recognition)
