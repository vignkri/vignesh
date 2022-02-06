---
author: "Vignesh Krish"
date: 2022-02-06
linktitle: foundations of data teams
title: Building Foundations of data teams - Pt. 1
---

Building the foundations of a data team and the data team itself is a struggle.

Complexity seems to be ever increasing and job profiles keep changing rapidly as data and its usage explodes all around us [1]. There are terms such as data-quality, data-lineage, and observability that are used. Then, there are profiles a company needs to hire within its data-team: data scientist, data analyst, data engineer and maybe in the future, an analytics engineer. Or in some cases, do not hire an engineer but a person who likes to work with data [2].

{{< twitter user="ElenaRusAthletx" id="1483651998335614978" >}}

I've been working with different aspects of data, and the more I work, the more I understand that there is a huge gap in what is needed for a very strong data foundation and what actually gets achieved. So, this hopefully sheds some light into some opinions and thoughts I’ve collected over the past year. 

## Premise..

Hopefully, at the end of this post, there is a clarity to what system can be built when building a data team or the foundations of a data team. With this blog post, my primary goal is to answer this simple question:

| What is a solid data team to start with that shall improve the quality of life for that company?

The secondary outcome, I believe to naturally arise out from this premise is the company structure of how it could work [3]. This blog post is for small teams, where to start, how to proceed with building a team over time that is empowered to answer hard questions by looking at internal data

In order to handle this, the basic process in approaching such a problem would be:
Ask questions that are currently points of pain
Find data that can provide answers or improve understanding of the point
Collect that data in an easy to use place
Visualise and analyse the data in various ways to understand what is the underlying reason the data looks that way
Take the understanding, implement it in business process
Do this again and again, over time the process will reward by indicating whether the decisions are better or are worse

So, let’s unpack this problem.

## Where do we start?

Similar to the chicken-and-egg problem, we need a question. Before a question, we need a culture. A culture that can actually handle the questions and the answers that looking at the data generates. In a basic sense, the most important requirement for a small team that starts its work with data is: curiosity. 

That is usually a foundation of the data system, curiosity to find and look for data that will answer the questions within the company. Let us take an example to build from to make this clear.

## Welcome P1 to the game..

P1 is a very inquisitive person looking for answers within a company, these questions could be any of the following and be targeted towards different facets/departments within the company:
How many visit our website every day?
What is the average time spent by a potential customer on our store-front?
How many failures occur within each batch of manufacturer goods?

These are different questions but they have an answer within the data. And funnily enough, these data points do not necessarily solve the problem but they give the direction in which to dig in order to solve the problem i.e., enable targeted decision. So, now P1, this inquisitive person goes off on the hunt.

## … where does this lead to?

The value derived by asking these questions is intrinsic to what the company is trying to solve at that stage: are we looking to improve customer retention, improve the sales process, or just make a more reliable product. 

These questions pave the way to the next logical series of actions. In order to answer these questions, we need a reliable process where P1 can get the data, process the data and build analysis and visualisations and discussions within the company.

Like any manufacturing line, from where software engineering unfortunately derives its technical terminology, there needs to be a process that leads to reliable analytics. And we need roles to fulfil the process with what is currently known as the modern data stack.

## The single person team…

The single-person analytics team doesn’t necessarily require a complex engineering process. Overall directional aspect of the process is more or less local to the system, simple scripts that can pull data from sources, local notebooks using either Python / R / Excel for analysis that can provide insight into the questions. For example, P1, looking for the answers to the question on the customer eyeballs on the website, the overall flow would be something like this:

Get either manual or programmatic access to an web analytics platform: Google Analytics / Plausible Analytics
Access the data either through existing visualisation tools built into the platform or pull locally
Analyse and review data for making decisions

A flow such as the above on one occasion makes it not much usable, but consistent analysis on the process changes the process, each decision now can be vetted and verified for positive or negative change. This feedback-driven process is the cultural cornerstone for a company, and building the foundations of a data team.

## Foundations of analytics leading to…

This leads to the foundational data stack for analytics teams. In most cases, for most companies, we have the foundational team that can do the most critical of operations: find data, get it to a very clean state, and ask questions from it or on it.

The simplest of data teams is a single person analytics, a person like P1, collect data, process and analyse the response for the company. Once the manual process and the data sources grow, it becomes a team consisting of pairing a data engineer with a data analyst.

This however, is not an absolute statement, if the company in question is in a field where the requirement is a specialist, of course, a data scientist and data engineer or even an ML engineer pairing is a better option. But, those companies know themselves and what they require within the company.

## … the process that builds a team and culture.

This makes it easy to digest for building a data team:

Find the questions you need answers for
Find the right people who can do the following:
Get the data which answers these questions and push them into a repository
Get tools and services that can transform the data into valid insight
Analyse and visualise the data until you get enough information to help augment your decision
Implement the right decision as aided by the data
Track the results, and do this process again

This process becomes a continuous, living thing. Once you have the foundations of the questions, the internal process of collecting data, and visualising metrics can be tracked over time. Once the metric being tracked becomes a time-series, the next thing gets unlocked: trend.

Trends are strong tools that can help us reinforce that we are doing the right thing. It unlocks the benefit of understanding what our actions are doing: positive trends indicate we did the right thing, negative trends indicate we are definitely doing something wrong. By just unlocking a process with a simplified team, the questions can become more interesting, and the foundations of the data team now have the basics to work from.

At this point, there is a strong foundation in a data team to expand further. Then comes the questions that we started off with: data quality, data lineage, and machine-learning, advanced topics for another rainy day.


## References

[1] The sheer size and choices available to do any particular thing is crazy: http://46eybw2v1nh52oe80d3bi91u-wpengine.netdna-ssl.com/wp-content/uploads/2021/12/Data-and-AI-Landscape-2021-v3-small.jpg

[2] Stefania Olafsdottir, Don’t hire a data engineer yet, Coalesce 2021:  https://coalesce.getdbt.com/talks/dont-hire-a-data-engineer-yet/

[3] LocallyOptimistic - The next big challenge for data is organization: https://locallyoptimistic.com/post/the-next-big-challenge-for-data-is-organizational/
