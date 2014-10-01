Requirements
------------
* Sample the 8-bit input
* Rendering it possible to retrieve this value to memory (will be handled by the central logic)


8-bit presettable syncronous (they always are) binary counter

    preset input_counter to reflect input  # sample
    decouple input_counter from  input
    { # central logic
        [-]  # *m = 0
        while(input_counter--) *m++
    }
