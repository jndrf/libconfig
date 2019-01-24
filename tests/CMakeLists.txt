if(CMAKE_HOST_WIN32)
    set(libname "libconfig")
else()
    set(libname "config")
endif()

add_executable(libconfig_tests
    tests.c
    )
  
target_include_directories(libconfig_tests PRIVATE ${CMAKE_SOURCE_DIR}/lib)

target_link_libraries(libconfig_tests
    ${libname}
    libtinytest
)

add_test(
    NAME libconfig_tests
    COMMAND libconfig_tests
    WORKING_DIRECTORY ${CMAKE_SOURCE_DIR}/tests
)
