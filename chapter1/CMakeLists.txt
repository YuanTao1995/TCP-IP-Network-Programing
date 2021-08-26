
set(EXECUTABLE_OUTPUT_PATH ${CMAKE_CURRENT_SOURCE_DIR}/bin)
add_executable(hserver hello_server.c)
add_executable(hclient hello_client.c)
add_executable(low_open low_open.c)