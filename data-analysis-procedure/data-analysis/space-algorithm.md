---
title: Space Algorithm
layout: page
---

The wide variance of CHARACTER and WORD space time durations prohibits use of the averaging technique used for the pulse algorithms» The technique was tried, however, with less than desirable results. A threshold was established as the mid-point between the CHARACTER space average and the WORD space average. New spaces were classified as CHARACTER spaces if their time duration was less than the threshold, and as WORD spaces if their time duration was greater than the threshold. Respective space averages were then computed in a manner similar to that used in the pulse algorithm. In test runs of the recognition program, the threshold point was consistently smaller than the optimum value, resulting in many CHARACTER spaces being classified as WORD spaces.

This lower than desired threshold is due to two contributing factors. The first, and most important, is the large overlap of the CHARACTER and WORD space variances. The second factor is the difference in frequency of occurrence of the two types of spaces. CHARACTER spaces, for English language text, occur approximately 4 times as often as WORD spaces. Those CHARACTER space time durations which are slightly greater than the threshold value force the WORD space average to be lower than it actually is. This, in turn, lowers the threshold value, which is defined as the mid-point of the CHARACTER and WORD space averages. The lower threshold causes more CHARACTER spaces to be defined as WORD spaces, thus lowering the WORD space average even more and compounding the problem. The threshold value settles near the true CHARACTER space average, much lower than desired.
The space algorithm finally arrived at for use in the recognition program is based on the average of all non-SYMBOL spaces which follow a DOT. The CHARACTER-WORD space average is calculated as follows:

![fig-3.3]

Figures 3-2, 3-3, and 3-4 illustrate the linear decision boundaries, as determined by the pulse and space algorithms, for Recording Sessions 1, 2, and 3, respectively. Individual pulse-space clusters have been circled on these figures to indicate the size and shape of each cluster and the overlap regions between clusters. Table II lists the type of cluster identified by the letters shown on the three figures.

The pulse average lies in the gap between the DOT and DASH clusters on all three figures. This average value also lies in the gap between the DOT- SYMBOL cluster and the DOT-CHARACTER cluster for Recording Sessions 1 and 2, but not for Recording Session 3. Notice that the DOT-SYMBOL cluster in Fig. 3-4 has a much larger SYMBOL space variance than is indicated on similar clusters shown in Figures 3-2 and 3-3. This large variance is due to a faulty DOT-SYMBOL space generator on the "bug" used to transmit recording Session 3. Therefore, it is assumed that the pulse average value also lies in the correct location for Recording Session 3. The pulse average is therefore used as the linear decision boundary for SYMBOL versus non-SYMBOL space decisions, when the space is preceded by a DOT. Also notice that the CHARACTER-WORD average, computed by equation (3.3), lies in the DOT-CHARACTER and DOT-WORD cluster overlap region.

CHARACTER and WORD spaces, when preceded by a DASH, have shorter time durations than those preceded by a DOT. Therefore, an adjusted boundary value must be used when a space is preceded by a DASH. The adjusted SYMBOL space boundary value is computed as a function of the time duration of the preceding DASH as follows:

![fig-3.4]

The adjusted CHARACTER-WORD space boundary value is computed in a similar manner as follows:

![fig-3.5]

The resulting linear decision boundaries are negatively sloping lines, as shown on the accompanying figures. A maximum DASH time duration is established as twice the current DASH average for use in the boundary computations» thereby setting a lower limit to the threshold value« To permit real-time adjustment of the C-W Boundary, a positive or negative adjustment value, X, is added to the threshold as follows:

![fig-3.6]

By adding the appropriate adjustment value to suit a particular Morse  code transmission, the operator can optimize the readability of the printed output.


[fig-3.3]: {{site.baseurl}}public/figures/3.3.png  "Figure 3.3"
[fig-3.4]: {{site.baseurl}}public/figures/3.4.png  "Figure 3.4"
[fig-3.5]: {{site.baseurl}}public/figures/3.5.png  "Figure 3.5"
[fig-3.6]: {{site.baseurl}}public/figures/3.6.png  "Figure 3.6"

