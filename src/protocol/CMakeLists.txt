include_directories(${CMAKE_CURRENT_SOURCE_DIR})

collect_sources(PROTOCOL)

add_library(lzfsprotocol ${PROTOCOL_SOURCES})

# if (ZLIB_FOUND)
#   target_link_libraries(mfscommon ${ZLIB_LIBRARIES})
# endif()
# if (RT_LIBRARY)
#   target_link_libraries(mfscommon ${RT_LIBRARY})
# endif()
# if(TCMALLOC_LIBRARY)
#   target_link_libraries(mfscommon ${TCMALLOC_LIBRARY})
# endif()
# if(SOCKET_FOUND)
#   target_link_libraries(mfscommon ${SOCKET_LIBRARIES})
# endif()
create_unittest(lzfsprotocol ${PROTOCOL_TESTS})
link_unittest(lzfsprotocol mfscommon)
