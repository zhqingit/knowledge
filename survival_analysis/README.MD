# Notes of the survival analysis (SA)

Copyright: Qing Zhang

Author: Qing Zhang

Create date: 05/04/2023

Last update: 05/05/2023

## Introduction
This is the note about learning papers<sup>\[1,2,3,4\]</sup>,

## Types of the 'event'
In medical studies, the event can be time to death, or the time between response to treatment and recurrence or relpase-free survival time.

## Concepts
### Censoring
- right censoring:
    The  event  (assuming it were to occur) is beyond the end of the follow-up period.
- left censoring: 
    The presence of a state or condition but do not know where it began
- interval censoring: 
    The individuals come in and out of observation
### Survival
- survival probability *S(t)* (survival funciton):
    The probability that an individual survives from the time origin (e.g.diagnosis of cancer) to a specified future time *t*
- hazard *h(t)* or *$\lambda$(t)*:
  The probability that an individual who is under observation at a time *t* has an event at that time

  The hazard relates to the incident (current) event rate, while survival reflects the cumulativenon-occurrence

## Kaplan-Meier survival estimate
   $S(t_j) = S(t_{j-1})(1-d_j/n_j )$ 

   where $d_j$  is the number of events at $t_j$ and $n_j$ is the number of patients alive just before $t_j$; $t_0 = 0$ and $S(0)=1$. 

   The value of $S(t)$ is constant between times of events, and therefore the estimated probability is a step function that changes value only at the time of each event. 

## Hazard and cumulative hazard
   $h(t) = -\frac d d_t[logS(t)]$

   $H(t) = - log[S(t)]$

   The cumulative hazard $H(t)$ is defined as the integral of the hazard, or the area under the hazard function between times 0 and t because $h(t)$ is not easy to estiamte.

## Nonparametric tests comparing survival
### logrank test
The logrank test is used to test the null hypothesisthat there is no difference between the populations in the probability of an event (here a death) at any time point.
### Comparison
$X^2 = \sum\limits_{i=1}^{g} {(O_i-E_i)^2 \over  E_i}$

where $E_i$ represents the total expected number of events in the group $i$; $O_i$ represents the observed number of events in group $i$;

The value $X^2$ is compared to a $\chi^2$ distribution with ($g$-1) degrees of freedom, where $g$ is the number of groups.

The $E_i$ can be caculated by firstly getting the event ratio using the data from all groups, then multiply the total patients in group $i$. See the example in paper<sup>2</sup>.
### Hazard ratio (HR)
$HR = {O_1/E_1 \over O_2/E_2}$

The hazard ratio (HR) is a measure of the relative survival experience in two groups.

## Some key requirements fr the analysis of survival data
### Censoring
- Uninformative censoring:
 censoring  carries  no  prognosticinformation about subsequent survival experience;
- Informative censoring
when patients withdraw from a clinical trial because ofdrug toxicity or worsening clinical condition

    Standard methods used to analyse survival data with censored observations are valid only if the censoring is ‘noninformative’. 

### Length of follow up
### Completeness of follow up
### Cohort effect on survival
### Between center difference

## References

1. Clark TG, Bradburn MJ, Love SB, Altman DG. Survival analysis part I: basic concepts and first analyses. Br J Cancer. 2003 Jul 21;89(2):232-8. doi: 10.1038/sj.bjc.6601118. PMID: 12865907; PMCID: PMC2394262.
2. Bland JM, Altman DG. The logrank test. BMJ. 2004 May 1;328(7447):1073. doi: 10.1136/bmj.328.7447.1073. PMID: 15117797; PMCID: PMC403858.