---
title: Data Analysis Procedure
layout: page
---

Many possible decision algorithms may be used to recognize hand-sent
Morse code by machine. Indeed, each of the three recognition machines
discussed in Chapter I employs a different method to perform the recognition
process. Since there was no intuitively "best" method to use in performing
this process, a thorough data analysis procedure was undertaken in search
for an "optimal" decision algorithm, i.e., one that would yield the smallest
percentage of recognition errors for all types of Morse code transmissions.
The procedures used to obtain and analyze hand-sent Morse code
data and the decision algorithms derived from this analysis are presented
in the following paragraphs.



Data Gathering
---

Three samples of Morse code transmissions were recorded for analysis.
These samples differ from each other in two ways: 1) the type of sending
unit used, and 2) the degree of operator proficiency. The first sample,
Recording Session 1, was transmitted with a "bug" at a rate of approximately
15 words per minute. Recording Session 2 was transmitted with a hand key
at a rate of approximately 10-12 words per minute. Recording Session 3
was transmitted with a "bug" at a rate of approximately 18-20 words per
minute. The three recording sessions were transmitted by separate individuals
at their normal speed. None of these individuals were, at the time
of the recordings, actively involved in cw (continuous wave) transmissions
as a hobby, although they were at some time in their past. Thus, the
recordings, are biased towards a low-proficiency level. As pointed out in
the next section, this resulted in a slightly erratic sending rate and a
wide spread of pulse and space time durations over a given time period.

The recording sessions were conducted in the following manner. A
500-word text, taken from The Radio Amateur's Handbook (Ref 1:7), was
prepared for use as the message to be transmitted. A copy of this
message, listed in Appendix D, was given to each of three individuals.
While one individual transmitted the message, the other two annotated
observed sending errors on their copy of the text, The Morse code
transmission was recorded for use in the data analysis process. Only
one recording session was held at a time to prevent mental fatigue from
adversely affecting both the sender and the receivers. Recording sessions
were held every other day until complete. The annotated copies of the
transmitted Morse code messages were saved for use in evaluating
recognition program performance, as explained in Chapter VI.



Data Categorizing
---

The recorded hand-sent Morse code transmissions were examined in
a three step process. First, the time durations of pulses and spaces
were obtained and stored on magnetic computer tape. Second, each pulse
and space was identified as belonging to one of twenty different categories
and again stored on magnetic tape. Finally, the categorized pulses and
spaces were plotted for visual examination. Each of these three steps
will now be discussed.


### Analog-to-Digital Conversion

The time duration for each transmitted
pulse and space was obtained and stored through the use of the PDP-12
computer in the following manner. The recorded Morse code transmission
was connected to an A-D Converter external input channel and sampled
periodically. When a change was detected, i.e., pulse-to-space or
space-to-pulse, the time duration indicated on a real-time clock was
recorded and stored. The clock was then reset and the process repeated.

Approximately the first 200 words of each 500-word Morse code transmission
were processed in this manner. Upon completion of this process,
the stored time durations were visually examined and categorized, as
explained next.

### Manual Identification ###
Pulses and spaces were classified into 10 separate categories each. Space
categories were chosen to permit investigation of the pulse vs. following
space interrelations known to exist in hand-sent Morse code. For example,
the time duration of a space, when preceded by a DASH, is generally less
than it is when preceded by a DOT. Thus, space categories correspond
directly to the category of the preceding pulse. Pulses were separated
into five DOT and five DASH categories according to their relative position
within a Morse code character. In this way, time duration vs. position
interrelationships, if any, would be disclosed. The 20 pulse and space
categories are listed in Table 1.

The ONLY category identifies a DOT or DASH that by itself signifies a Morse code character (the characters E and T respectively). A pulse is FIRST if it is the first pulse of at least two pulses comprising a character. Likewise, a pulse is Last if it appears as the last pulse in the character. The LAST CHARACTER and LAST WORD categories are determined by the type of space following the pulse, i.e., CHARACTER space or WORD space. An INTERMEDIATE pulse is one which is neither first nor last in a multi-pulse string. Only category pulses which also appear as the last pulse in a word are categorized as Last Word.

The visual identification process was performed in the following manner. Stored pulse and space time durations were displayed on the PDP-12 CRT Display screen as a series of lines, proportionate in length to the time duration represented, as depictad in Fig. 3-1. A cursor was also displayed to indicate the particular pulse to be categorized. Note that it is only necessary to identify pulses, since spaces are categorized by the type of preceeding pulse. The pulse was then visually identified by noting its relative length and position with respect to surrounding pulses and spaces. The pulse and following space time durations were then stored according to their respective categories by depressing one  of 10 keys on a teletypewriter. Depression of the teletype key also advanced the display to the next pulse to be identified. The process
was continued in this manner until all pulses and spaces were categorized and stored.

### Distribution Plots

Cluster-type distribution plots of the categorized pulses and spaces were obtained by plotting pulse time duration versus following space time duration for the 10 categories. Plots were made of each individual category as well as all categories combined for the three recording sessions. The individual category plots for Recording Session 1 and combined plots for all recording sessions are contained in Appendix B, Figures B-l through B-13.











