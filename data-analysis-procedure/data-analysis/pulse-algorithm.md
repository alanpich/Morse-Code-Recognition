---
title: Pulse Algorithm
layout: page
---

Due to the wide separation between DOT and DASH time durations, and the small variance of these durations, a linear decision boundary can easily be established as a function of DOT and DASH averages. However, to allow for slowly changing transmission rates, and to suppress temporarily large excursions from the mean, individual DOT and DASH averages must be calculated on a floating basis. That is, the averages must be computed for the last N DOTs and DASHes received, rather than on all received since the start of Morse code processing. The optimum size of N is that which both suppresses large excursions and permits the average to follow slowly varying changes. A value of eight achieves these goals and, as discussed below, permits easy average computation on the PDP-12 computer.

The DOT average is computed by the following equation:

![fig-3.1]

When a newly received pulse is identified as a DOT, the DOT average is recomputed to include the new time duration information. The division  process is performed by shifting the 12-bit register, containing the quantity to be divided, three places to the right. This is the equivalent 3 of dividing the quantity by 2 or 8. The use of this process eliminates the time consuming task of adding 8 registers together and then dividing by 8. The DASH average is computed in the same manner as the DOT average. The pulse average is computed after each recomputation of either the DOT average or the DASH average by the following equation:

![fig-3.2]

The pulse average is used as the pulse time duration linear decision boundary. Note that the pulse average is not the mean of the DOT and DASH averages, but is instead, slightly closer to the DOT average. This adjustment compensates for the difference between DOT and DASH time duration variances. The resulting pulse decision boundary lie? Nearly in the center of the gap between DOT and DASH time duration clusters* If a new pulse has a time duration greater than the pulse average, it is considered to be a DASH; otherwise it is a DOT. Recomputation of the pulse average after receipt of each DOT and DASH permits the threshold to adjust to slowly varying  changes as they occur.

The DOT and DASH averages are influenced most by the DOT-SYMBOL and DASH-SYMBOL clusters shown on the data distribution plots. This is due to  the fact that there are proportionately more pulses followed by SYMBOL spaces than followed by CHARACTER or WORD spaces. Since the DOT and DASH time duration variance is smaller in these clusters, especially in the DASH-SYMBOL cluster, the resulting pulse average, as determined by equation (3.2), lies more near the center of the gap between the two clusters, thereby providing a better linear decision boundary.


[fig-3.1]: {{site.baseurl}}public/figures/3.1.png  "Figure 3.1"
[fig-3.2]: {{site.baseurl}}public/figures/3.2.png  "Figure 3.2"
