# Leak report

  In the world of c, and other programs of the sort there is a memory management that is not quite on par with other newer anguages. Unlike other types of programing languages that have a more automatic approach to cleaning up memory. When the free() call is not placed into function. Then if it’s a looping call, or is acted upon every time the function that moves through a giver set of variables it will create an allotment in the working ram.

  This allotment unless removed will continue to exist in the working system ram, and since this level is finite it will eventually fill up to the point of causing system slow down or even failure. For instance we can allocate say 4 bits per letter but our system can only handle 40 bits at max it could handle 10 letters but if we don’t free up that space it will only be able to handle 10 letter until the system either locks up or will no longer run unless free() is used in order to free up space and the freed memory is able to be accessed again.

  In this instance the leak was easily identified since there was no free() command. One of the key parts was to know where to put it. Since if it was in the allocate area it would crash the program. But I found that nesting it after the is clean area right before the return allowed the program to run, and checking if the item existed in (cleaned) and if so freed up the space.
