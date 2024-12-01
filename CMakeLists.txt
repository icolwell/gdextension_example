cmake_minimum_required(VERSION 3.22)

project("gdextension_example")

add_subdirectory("godot-cpp")

add_library("gdextension_example" SHARED
    "src/gdexample.cpp"
    "src/register_types.cpp"
)

target_link_libraries("gdextension_example" PRIVATE "godot::cpp")

string(TOLOWER "${CMAKE_SYSTEM_NAME}" CMAKE_SYSTEM_NAME_LOWER)
string(TOLOWER "${CMAKE_SYSTEM_PROCESSOR}" CMAKE_SYSTEM_PROCESSOR_LOWER)

set_target_properties("gdextension_example" PROPERTIES OUTPUT_NAME "gdexample.${CMAKE_SYSTEM_NAME_LOWER}.template_debug.${CMAKE_SYSTEM_PROCESSOR_LOWER}")
