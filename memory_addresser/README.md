Requirements
------------
* Up/down the address
* Single-out the choosen memory_cell
* Enableable

Up/down N-bit binary counter to hold address state and handle state changes. (Must also have enable pin)
1-to-N multiplexer to single-out/activate a memory_cell and N-to-1 demultiplexer for its corresponding non-zero signal.
The address from the counter is feed into the address of the multiplexer.

    multiplexer_input = memory_active  #the entire memory is considered active (the address will decide which one of the cells gets activated)
    counter_enable = "<>"

The memory cells will all share +/-.

Investigation
-------------
