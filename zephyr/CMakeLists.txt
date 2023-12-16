if(CONFIG_AMPOULE_PROTOS)
    file(GLOB proto_sources ${CMAKE_CURRENT_SOURCE_DIR}/../protos/*.options ${CMAKE_CURRENT_SOURCE_DIR}/../protos/*.proto)

    nanopb_generate_cpp(PROTO_SRCS PROTO_HDRS RELPATH ${proto_sources})

    zephyr_library_sources(${PROTO_SRCS})
    zephyr_include_directories(${CMAKE_CURRENT_BINARY_DIR})
endif()
