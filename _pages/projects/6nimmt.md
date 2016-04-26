---
title: "6 Nimmt!"
layout: single
excerpt: "A simple implementation of 6 nimmt! that includes several AIs"
sitemap: true
permalink: /projects/6nimmt
categories: [project]
---

**[6 nimmt!](http://www.amigo-spiele.de/spiel/6-nimmt)** is a card game. Each player is dealt a hand of ten cards, with four more cards making up the initial board, as four rows of one card each. Every round, all players simultaneously and secretly choose one of their cards, then all of them are revealed. Play proceeds from the lowest to the highest card. Each card has to placed at the end of a row, such that it is higher than the last card in that row, and that there is no row that ends with a lower-valued card (i.e. players don't have a choice where to place their card, it goes into the row it {{ 'fits best' | smartify }}). Whoever places the sixth card in a row has to take the other five cards as a trick, and their card becomes the sole card in that row. After ten rounds, when all cards have been played, whoever has the fewest points from tricks wins.

When we played this game, one player just decided to play randomly, since the game can be very frustrating when a carefully considered choice does not turn out as well as expected. Since there is a fair amount of variance in the game, he actually ended up doing well in some games. 