---
title: Signal Processing Section
layout: page
---

The Signal Processing section, as previously mentioned, serves to  transform the received analogue Morse code signal into pulse and space time .  duration information for use in the Code Translation section. If the  received signal were completely clean and interference free, this transformation  would be relatively easy* However, the transformation becomes  rather difficult when the effects of noise and signal fading are considered. The main purpose, then, of the Signal Processing section is to recognize  the Morse code transmission under realistic conditions of signal fading  and distinguish it from pulse interference and "white" noise. The  methods used to achieve these tasks will now be discussed.

The incoming pulse-modulated signal is first converted into dc  pulses, corresponding to the Morse code being received, by a full-wave  bridge rectifier and RC filter. The input signal voltage level is sampled  periodically (approximately once every 200 microseconds) and compared to  a threshold voltage level. If the input signal is less than the threshold  level, a -1 is stored; if the input signal is greater than the threshold  level, a +1 is stored. The effects of signal fading may be reduced by  proper settings of the input signal voltage and threshold level.

A low pass digital filter technique is employed to limit the effects  of noise on the input signal. Rather than base the pulse-space decision  on whether the input signal level is above or below the threshold level  for any one particular sample, the average of several of the samples must  be above or below the threshold before a pulse-to-space or space-to-pulse change is detected.

When an input signal level change is detected, it is checked again  to determine if the change is permanent. The checking process is similar  to the change detection process, except that twice as many samples are  averaged. If the checking process result confirms the input signal change,  then the signal is considered to have changed permanently. The time  duration of the just-ended pulse or space is then obtained from the realtime  clock counter and the clock is reset to begin timing the next pulse  or space. If the result of the checking process conflicts with the change  detection process, then the input signal change was due to interference  rather than a valid Morse code input. In this case, the change detection  process is repeated, again looking for an input signal level change.

When a valid input signal change is detected, the pulse or space  time duration is stored in a 200g-word memory buffer. Previously stored  time durations are retrieved from the buffer as needed by the Code  Translation section for processing. The 200g-woru buffer permits the  Code Translation section to temporarily lag behind the Signal Processing  section without loss of Morse code signal information.

This method of storage and retrieval of Morse code time durations  presents an operational limit to the overall recognition program in that  it is possible to over-write previously stored time-durations before the  Code Translation section processes them. If the interrupts occur too  frequently, not enough time will be available for the Code Translation  section to keep up with the storage of new time durations, a function of  the Morse code transmission speed. Thus, the interrupt frequency upper  limit is determined by the execution time of the Cod« Translation section.  Fortunately, this presents no real problem to the overall recognition program, since the upper limit is well above the minimum input signal  sample frequency needed to ensure proper detection of Morse code signal  changes.

The Signal Processing section is divided into two separate routines:
1. the Signal Sampling routine (Fig. 4-4)
2. the Change Detection routine (Fig. 4-5).
The particular function of these routines is discussed in the following paragraphs.

## Signal Sampling routine
The Signal Sampling routine performs the  actual sampling of the Morse code input signal. If the sampled input  voltage is greater than the threshold level, a +1 is stored. If the  sampled input voltage is less than the threshold level, a -1 is stored.  If N' samples have not been taken yet, program operation is returned to  the Code Translation section through the Service program. When the N'th sample is taken, program operation continues in the Change Detection  routine.
