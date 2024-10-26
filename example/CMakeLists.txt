add_executable(opencsgexample WIN32 MACOSX_BUNDLE
    displaylistPrimitive.cpp displaylistPrimitive.h
    includeGl.h
    main.cpp
)

find_package(GLUT REQUIRED)
find_package(OpenGL REQUIRED)

target_include_directories(opencsgexample PRIVATE
    ${OPENGL_INCLUDE_DIR}
    ${CMAKE_SOURCE_DIR}/include
)
target_link_libraries(opencsgexample PRIVATE
    ${GLUT_LIBRARIES}
    ${OPENGL_LIBRARIES}
    opencsg
)

install(TARGETS opencsgexample
    BUNDLE DESTINATION .
    RUNTIME DESTINATION ${CMAKE_INSTALL_BINDIR}
)

