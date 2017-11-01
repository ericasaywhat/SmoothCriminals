# Agent-based modelling: a new way to model of street robbery
Erica Lee and Emily Yeh

## Abstract
We will be making an agent-based model of the citizens of Los Angeles, each with its own characteristics and behavioural rules. Depending on the behavioural rules, the nodes will or will not commit street robbery. We will be using the dataset on crime from the city of Los Angeles. Comparing our results to those of Groff's in her report, *Simulation for theory testing and experimentation*, will yield differences between the crime in LA and the crime in Seattle, since her data is based on Seattle's crime reports. We will then extend Groff's experiment by implementing less random movement for criminal agents, and instead, base their movement on simulated employment, housing developments, recreational space relocations, and so on.

## References
**Groff, Elizabeth R. ["Simulation for theory testing and experimentation"](https://link.springer.com/article/10.1007/s10940-006-9021-z): An example using routine activity theory and street robbery." Journal of Quantitative Criminology 23.2 (2007): 75-103.**

This paper presents a new approach to testing the routine activity theory. The routine activity theory is a criminology subfield developed by Marcus Felson and Lawrence E. Cohen. Routine activity theory is based on the premise that crime is committed regardless of social causes such as poverty, inequality, and unemployment. Some crimes that are well modelled by routine activity theory is copyright infringement, peer-to-peer file sharing, corporate crime, etc. The author of this paper, Elizabeth R. Groff, uses agent-based modelling to model street robbery since it involves the interaction of agents in a public place and is driven by economic gain, making it more of a rational decision than a crime such as assault. A wide variety of studies from surveys of individuals to macro and micro level data to represent routine activity in society. However, all of these studies struggled with separating constructs and accurately replicating crime patterns. Rather than the usual top-down approach, agent-based modelling is a bottom up approach that starts with individuals with characteristics and behavioural rules already implemented. This model introduces a new framework for more complete and rigourous tests of theories. It clearly supports the possibility of the basic premise of routine activity theory.

**https://Data.lacity.org/Api/Views/y8tr-7khq, 19 Apr. 2017.**

This is data on the crime in the city of Los Angeles from 2010 to 2017. It is compiled by the LAPD and is currently available on the city website.

## Experiments

We will replicate Groff's experiment by designing our own agent-based model with agents that have characteristics and behavioral rules similar to those of the agents in Groff's experiment. Groff uses data about street crimes in Seattle, so her results might differ from ours, which will be based on data about street crimes in Los Angeles - we will comment on the differences and generate graphs that help demonstrate these differences more clearly.

In addition, Groff suggests that her experiment could be improved in various ways. For example, in her model, citizens travel randomly throughout Seattle, but in reality, they might relocate because of new employment opportunities, new homes, new recreational spaces, and so on. If we can come up with a way to incorporate ordered relocation of our crime-committing agents, we might be able to design a model with results that are much closer to those of the real world.

## Methods of Analysis

We will use agent-based modeling to create our models, where each agent will have a set of characteristics and behavioral rules. An agent's decision to offend (DTO) will be based on a number of factors, as specified in Groff's paper: whether a police agent is at a given node, whether a guardian agent is at a given node, whether a suitable target can be identified (based on the potential targets' wealth), and a random decision about whether other capable guardians are present. Like Groff's model, we will start off with 1000 agents, of which 200 are police. We will take the rest of the constants from the LAPD dataset, such as the percentage of the population that has committed a crime, unemployment rates, and wealth values for each citizen.

## Causes for Concern

We don't know how difficult it will be to model the agents. We do already have data, which should help, but we think it will take a lot of adjustments to get our model working. We may also have trouble comparing Groff's results with our results, since the crime in Seattle and LA might be very different.

## Next Steps

We will work on replicating Groff's experiment first by creating our agents and setting their behavioral rules. It probably would not make sense to split up for this step, since we don't think there are multiple discrete subtasks for this step, so we will work on the replication together.
