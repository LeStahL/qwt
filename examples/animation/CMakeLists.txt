add_executable(animation
    main.cpp
    Plot.cpp
)

target_link_libraries(animation qwt Qt5::Core Qt5::Widgets)
target_include_directories(animation PUBLIC
    "${PROJECT_SOURCE_DIR}/classIncludes"
    "${PROJECT_SOURCE_DIR}/src"
)
