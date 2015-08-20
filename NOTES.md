Valgrind/Callgrind events profiling:
------------------------------------

Event data captured using: `valgrind --tool=callgrind --dump-instr=yes ./tis`

Thing done                                |Events captured
------------------------------------------|----------------
*Original:*                                 |8730632
*No RICH_OUTPUT:*                           |
  After cmake (with m linking fix):       |8729470
  After cmake (no m linking):             |8701013
*After cmake (no m linking):*               |
  Dispatch goto-by-val (before de-cruft): |8700041
  Dispatch goto-by-val (after de-cruft):  |8631005
*Dispatch goto-by-val (after de-cruft):*    |
  Added m linking back (1):               |8659462
*Add -O2 to CFLAGS*                         |5070865

(1) Added libm link back else it wouldn't be true to the original compile.
