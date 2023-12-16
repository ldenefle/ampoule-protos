if(CONFIG_AMPOULE_PROTOS)
    zephyr_library_named(ampoule_protos)
    file(GLOB proto_sources ${CMAKE_CURRENT_SOURCE_DIR}/../protos/*.options ${CMAKE_CURRENT_SOURCE_DIR}/../protos/*.proto)

    list(APPEND CMAKE_MODULE_PATH ${ZEPHYR_BASE}/modules/nanopb)
    include(nanopb)

    zephyr_nanopb_sources(ampoule_protos ${proto_sources})
    zephyr_include_directories(${CMAKE_CURRENT_BINARY_DIR})
endif()
