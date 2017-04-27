---
title: "Hanabi - User Interface and AIs"
layout: single
excerpt: "A browser-based UI and implementation of Hanabi for the development, exploration and evaluation of AIs"
sitemap: true
permalink: /research/hanabi
categories: [research]
---

[Hanabi](https://boardgamegeek.com/boardgame/98778/hanabi) is a cooperative card game in which players collaborate to build fireworks in five colors, represented by cards in these colors ranked from 1 to 5. In a twist to most other card games, players don't see the cards in their own hand, but they see the cards in every other players' hand. Game play consists of giving hints to other players, giving them information about some subset of their cards, and trying to play cards in each color in ascending order. Hanabi is an interesting test environment for AI research because it is cooperative, has partially hidden information and requires effective communication to reach a good score. 


We have implemented a version of Hanabi that allows players to play the game inside a web browser, with a variety of different AIs. Some of these AIs are based on work by Hirotaka Osawa [1], while others were developed by us as part of our research on [intentional AIs](/research/hanabiai). The implementation is easily extensible with additional AIs, making it an ideal platform for the development of new AIs and approaches to the game. We used this implementation to test how our AI performed when compared to one of Osawa's when playing with a human cooperator. We are also providing the complete experiment setup so that other researchers can produce comparable results. Additionally, our UI can display completed games as replays. Using this capability it is possible to analyze the behavior of different AIs. It is also possible to take over a game from any point while watching such a replay, using the same AI as was used to record the replay, or a different one. This is useful to investigate how different AIs handle the same game situation. 


All code of our implementation is freely available in a [github repository](https://github.com/yawgmoth/pyhanabi). It also contains a README file with further information about how add new AIs.

We have also obtained over 2000 game logs from 240 players that can be used with the aforementioned capability to watch them as a replay. They can also provide a basis for the development of other AIs. The game log files are available in their own [github repository](https://github.com/yawgmoth/HanabiData) that includes more explanation of what data they contain.



[1] Osawa, Hirotaka. "Solving Hanabi: Estimating Hands by Opponent's Actions in Cooperative Game with Incomplete Information." Workshops at the Twenty-Ninth AAAI Conference on Artificial Intelligence. 2015.

