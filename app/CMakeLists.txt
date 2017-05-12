add_executable(app app.cc)
target_link_libraries(app net_static)

add_executable(http_client http_client.cc)
target_link_libraries(http_client net_static)

find_package(RapidJSON)
if (RapidJSON_FOUND)
include_directories(${RapidJSON_INCLUDE_DIRS})
add_executable(rest_description rest_description.cc)
target_link_libraries(rest_description net_static)
endif()
