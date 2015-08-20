Valgrind/Callgrind events profiling:
------------------------------------

Notes for differences in operations (events) to run divide.tis

Event data captured using: `valgrind --tool=callgrind --dump-instr=yes ./tis`

Thing done to code                        |Events captured | Diference | Diff. from orig
------------------------------------------|----------------|-----------|-----------------
**Original:**                                 |8730632         |0          |
After cmake (with m linking fix):         |8729470         |-1162      |-1162
Dispatch goto-by-val (after de-cruft):    |8659462         |-70008     |-71170
Add -O2 to CFLAGS *(1)*                     |5070865         |-3588597   |-3659767

(1) This is basically cheating.
