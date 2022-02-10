---
author: "Vignesh Krish"
date: 2022-02-06
linktitle: foundations of data teams
title: Building Foundations of data teams - Pt. 1
---
Building the foundations of a data team and the data team itself is a struggle.

Complexity seems to be ever increasing and job profiles keep changing rapidly as data and its usage explodes all around us [1]. There are terms such as data-quality, data-lineage, and observability that are used. Then, there are profiles a company needs to hire within its data-team: data scientist, data analyst, data engineer and maybe in the future, an analytics engineers [2].

{{< twitter user="ElenaRusAthletx" id="1483651998335614978" >}}

I've been working with different aspects of data, and the more I work with it, the more I understand that there is a huge gap in what is needed for a very strong data foundation and what actually gets achieved. So, this post hopefully sheds some light into some opinions and thoughts I’ve collected through my experience.

## The Premise..

By the end of this post, I hope to provide clarity on what to focus on when building the foundations of a data team. The primary goal here is to answer this simple question:

| What is a solid data team to start with? What is needed within that team to improve the quality of life for the company?

The secondary outcome, I believe to naturally arise out from this premise is the company structure of how it could work [3]. This blog post is for small teams, where to start, how to proceed with building a team over time. One that is empowered to answer hard questions by looking at internal data and data produced through actions taking place within the company.

In order to handle this, the basic process in approaching such a problem would be:
Ask questions that are currently points of pain
Find data that can provide answers or improve understanding of the question being raised
Collect the data in a way it can be accessed easily and quickly
Visualise and analyse the data in various ways to understand what is the underlying reason the data looks that way
Take the understanding, implement it as a business decision
Do this again and again, over time the process will reward the process owner by indicating whether the decisions are better or are worse

So, let’s unpack this problem.

## Where do you start?

Similar to the chicken-and-egg problem, we need a question. Before a question, we need a culture. A culture that can actually handle the questions and the answers that looking at the data generates. In a basic sense, the most important requirement for a small team that starts its work with data is: curiosity and ability to accept answers that betray our intuitive thinking. 

That is usually a foundation of the data driven organisation. The curiosity leads to finding data points that are relevant for the question being answered and providing novel takes on the question itself. The ability to accept non-intuitive world views improves what we take out from this process. Sometimes, the data is going to tell us that our world or rather, our viewpoint on our world is broken. And such, the combination of curiosity and the ability to accept contradictory viewpoints will lay the foundations of a data team that will reward the organisation with momentum and insight.

To do this, let us hire P1.

## Welcome P1 to the game..

P1 is a very inquisitive person looking for answers within a company, these questions could be any of the following and be targeted towards different facets/departments within the company:
How many visitors do we have on our website every day?
What is the average time spent by a potential customer on our store-front?
How long do customers spend on the store-front before purchasing?
How many failures occur within each batch of manufacturer goods?
Can we forecast purchases per month? 

These are different questions but they have an answer within the data. And funnily enough, these data points do not necessarily solve the problem but they give the direction in which to dig in order to solve the problem or make a decision i.e., enable targeted decision. So, now P1, this inquisitive person goes off on the hunt.

## … where does this lead to?

The value derived by asking these questions is intrinsic to what the company is trying to solve at that stage: are we looking to improve customer retention, improve the sales process, or just make a more reliable product. 

These questions pave the way to the next logical series of actions. In order to answer these questions, we need a reliable process where P1 can get the data, process the data and build analysis and visualisations and discussions within the company. This process, of extraction, loading and transformation (ELT) and sometimes ETL is the basics of what is now called popularly the Modern Data Stack [4].

## The single person team…

The single-person analytics team doesn’t necessarily require a complex engineering process. Overall directional aspect of the process is more or less local to the system, simple scripts that can pull data from sources, local notebooks using either Python / R / Excel for analysis that can provide insight into the questions. For example, P1, looking for the answers to the question on the customer eyeballs on the website, the overall flow for which would be something like this:

Get either manual or programmatic access to an web analytics platform: Google Analytics / Plausible Analytics
Access the data either through existing visualisation tools built into the platform or pull locally
Analyse and review data for making decisions

A flow such as the above on one occasion makes it not much usable, but consistent analysis on the process changes the outcome, each decision now can be vetted and verified for a positive or negative change. This feedback-driven process is the cultural cornerstone for a company that is building a data-driven team.

## This foundation of analytics leads to…

This leads to the foundational data stack for analytics teams. In most cases, for most companies, we have the foundational team that can do the most critical of operations: find data, get it to a very clean state, and ask questions from it or on it.

The simplest of data teams is a single person analytics, a person like P1, collects data, processes data and analyses the response for the company. Once the manual process and the data sources grow, it becomes a team consisting of a pairing of a data engineer with a data analyst or a data scientist.

This however, is not an absolute statement, the complexity of what is being achieved indicates who you need: a data scientist, ML Engineer, or a hybrid. 

## … the process that builds a team and culture.

This makes it easy to digest for building a data team:

Find the questions you need answers for
Find the right people who can do the following:
Get the data which answers these questions and push them into a repository or a warehouse or data lake
Get tools and services that can transform the data into valid insight
Analyse and visualise the data until you get enough information to help augment your decision
Implement the right decision as aided by the data
Track the results, and do this process again

This process becomes a continuous, living thing. Once you have the foundations of the questions, the internal process of collecting data, and visualising metrics can be tracked over time. Once the metric being tracked becomes a time-series, the next thing gets unlocked: trend.

Trends are strong tools that can help us reinforce that we are doing the right thing. It unlocks the benefit of understanding what our actions are doing: positive trends indicate we did the right thing, negative trends indicate we are definitely doing something wrong. By just unlocking a process with a simplified team, the questions can become more interesting, and the foundations of the data team now have the basics to work from and improve.

At this point, there is a strong foundation in a data team and a cultural support that allows the data team to ask questions and help in improving internal decision making. This foundation would lead into specific operational actions that data teams of slightly higher complexity need to implement: data lineage, data quality verifications, automated analytics, and feature stores. These are topics for another rainy day.

Thanks to Rohit Sharma (LinkedIn) and Morten Badensoe (LinkedIn) for discussions and help in formulating and refining this blog post.

## References

[1] The sheer size and choices available to do any particular thing is crazy: http://46eybw2v1nh52oe80d3bi91u-wpengine.netdna-ssl.com/wp-content/uploads/2021/12/Data-and-AI-Landscape-2021-v3-small.jpg

[2] Stefania Olafsdottir, Don’t hire a data engineer yet, Coalesce 2021:  https://coalesce.getdbt.com/talks/dont-hire-a-data-engineer-yet/

[3] LocallyOptimistic - The next big challenge for data is organization: https://locallyoptimistic.com/post/the-next-big-challenge-for-data-is-organizational/

[4] What is the modern data stack: https://www.analytics8.com/blog/what-is-the-modern-data-stack-and-why-should-you-be-excited-about-it/#
