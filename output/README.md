Requirements
------------
* Hold the state for the 8-bit output
* Rendering it possible to set the memory value to output (will be handled by the central logic)

8 gated D-latches one for each bit to hold the output 8-bit state and interface with the output. (Should preferably handle normal output currents otherwise an extra driver layer must be added)
One 8-bit counter to hold the state while sampling it to output via the D-latches and then move that value back

    { # central logic context
        while(*m--) output_counter++  # output_counter=*m; *m=0;
    }
    sample output_counter to output via D-latches
    decouple output_counter from D-latches
    { # central logic context
        while(output_counter--) *m++  # *m=output_counter; output_counter=0;
    }
