This is the real mess.

External Interfaces
-------------------
* Input from program_memory
* Output to program_counter
* Input from input
* Output to output (technically it also inputs it when recreating *m)
* Output to memory_cell
* Input from memory_cell.non_zero
* Output to memory_address
* Input from clock (redistributed to the surrounding stuff)

External blocks
---------------
* Program
* Memory
* Input
* Output
* Clock

Internal States
---------------
* Searching forward "[" :: Bool
* Searching backward "]" :: Bool
* frame_count, count to match brackets :: Integer
* Reading input "," (with luck could be inferred from *pc)  :: InferedBool
* Writing output "." (with luck could be inferred from *pc) :: InferedBool

Looping
-------

    *pc=="[":
        *m==0:
            search matching bracket forward, pc++
        else:
            pc++
    *pc=="]":
        *m==0:
            pc++
        else:
            search matching bracket backwards, pc++


Searching
---------
* Disable operations whilst searching
* Handle frame_counter to find matching braket

frame_counter
-------------
* +/- # *pc=="["/*pc=="]" or vice versa (depending on direction)
* (/=0) to check exit search

{8-bit binary counter with 8-input OR} will do
