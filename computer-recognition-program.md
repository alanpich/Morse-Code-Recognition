---
title: The Computer Recognition Program
layout: page
---

This Chapter describes the operation of the computer recognition program. The program consists of two distinct but interdependent parts: 1) the Signal Processor section, and 2) the Code Translation section. Discussion of the routines contained within each section is presented in an order indicative of the overall organization of the recognition program and the sequence in which the routines are executed. General flow charts are included for each routine to supplement the associated text.

A discussion of the programming constraints due to the physical limitations of the PDP-12 computer and the self-imposed operational goals is presented at the beginning of this chapter. It is hoped that knowledge of these limitations will enable the reader to better understand the rationale behind various operations performed within the program. A complete program listing with comments is provided in Appendix A.



## Program Constraints ##
Before ideas can be constructively transformed into computer programs, the operational characteristics of the particular computer system to be used must be defined. A list of operational goals and performance objectives must also be defined to optimize the programming process.


