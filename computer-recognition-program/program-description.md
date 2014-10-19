---
title: Program Description
layout: page
---

The recognition program is segmented into two major parts: the Signal Processing section (Fig. 4-1), and the Code Translation section (Fig. 4-2). The Signal Processing section serves to transform the received Morse code analog signal into pulse and space time duration information for use in the Code Translation section. The Code Translation section then uses these time durations tc identify transmitted Morse code characters and print out the message. Detailed discussion of these two sec ions and their associated routines is presented in subsequent paragraphs.

Program operation in either section is controlled by an external  program interrupt. Acknowledgement of a program interrupt is controlled  by the status of an interrupt bus. If the bus is enabled, a program  interrupt will halt current computer execution and transfer operation to  absolute memory location OOOlg in 8 mode or 0040g in LINC mode. If the  interrupt bus is disabled, a program interrupt has no effect on execution.  When a program interrupt is recognized and operation is transferred to the  appropriate location, the interrupt bus is automatically disabled. The  interrupt bus can only be enabled again by specific program instruction.

The interrupt bus is enabled during operation in the Code Translation  section only. When an interrupt occurs, execution in that section is  halted and the Service program (Fig. 4-3) is entered through location  OOOlg or 0040g, depending on the computer mode at the time of interrupt.  In either case, the current accumulator, link, and program counter register  values are saved for use in returning to interrupted program. Signal  Processing section operation then begins and continues until complete,  at which time the Service program is re-entered. Appropriate register  values are restored, the interrupt bus is turned on, and operation again  resumes in the Code Translation section at the pointy of interruption. Operation continues in this section until the occurrence of another interrupt, at which time the process is repeated.




