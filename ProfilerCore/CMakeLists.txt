IF (WIN32)
file(GLOB Platform_SRC
    "Windows/*.h"
    "Windows/*.cpp"
)
ELIF(WIN64)
file(GLOB Platform_SRC
    "Windows/*.h"
    "Windows/*.cpp"
)
ELSE()
file(GLOB Platform_SRC
    "Linux/*.h"
    "Linux/*.cpp"
)
ENDIF()

file(GLOB Common_SRC
    "*.h"
    "*.cpp"
)

add_library (ProfilerCore ${Common_SRC} ${Platform_SRC})
target_include_directories (ProfilerCore PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})