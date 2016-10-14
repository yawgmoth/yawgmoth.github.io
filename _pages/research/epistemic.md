---
title: "A language for Epistemic Actions"
layout: single
excerpt: "A high level language to express actions that update actor's mental models"
sitemap: true
permalink: /research/epistemic
categories: [research]
---

Three logicians walk into a bar. The barkeeper asks them "Do all of you want a beer?". The first logicians says: "I don't know". The second logician says: "I don't know". The third logician says: "Yes".

This anecdote, of course, works by all three logicians indeed wanting a beer. If the first logician had not wanted one, they would have answered with "No". Because they did not, the second logician can then deduce that the first logician indeed wants a beer, and because they themself want a beer (and having no knowledge about the third logician) they also answer with "I don't know". From that the third logician can conclude that the first two indeed want beers, and adding to that the knowledge about their own desire, they can answer "Yes". 

While not a game per se, this anecdote serves as a great example for our language. The basic data structure that is being manipulated is a property, i.e. a named attribute of a tuple. For example, to represent "a player p has a card in their hand at position i" in a card game, one would have a property `at(p,i)`. The language then has operators to set and unset these properties, and an if-construct that can query property values. To manipulate mental states, the language includes ways to inform players about properties, and about which branch of an if-construct is taken. It is also possible to query mental states in the predicates of if-constructs. For example, consider an action that represents a logician answering the barkeeper's question in the above anecdote:

~~~~
answer(player: Players)
    publicif Players (B (player): Forall p1 in Players: wants(p1) == Beer)
        say(player) = yes
    else
        publicif Players (B (player): Exists p1 in Players: wants(p1) != Beer)
            say(player) = no
        else
            say(player) = idk
~~~~

The desires of the logicians are modeled as properties `wants(p)` that can be set to `Beer`, while their answers are properties `say(p)` that are set to the corresponding string. The `publicif` construct branches on the given predicate, but also informs all members of a group about which branch is taken (in this case, that group would be all Players). The condition of the first if is read as "player believes that all Players want a beer", and the second one is "player believes that there exists a player that does not want a beer". In addition to `publicif` there is also an explicit `tell` statement, as can be seen in this example:

~~~~
hint_color(player: Actors, c: Colors) 
    tell(player): Each i in HandIndex: color(at(player, i)) == c
~~~~

Intuitively speaking, this action tells a player which cards in their hand have a particular color (As in e.g. the "These are all your red cards" hint action in Hanabi). `tell` also supports the `Forall` (To tell someone e.g. "all your cards are/are not red") and `Exists` quantifiers (To tell someone e.g. "you have at least one/you don't have any red card(s)") seen above, as well as a `Which` quantifier, which behaves like `Exists`, but additionally tells the recipient which object fulfills the condition, if any (As in "This is a red card in your hand/You have no red cards in your hand").

To use this language, we compile it to Baltag's [Logic for Suspicious Players](http://www.vub.ac.be/CLWF/SS/BER.pdf), and apply actions to epistemic states as described in Baltag's paper. 