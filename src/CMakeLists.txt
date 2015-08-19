# CMake flags
set(CMAKE_C_FLAGS "-std=c99 -pedantic -Wall -pedantic-errors -Wundef -Wstrict-prototypes  -Wmissing-declarations")

# Find Ncurses
find_library(NCURSES NAMES ncurses libncurses)

# Core libraries
foreach(BaseSrcsIter program node util input_code node_list output)
    set(BaseSrcs ${BaseSrcs} ${BaseSrcsIter}.c)
endforeach(BaseSrcsIter)
add_library(core ${BaseSrcs})

# Main executable
add_executable(tis tis.c)
target_link_libraries(tis
    ncurses core
    )
