---
title: "Intentional AI for Hanabi"
layout: single
excerpt: "An intentional AI for Hanabi"
sitemap: true
permalink: /research/hanabiai
categories: [research]
---

[Hanabi](https://boardgamegeek.com/boardgame/98778/hanabi) is a cooperative card game in which players collaborate to build fireworks in five colors, represented by cards in these colors ranked from 1 to 5. In a twist to most other card games, players don't see the cards in their own hand, but they see the cards in every other players' hand. Game play consists of giving hints to other players, giving them information about some subset of their cards, and trying to play cards in each color in ascending order. Hanabi is an interesting test environment for AI research because it is cooperative, has partially hidden information and requires effective communication to reach a good score. 


When humans play Hanabi, they have certain expectations for the behavior of their cooperators. For example, a human player expects information that other players convey to them to be relevant and unambiguous, according to [Grice's maxims of communication](https://www.sas.upenn.edu/~haroldfs/dravling/grice.html). They also assume that players behave in a goal-directed manner. To combine these two characteristics, we developed an AI that forms intentions about what it wants the human cooperator to do, and then evaluates what effect the possible communicative actions it can perform would likely have, taking Grice's maxims into account. We tested this AI by comparing it to an AI developed by Osawa [1], and showed that it performs better when playing with a human player, even though it performs comparably when playing with another AI agent. More details can be found in our paper that is currently under review for publication, but available as a [preprint here](/images/hanabipaper.pdf).

Note that our implementation of Hanabi, including various AIs, and most of the data we obtained during the experiment are available for download. Find more details [here](/research/hanabi).



[1] Osawa, Hirotaka. "Solving Hanabi: Estimating Hands by Opponent's Actions in Cooperative Game with Incomplete Information." Workshops at the Twenty-Ninth AAAI Conference on Artificial Intelligence. 2015.

