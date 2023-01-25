# find_package(fmt CONFIG REQUIRED)

set(SRC main.cpp)

# add the executable
add_executable(hello ${SRC})

# target_link_libraries(hello PRIVATE fmt::fmt-header-only)
