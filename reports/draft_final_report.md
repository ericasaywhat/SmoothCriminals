# Smooth criminals: agent-based modeling of street crime

Erica Lee and Emily Yeh

## Abstract

We design and implement an agent-based model of citizens in a simulated world we call CrimeWorld, where each citizen has their own characteristics and behavioral rules, including the citizen’s likelihood of committing crimes. This version of CrimeWorld includes clearly visible police which deter criminals. Comparing our results to those of Groff in her report, *Simulation for theory testing and experimentation*, we observe that our results behave qualitatively similarly. We then extend Groff's experiment by implementing a CrimeWorld with punishment for committing crimes. This CrimeWorld includes undercover police, who punish criminals if they catch them by taking away a large proportion of their wealth, thereby affecting their motivations to commit crimes. This experiment is still in progress, but our hypothesis is that the rate of crime will increase in this version of CrimeWorld, which is counter-intuitive since punishment is typically intended to lower the rate of crime.

## Introduction

The idea behind routine activity theory (RAT) is that if the frequency of convergence between offenders, guardians, and targets increases, crime rates may increase even if the absolute number of motivated offenders remains constant. We'll explore RAT by simulating many agents called Citizens inside of a series of nodes called CrimeWorld.

In our simulated world, our agents are Citizens. These Citizens can have a variety of roles: some are offenders (agents who commit crimes), some are police (agents who prevent crimes), and some are targets (agents against whom crimes are committed).

### Deciding to commit crimes

According to Groff's experiment<sup>2</sup>, a variety of factors affect an offender's decision to commit a crime. Consider several agents at a single node; some might be police and some might be offenders trying to find a target. The first factor the offenders must consider is whether there are police at the node. No crimes may be committed in the presence of a police officer. If there are no police officers, however, the offenders must consider several other factors, which are summarized in Figure 1.

![decision tree](https://github.com/ericasaywhat/SmoothCriminals/blob/master/reports/decision_tree.png)

*Figure 1. An offender's decision tree<sup>2</sup>; how an offender decides whether to commit a crime.*

As Figure 1 indicates, if there are no police officers in a node, the second factor the offenders must consider is the guardianship of other agents present - a variable represented by `G`.

#### `G = (N`<sub>agents</sub>` - 2) + P`

`G` depends on two other variables. `N`<sub>agents</sub> is the total number of agents present at a given node, and we subtract 2 to account for the offender and their potential target. `P` is a randomly selected number between -2 and 2 that represents the offender's perception of the capability of the guardians who are present. If `G < 1`, the offender determines that there are not capable guardians present, so they should commit the crime. If `G == 1`, the offender isn't sure if there are capable guardians present, so they make a random decision to commit the crime. And finally, if `G > 1`, the offender determines that there are capable guardians present and they should not commit the crime.

Now, let's assume `G <= 1` and the offender has decided to commit the crime. Which agent should the offender offend? The offender finds the wealthiest person in that node and robs that person.

The figures below show our simulation's results as a distribution of robberies across CrimeWorld. (We need to write interpretations for these results, and we will definitely do so for the final report.)

![100 steps](https://github.com/ericasaywhat/SmoothCriminals/blob/master/reports/1000_100.png) ![200 steps](https://github.com/ericasaywhat/SmoothCriminals/blob/master/reports/1000_200.png) ![300 steps](https://github.com/ericasaywhat/SmoothCriminals/blob/master/reports/1000_300.png)
![400 steps](https://github.com/ericasaywhat/SmoothCriminals/blob/master/reports/1000_400.png) ![500 steps](https://github.com/ericasaywhat/SmoothCriminals/blob/master/reports/1000_500.png) ![600 steps](https://github.com/ericasaywhat/SmoothCriminals/blob/master/reports/1000_600.png)

*Figure 2. The distributions of robberies across CrimeWorld for 100, 200, 300, 400, 500, and 600 steps.*

| I   | J   | Mean Difference (I - J) |
| --- | --- | ---                     |
| 0.3 | 0.4 | -4.73                   |
| 0.3 | 0.5 | -10.91                  |
| 0.3 | 0.6 | -15.42                  |
| 0.3 | 0.7 | -19.78                  |
| 0.4 | 0.5 | -6.19                   |
| 0.4 | 0.6 | -10.69                  |
| 0.4 | 0.7 | -15.05                  |
| 0.5 | 0.6 | -4.51                   |
| 0.5 | 0.7 | -8.86                   |
| 0.6 | 0.7 | -4.36                   |

*Figure 3. Comparison of the average number of robberies per node for different percentages of time away from home.*

![cumulative robberies](https://github.com/ericasaywhat/SmoothCriminals/blob/master/reports/cumulative_robberies.png)

*Figure 4. The cumulative number of robberies over time.*

![rate of robberies](https://github.com/ericasaywhat/SmoothCriminals/blob/master/reports/rate.png)

*Figure 5. The rate at which the number of robberies increased over time.*

### A CrimeWorld full of punishment

Our version of CrimeWorld as implemented according to Groff's experiment does not include punishment for committing crimes. When an offender decides whether to commit a crime in a node, they also consider whether there are any police agents in the node. If so, the offender simply does not rob anyone. We propose a version of CrimeWorld where offenders do get punished if they are caught committing crime. We hypothesize that this version of CrimeWorld will result in higher crime rates and more overall crimes committed. In this CrimeWorld full of punishment, we increase the motivation of offenders who commit crimes successfully and decrease the motivation of offenders who are caught while committing crimes.

(This experiment isn't done yet, but we're going to generate some nifty figures and things for the final report when it is.)

## Annotated Bibliography

**1. Cohen, Lawrence E., and Marcus Felson. ["Social change and crime rate trends: A routine activity approach."](http://www.jstor.org/stable/2094589) American sociological review (1979): 588-608.**

Cohen and Felson introduce the idea of routine activity theory in which they state that crime is not affected by social causes such as poverty or unemployment. They focus on the circumstances under which an individual carries out a crime. During their time, the conventional theories of crime was unable to explain why crime rates increased post World War II since the economy was on the rise. Their routine activity theory states that there was more crime post WWII since people were generally more wealthy and there was more to steal.

**2. Groff, Elizabeth R. ["Simulation for theory testing and experimentation"](https://link.springer.com/article/10.1007/s10940-006-9021-z): An example using routine activity theory and street robbery." Journal of Quantitative Criminology 23.2 (2007): 75-103.**

This paper presents a new approach to testing the routine activity theory. The routine activity theory is a criminology subfield developed by Marcus Felson and Lawrence E. Cohen. Routine activity theory is based on the premise that crime is committed regardless of social causes such as poverty, inequality, and unemployment. Some crimes that are well modelled by routine activity theory is copyright infringement, peer-to-peer file sharing, corporate crime, etc. The author of this paper, Elizabeth R. Groff, uses agent-based modelling to model street robbery since it involves the interaction of agents in a public place and is driven by economic gain, making it more of a rational decision than a crime such as assault. A wide variety of studies from surveys of individuals to macro and micro level data to represent routine activity in society. However, all of these studies struggled with separating constructs and accurately replicating crime patterns. Rather than the usual top-down approach, agent-based modelling is a bottom up approach that starts with individuals with characteristics and behavioural rules already implemented. This model introduces a new framework for more complete and rigourous tests of theories. It clearly supports the possibility of the basic premise of routine activity theory.

**3. Malleson, Nick, Heppenstall, Alison, and See, Linda. ["Crime reduction through simulation: An agent-based model of burglary"](http://www.sciencedirect.com/science/article/pii/S0198971509000787). Computers, Environment and Urban Systems Volume 34, Issue 3 (2010): 236-250.**

Malleson et. al. introduce a model in which they simulate burglaries that happen within an environment where the burglars' need to acquire wealth fluctuates with their need to sleep (so it decreases when they are tired and increases after they sleep). The authors find that burglary rates increase in certain areas in their model, leading them to suspect that if these areas had increased security, the rates of burglaries would decrease. Altering the security in different environments produces different burglary rates and community types within 50 days (according to the simulation's timeline). We think that this article would provide an interesting basis for an extension to Groff's experiment, in which we might implement exhaustion as a property of crime-committing agents and simulate areas with higher or lower security to observe how these agents behave under varying circumstances.

**4. https://Data.lacity.org/Api/Views/y8tr-7khq, 19 Apr. 2017.**

This is data on the crime in the city of Los Angeles from 2010 to 2017. It is compiled by the LAPD and is currently available on the city website.


