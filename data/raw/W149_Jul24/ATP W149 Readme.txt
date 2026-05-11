PEW RESEARCH CENTER
Wave 149 American Trends Panel 
Dates: July 1 - 7, 2024
Mode: Web and CATI
Sample: Full panel
Language: English and Spanish
N=9,424

***************************************************************************************************************************
NOTES

This dataset contains the variables corresponding to questions asked in the survey. It also contains administrative data, such as the main production weight and completion date. There are several types of additional variables that we can typically provide upon request, if they were created for published reporting: 
(1) Researcher-created variable(s) reflecting how we categorized responses to open-ended questions. We do not release verbatim answers to open-ended questions, in the interest of protecting panelist anonymity.
(2) Researcher-created variables needed to replicate published analysis (e.g., an index using several questions).
(3) Special weights needed to replicate published analysis. The main production weight is included in the public dataset. Special weights refer to those used for unusual, bespoke analysis. We can provide existing special weights upon request so long as the analysis they support does not pose a risk to panelist anonymity.

For a small number of respondents with high risk of identification, certain values have been randomly swapped with those of lower risk cases with similar characteristics.

HORSE_W149
The W149 dataset contains the HORSE_W149 created variable indicating 2024 presidential vote preference.

VOTEGEN_W149/ VOTE_MOTIV_W149/ VOTEHOW_W149/ RPLC_W149
In the dataset, VOTEGEN_W149, VOTE_MOTIV_W149, VOTEHOW_W149, and RPLC_W149 are filtered on those who say they are registered to vote (F_REG=1).


***************************************************************************************************************************
WEIGHTS 


WEIGHT_W149 is the weight for the sample. Data for all Pew Research Center reports are analyzed using this weight.


***************************************************************************************************************************
Releases from this survey:

July 11, 2024, "Amid Doubts About Biden’s Mental Sharpness, Trump Leads Presidential Race"
https://www.pewresearch.org/politics/2024/07/11/amid-doubts-about-bidens-mental-sharpness-trump-leads-presidential-race/

July 19, 2024, "How Latino voters view the 2024 presidential election"
https://www.pewresearch.org/short-reads/2024/07/19/how-latino-voters-view-the-2024-presidential-election/

July 29, 2024, "War in Ukraine: Wide Partisan Differences on U.S. Responsibility and Support"
https://www.pewresearch.org/politics/2024/07/29/war-in-ukraine-wide-partisan-differences-on-u-s-responsibility-and-support/

August 1, 2024, "Many Americans are confident the 2024 election will be conducted fairly, but wide partisan differences remain"
https://www.pewresearch.org/short-reads/2024/08/01/many-americans-are-confident-the-2024-election-will-be-conducted-fairly-but-wide-partisan-differences-remain/

August 8, 2024, "Favorable views of Supreme Court remain near historic low"
https://www.pewresearch.org/short-reads/2024/08/08/favorable-views-of-supreme-court-remain-near-historic-low/

August 12, 2024, "Americans see many federal agencies favorably, but Republicans grow more critical of Justice Department"
https://www.pewresearch.org/short-reads/2024/08/12/americans-see-many-federal-agencies-favorably-but-republicans-grow-more-critical-of-justice-department/


***************************************************************************************************************************
SYNTAX

**HORSE variable syntax**

compute HORSE_W149 = $sysmis.
do if F_REG=1.
if (VOTEGEN24_W149=1 or VOTEGEN24_LEAN_W149=1) HORSE_W149 = 1.
if (VOTEGEN24_W149=2 or VOTEGEN24_LEAN_W149=2) HORSE_W149 = 2.
if (VOTEGEN24_W149=3 or VOTEGEN24_LEAN_W149=3) HORSE_W149 = 3.
if (VOTEGEN24_LEAN_W149=4) HORSE_W149 = 4.
if (VOTEGEN24_LEAN_W149=99) HORSE_W149 =99.
end if.
VARIABLE LABELS HORSE_W149 'Combined horserace variable for W149'.
VALUE LABELS HORSE_W149 1 'Trump/Lean Trump' 2 'Biden/Lean Biden' 3 'Kennedy/Lean Kennedy' 4 'Lean toward none' 99 'Refused VOTEGEN24_LEAN'.
EXECUTE.



