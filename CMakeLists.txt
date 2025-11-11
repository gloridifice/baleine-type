# Baleine Type
add_library(BaleineType INTERFACE)
target_include_directories(BaleineType INTERFACE ${CMAKE_CURRENT_SOURCE_DIR}/include)
set_target_properties(BaleineType PROPERTIES LINKER_LANGUAGE CXX)

#Baleine Type Absl
add_library(BaleineTypeAbsl INTERFACE)
target_include_directories(BaleineTypeAbsl INTERFACE ${CMAKE_CURRENT_SOURCE_DIR}/include_absl)
target_link_libraries(BaleineTypeAbsl INTERFACE
        absl::synchronization
)
set_target_properties(BaleineTypeAbsl PROPERTIES LINKER_LANGUAGE CXX)

# Test
if (BUILD_TESTING)
    add_subdirectory(test)
endif ()
