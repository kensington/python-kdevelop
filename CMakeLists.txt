PROJECT(python-kdevelop)
cmake_minimum_required(VERSION 2.8)

add_custom_target(
    parser ALL
    COMMAND /bin/bash ${CMAKE_CURRENT_SOURCE_DIR}/configure --enable-shared --without-pymalloc WORKING_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR}
    COMMAND /usr/bin/env make -C ${CMAKE_CURRENT_SOURCE_DIR}
)

install(FILES libpython2.7-kdevelop.so DESTINATION ${LIB_INSTALL_DIR})
install(FILES libpython2.7-kdevelop.so.1.0 DESTINATION ${LIB_INSTALL_DIR})
install(DIRECTORY python-src/Lib/encodings DESTINATION ${DATA_INSTALL_DIR}/kdevpythonsupport)
