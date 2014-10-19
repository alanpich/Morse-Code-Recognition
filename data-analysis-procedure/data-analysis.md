---
title: Data Analysis
layout: page
---

The individual and combined distribution cluster plots for the
three recording sessions were examined to identify any possible relationships
that might be used in the recognition program. Several such
relationships were found.

It was immediately obvious that some of the pulse and following space categories are essentially identical and can be combined into one Unique  Category. The First and Intermediate categories for both DOTs and DASHes  Are identical, as are the Only and Last Character categories. Thus, the 10 Original categories can be reduced to 6 categories, 3 for each type of pulse. These three categories correspond to the type of   following space, i.e., SYMBOL, CHARACTER, and WORD.

Another obvious trait disclosed by the data plots was the large variance of CHARACTER and WORD space time durations. Since the plots represent data obtained over an extended period of time (approximately 10-15 minutes)  it was thought possible that the large variance was due to a gradual change in transmission speed during the time interval. To investigate this possibility, plots of pulse and space durations versus their sending sequence in time were made for the DASH Intermediate, Last Character, and Last Word categories. These plots, two of which are included in Appendix B (Figures B-14 and B-15), indicate that the large variance is not a function of a general speeding-up or slowing-down trend, but is, in fact, a characteristic of hand-sent Morse code. Examination of the data plots for all categories combined indicates that a large overlap exists between CHARACTER space and WORD space time durations.

The existance of this overlap prohibits correct identification of CHARACTER spaces versus WORD spaces on a time duration threshold basis. However, this distinction is not a critically important one, since both types of spaces signify the end of a Morse code character. The combined category data plots do, however, indicate a wide gap between SYMBOL space and non-SYMBOL space clusters. These gaps lend themselves to the formation of linear decision boundaries in two-dimensional pattern space quite easily.

Another obvious condition revealed by the combined data plots is the wide gap between DOT and DASH time durations. This again is conducive to a linear decision technique.
The combined data plots reveal two distinct correlations between
DASH time durations and the type of following space. The first, and most obvious of the two is that DASH time durations are generally longer when followed by a CHARACTER or WORD space than they are when followed by a SYMBOL space. The second correlation is that SYMBOL space durations tend to decrease as the time duration of the preceding DASH increases, and vice versa. Neither of these pulse-space correlations are evident in the DOT-space categories.

As discussed earlier in Chapters I and III, several different types of decision algorithms have been successfully used to recognize hand-sent Morse code. Most notable among these are the use of a unique set of linguistic rules and the comparison of the time duration of the previous pulse with that of the next space and pulse on a threshold decision basis. A different approach to the recognition problem was looked for in this project; one that might prove more successful than those methods previously tried.

Evaluation of all the observations made from the data distribution plots led to the derivation of pulse and space linear decision algorithms, based on time  duration averages, for use in the recognition program. These algorithms are discussed in the following paragraphs.

