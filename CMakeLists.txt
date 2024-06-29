# It is not recommended to build dynamic libraries.
add_library(tmc2209 INTERFACE)

target_include_directories( tmc2209 INTERFACE src )

target_sources(tmc2209 INTERFACE
    src/TMC2209/TMC2209.cpp
)

# For interface libraries this is not completely required. (This would likely be required for static and dynamic libraries.)
# Use caution when building static libraries as there could be internal dependencies which need to be mitigated.
target_link_libraries(tmc2209 INTERFACE
    pico_multicore
    hardware_dma
    hardware_pio
    hardware_timer
)
