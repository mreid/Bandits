Bandits
=======
_Mark Reid <mark.reid@gmail.com> -- Created: 2010-04-05_

This is a JavaScript/jQuery/Flot hack to demonstrate a few key algorithms in the
literature on multi-armed bandit problems. It is also my first attempt at using 
JavaScript for something more than a widget so be careful taking anything in 
here as an example of good JS programming style.

Introduction
------------
A multi-armed bandit problem is described by the following game wherein an 
agent tries to maximise the total reward it receives:

  * Input: k bandits B[0], ..., B[k-1]
  * For time steps t = 0, 1, ..., T
    1. An agent A chooses an "arm" (index) i
    2. The agent receives a reward B[i].reward() (a value in [0,1])

This very simple game illustrates the _exploration/exploitation_ dilemma: if an 
agent finds an high-rewarding arm early should it stick with it and possibly
forego a different arm with a high reward?

Algorithms
----------
There are several well-analysed algorithms for playing such a game. I've 
implemented two important ones: 

  * `UCB1`, as described in [1]
  * `Exp3`, as described in [2]
  
as well as the `Random` agent (which simply chooses an arm at random), and 
a couple of the Exp3 variants (`Exp3.1` and `Exp3.S`), also described in [2].

Using the demo
--------------
The whole demo is just a HTML file with a bunch of JavaScript implementing the
UI, plotting, bandits and agents. Just checkout the source and open `index.html` 
in your browser (I've only tested with Safari).

The user is first presented with a game description UI. Bandits and agents can
be chosen using the drop-down selections. New bandits and agents can be added by
clicking the "+ create" link. If a bandit or agent requires parameters these can
be added in the text areas which appear next to the drop-down menu.

Once the bandits and agents are selected, the number of steps for the game can 
be entered in the text field on the right. Then hit "Go!" to run the game. 

The results are plotted below the UI. Rewards for bandits are drawn in light
grey, agents are in colour and are listed in the plot's legend. (The "Averages"
check box determines whether running totals or averages are displayed).

Acknowledgements
----------------
I've used the [flot](http://code.google.com/p/flot/) plugin to
[jQuery](http://jquery.com) for plotting multi-armed bandit games. 


References
----------
[1] P. Auer, N. Cesa-Bianchi, and P. Fischer. "Finite-time Analysis of the Multiarmed Bandit Problem", Machine Learning, 47, 235-236, 2002.

[2] P. Auer, N. Cesa-Bianchi, Y. Freund, and R. Schapire. "The nonstochastic multiarmed bandit problem", SIAM Journal on Computing, 32(1):48–77, 2002.


