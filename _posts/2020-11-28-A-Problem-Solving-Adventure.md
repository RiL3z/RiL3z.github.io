# A Problem Solving Adventure
In an attempt to stay sharp, I've decided that I could work a bit more on my problem solving skills. To do that, I've pulled a problem straight out of a book I own. The book is called *Artificial Intelligence: A Modern Approach* and it's by Stuart Russell and Peter Norvig. The problem is number 3.3 on page 113. It reads:
> Suppose two friends live in different cities on a map, such as the Romania map shown in Figure 3.2. On every turn, we can simultaneously move each friend to a neighboring city on the map. The amount of time needed to move from city *i* to neighbor *j* is equal to the road distance *d(i,j)* between the cities, but on each turn the friend that arrives first must wait until the other one arrives (and calls the first on his/her cell phone) before the next turn can begin. We want the two friends to meet as quickly as possible.  
**a.** Write a detailed formulation for this search problem. (You will find it helpful to define some formal notation here.)  
**b.** Let *D(i,j) be the straight-line distance between cities *i* and *j*. Which of the following heuristic functions are admissable? (i) *D(i,j)*; (ii) 2 * *D(i,j)*; (iii) *D(i,j)*/2.  
**c.** Are there completely connected maps for which no solution exists?  
**d.** Are there maps in which all solutions require one friend to vist the same city twice?

Here is Figure 3.2, the simplified map of Romania.
![romania](/assets/romania.jpg)
