# A Problem Solving Adventure
In an attempt to stay sharp, I've decided that I could work a bit more on my problem solving skills. To do that, I've pulled a problem straight out of a book I own. The book is called *Artificial Intelligence: A Modern Approach* and it's by Stuart Russell and Peter Norvig. The problem is number 3.3 on page 113. It reads:
> Suppose two friends live in different cities on a map, such as the Romania map shown in Figure 3.2. On every turn, we can simultaneously move each friend to a neighboring city on the map. The amount of time needed to move from city *i* to neighbor *j* is equal to the road distance *d(i,j)* between the cities, but on each turn the friend that arrives first must wait until the other one arrives (and calls the first on his/her cell phone) before the next turn can begin. We want the two friends to meet as quickly as possible.  
**a.** Write a detailed formulation for this search problem. (You will find it helpful to define some formal notation here.)  
**b.** Let *D(i,j) be the straight-line distance between cities *i* and *j*. Which of the following heuristic functions are admissable? (i) *D(i,j)*; (ii) 2 * *D(i,j)*; (iii) *D(i,j)*/2.  
**c.** Are there completely connected maps for which no solution exists?  
**d.** Are there maps in which all solutions require one friend to vist the same city twice?

Here is Figure 3.2, the simplified map of Romania.
![romania](/assets/romania.JPG)
I like to tackle my problems piece-meal so, reading the first part of the problem description:
> Suppose two friends live in different cities on a map, such as the Romania map shown in Figure 3.2.  

Let us suppose we have two friends, I am going to call them "Jack" and "Jill". Suppose further that Jack lives in **Oradea** and Jill lives in **Bucharest**.  
Ok, with this in mind, onto the next piece of the problem description:
>On every turn, we can simultaneously move each friend to a neighboring city on the map.  

Alright, so let's assume it's *turn 0*. That means Jack is in the city **Oradea** and Jill is in **Bucharest**. What can happen on *turn 1*? Well, according to the rules of this game, we can move each friend to a neighboring city on the map. So we could choose to move Jack to **Zerind** or **Sibiu** and we could choose to move Jill to **Fagaras**, **Pitesti**, **Giurgiu**, or **Urziceni**, since those are all neighboring cities to our two characters.  
Onto the next piece:
> The amount of time needed to move from city *i* to neighbor *j* is equal to the road distance *d(i,j)* between cities,  

Alrighty. So if Jack moves from **Oradea** to **Sibiu**, looking at the map and the distances given, it is going to take him *d(**Oradea**,**Sibiu**)* = 151 units of time. If Jill moves from **Bucharest** to **Pitesti** it's going to take her *d(**Bucharest**,**Pitesti**)* = 101 units of time.  
> but on each turn the friend that arrives first must wait until the other one arrives (and calls the first on his/her cell phone) before the next turn can begin.  

So, if Jack moves from **Oradea** to **Zerind** and Jill moves from **Bucharest** to **Fagaras** within a turn, then once Jack has arrived in **Zerind** he is going to have to wait for Jill to arrive in **Fagaras** and call him on her cell phone so that the next turn can begin because *d(**Oradea**,**Zerind**)* < *d(**Bucharest**,**Fagaras**)*. (This is based off the two assumptions that Jack and Jill hit the road at the same time at the start of every turn and also that they both drive at the same rate. This last assumption may be a bad one because perhaps Jill is a speed demon.)
> We want the two friends to meet as quickly as possible.

Ok, so the objective is really to minimize the distance traveled by the two since distance = time in this problem. If Jack calls Jill and tells her that he's going to meet her in **Bucharest** (meaning Jill doesn't have to travel), he could choose to travel from **Oradea** to **Zerind** to **Arad** to **Timisoara** to **Lugoj** to **Mehadia** to **Drobeta** to **Craiova** to **Pitesti** to **Bucharest**. This is obviously not the optimal way of doing things since the total distance Jack traveled is *d(**Oradea**,**Zerind**)* + *d(**Zerind**,**Arad**)* + 
