---
title: Code Translation Section
layout: page
---

The Code Translation section converts the stored pulse and space  time duration information produced by the Signal Processing section into  a printed copy of the received Morse code message. This section is  composed of six routines: 1) the Initialization routine, 2) the Data  Recognition routine, 3) the Internal Code Generation routine, 4) the '  Character Identification routine, 5) the Word Space Correction routine,  and 6) the Error Correction routine.

Recognition program operation begins in the Code Translation section.  Pulses and spaces are identified by comparing the time duration of a  particular pulse or space to the average of past pulses and spaces.  Before any decisions can be made in this manner, some a priori knowledge  of the particular averages must be obtained. The Initialization routine  provides this knowledge by examining the first 49 pulses received, in a  two-step process. The acquired knowledge is then used to start the  recognition process, commencing with the first pulse or space received.  As subsequent pulses and spaces are processed, the averaging information  is constantly updated to adjust to changes in Morse code sending rates.

Pulses retrieved from the 200g-word memory buffer are compared with  the pulse average. If the time duration of the new pulse is greater than  this average, it is classified as a DASH, otherwise.it is a DOT. The  receipt of a DASH is noted by storing a 1 in a word register. A 0 is  stored in the word register to indicate the receipt of a DOT. The  number of pulses received is recorded by incrementing a number register.

Spaces are classified in a two-step process. First, the time duration  of the space in question is compared with the SYMBOL space boundary value.  If the time duration is less than this boundary value, the new space is classified as a SYMBOL space. If the time duration is greater than the  boundary value, the new space is either a CHARACTER or a WORD space.  The second step of the space classification process is then used to  make this distinction. The time duration of the new space is compared  with the CHARACTER-WORD space boundary value. If the time duration is  less than this value, the new space is classified a' a CHARACTER space;  otherwise it is classified as a WORD space.

When either a CHARACTER space or a WORD space is identified, the  contents of the word and number registers are combined to yield a unique  internal code word representing the received Morse code character. This  internal code word is then compared with a list of internal code words  stored in memory. The corresponding ASCII Teletype code is identified  and used to print the character. A list of internal code words is  presented in Appendix C.

When the internal code word cannot be identified as a valid code  word, an error correction process is initiated. This process, when  possible, corrects two types of errors« 1) the inclusion of an extra  pulse in the code word due to noise in the received Morse code signal, and  2) the joining of two Morse code characters caused by too small a space  separating the characters. In the first case, pulses having a time  duration less than one-half of the current DOT average are eliminated.  The internal code word is then recomputed and the valid character is  identified. If no pulses can be eliminated in this process, the second  case is considered. The largest SYMBOL space in the. invalid code word  is reclassified as a CHARACTER space. Two new internal code words are  generated from the invalid code word and reprocessed*. If either of the  ^ corrected internal code words is still invalid, a special error symbol is printed to indicate receipt of an unidentifiable Morse code character.

Recognition of a WORD space causes the Teletypewriter to skip a  space, thereby forming words rather than an endless string of transmitted  characters. However, the overlap of CHARACTER and WORD space time  durations, as shown in Chapter III, causes some CHARACTER spaces to be  erroneously classified as WORD spaces. In order to limit the number of '  erroneous classifications, a separate routine is used to re-evaluate  WORD spaces following the letters I, J, Q, U, V, and Z. The occurrence  of these letters as the last letter of an English language word is highly  unlikely, although not impossible. This routine compares the time duration  of the space in question with a slightly larger boundary value. If  the time duration is greater than this new boundary value, the space is  classified as a CHARACTER space. The readability of the printed message  is greatly improved through the use of this technique.

Discussion of the particular functions performed by each of the  six routines contained in the Code Translation section is now presented  in the following paragraphs.










