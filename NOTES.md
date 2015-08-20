Valgrind/Callgrind events profiling:
------------------------------------

Notes for differences in operations (events) to run divide.tis

Event data captured using: `valgrind --tool=callgrind --dump-instr=yes ./tis`

Thing done to code                        |Events captured
------------------------------------------|----------------
**Original:**                                 |8730632
After cmake (with m linking fix):         |8729470
Dispatch goto-by-val (after de-cruft):    |8659462
**Add -O2 to CFLAGS** *(1)*                     |5070865

(1) This is basically cheating.
