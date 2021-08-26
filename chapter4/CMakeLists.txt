
set(EXECUTABLE_OUTPUT_PATH ${CMAKE_CURRENT_SOURCE_DIR}/bin)
add_executable(eserver echo_server.c)
add_executable(eclient echo_client.c)