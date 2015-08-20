# CMake flags
set(CMAKE_C_FLAGS "-std=c99 -Wpedantic -O2 -Wall -Wundef -Wstrict-prototypes -Wmissing-declarations")

# Find Ncurses
find_library(NCURSES NAMES ncurses libncurses)

# Core libraries
foreach(BaseSrcsIter program node util input_code node_list output)
    set(BaseSrcs ${BaseSrcs} ${BaseSrcsIter}.c)
endforeach(BaseSrcsIter)
add_library(core ${BaseSrcs})
target_link_libraries(core ncurses m)

# Main executable
add_executable(tis tis.c)
target_link_libraries(tis core)
