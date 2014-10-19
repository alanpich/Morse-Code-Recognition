---
title: Operational Goals
layout: page
---

It goes without saying that the overall  operational goal is accuracy. The output of the computer recognition  program should exactly reproduce the hand-sent Morse code transmission.  But by what measure should the accuracy of the program be evaluated?  Should the program output be compared with that which a human would  interpret as the transmitted message? Or should it "be based strictly on  the quality of the received code, as compared to the standards for Morse  code language? Both evaluation criteria merit consideration. Further  discussion of this topic is presented in Chapter VI.

Three operational goals are specified for the computer recognition program. These are:

1. The program must be able to process the received Morse code transmission in real-time.
2. The final program must occupy less than 4K of memory space.
3. The program should be designed to lend itself to construction of a small, low-cost hardware realization, i.e., a special purpose minicomputer.


These goals are somewhat interrelated. If the recognition program  cannot process the received Morse code in real-time, a memory storage  unit is required to save the received signal until it can be processed,  thus requiring additional core space. In this case, the size of the  memory will determine the maximum length message that could be processed  at any one time. The real-time constraint eliminates this problem.

The 4K memory limitation was chosen to permit implementation of the  program within one basic unit of memory. Thus, the recognition program  can be implemented on the basic PDP-12 or similar minicomputer.

Construction of a hardware realization of the recognition program  is of particular interest at the Air Force Institute of Technology. Aside  from obvious educational benefits, construction of a low cost, portable  Morse code recognition machine has many military and civilian applications.  Proper choice of computer instructions, along with compliance to the  aforementioned goals, will result in a minimum number of components  necessary to construct a hardware realization.
