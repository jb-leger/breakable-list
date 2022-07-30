A breakable list
================

Build a list from a iterable, breakable by KeyboardInterrupt (SIGINT), and
monitorable by SIGUSR1 and SIGUSR2.

The function `breakable_list` act as list() constructor, and build a list from
an iterable, except:
  - When a SIGINT (CTRL-C, KeyboardInterrupt) is received, the construction
    is stopped, and the current list is returned.
  - When a SIGUSR1 is received, the last item is pickled in a file, and the
    construction of the list continues.
  - When a SIGUSR2 is received, the current list is pickled in an file, and
    the construction of the list continues.
