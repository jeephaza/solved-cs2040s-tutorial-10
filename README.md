Download Link: https://assignmentchef.com/product/solved-cs2040s-tutorial-10
<br>
<strong>Problem 1.</strong>

<strong>(Priority queue.)</strong>

There are situations where, given a data set, we want to know the top <em>k </em>highest value elements. A possible solution is to store all <em>n </em>elements first, sort the data set in <em>O</em>(<em>n</em>log<em>n</em>), then report the rightmost <em>k </em>elements. Give an algorithm to: (i) find the top <em>k </em>largest elements better than <em>O</em>(<em>n</em>log<em>n</em>); (ii) find the top <em>k </em>largest elements as the elements are streaming in (for each new element that is given to you, your data structure must be ready to answer queries for the top <em>k </em>largest elements efficiently), and the algorithm runs faster than <em>O</em>(<em>n</em>log<em>n</em>).

<strong>Problem 2.</strong>

<strong>(Horseplay.)</strong>

(Relevant Kattis Problem: https://open.kattis.com/problems/bank)

There are <em>m </em>bales of hay that need to be bucked and <em>n </em>horses to buck them.

The <em>i</em><sup>th </sup>bale of hay has a weight of <em>k<sub>i </sub></em>kilograms.

The <em>i</em><sup>th </sup>horse has a strength <em>s<sub>i</sub></em>—the maximum weight, in kilograms, it can buck—and can be hired for <em>d<sub>i </sub></em>dollars.

Bucking hay is a very physically demanding task, so to avoid the risk of injury every horse can buck at most one bale of hay.

Determine, in <em>O</em>(<em>n</em>log<em>n </em>+ <em>m</em>log<em>m</em>), the minimum amount, in dollars, needed to buck all bales of hay. If it is not possible to buck them all, determine that as well.

<strong>Problem 3.        </strong>(Union-Find Review)

<strong>Problem 3.a. </strong>What is the worst-case running time of the find operation in Union-Find with path compression (but no weighted union)?

<strong>Problem 3.b. </strong>Here’s another algorithm for Union-Find based on a linked list. Each set is represented by a linked list of objects, and each object is labelled (e.g., in a hash table) with a set identifier that identifies which set it is in. Also, keep track of the size of each set (e.g., using a hash table). Whenever two sets are merged, relabel the objects in the smaller set and merge the linked lists. What is the running time for performing <em>m </em>Union and Find operations, if there are initially <em>n </em>objects each in their own set?

More precisely, there is: (i) an array <em>id </em>where <em>id</em>[<em>j</em>] is the set identifier for object <em>j</em>; (ii) an array <em>size </em>where <em>size</em>[<em>k</em>] is the size of the set with identifier <em>k</em>; (iii) an array <em>list </em>where <em>list</em>[<em>k</em>] is a linked list containing all the objects in set <em>k</em>.

Find(i, j): return (id[i] == id[j])

Union(i, j): if size[i] &lt; size[j] then Union(j,i) else // size[i] &gt;= size[j] k1 = id[i] k2 = id[j] for every item m in list[k2]:

set id[m] = k1

append list[k2] on the end of list[k1] and set list[k2] to null size[k1] = size[k1] + size[k2] size[k2] = 0

Assume for the purpose of this problem that you can append one linked list on to another in <em>O</em>(1) time. (How would you do that?)

<strong>Problem 3.c. </strong>Imagine we have a set of <em>n </em>corporations, each of which has a (string) name. In order to make a good profit, each corporation has a set of jobs it needs to do, e.g., corporation <em>j </em>has tasks <em>T<sup>j</sup></em>[1<em>…m</em>]. (Each corporation has at most <em>m </em>tasks.) Each task has a priority, i.e., an integer, and tasks must be done in priority order: corporation <em>j </em>must complete higher priority tasks before lower priority tasks.

Since we live in a capitalist society, every so often corporations decide to merge. Whenever that happens, two corporations merge into a new (larger) corporation. Whenever that happens, their tasks merge as well.

Design a data structure that supports three operations:

getNextTask(name) that returns the next task for the corporation with the specified name.

executeNextTask(name) that returns the next task for the corporation with the specified name and removes it from the set of tasks that corporation does.

merge(name1, name2, name3) that merges corporation with names name1 and name2 into a new corporation with name3.

Give an efficient algorithm for solving this problem.

<strong>Problem 4. </strong>Elephant Encounters Related Kattis Problems:

https://open.kattis.com/problems/arbitrage https://open.kattis.com/problems/getshorty

Travelling can be a risky proposition: you never know when you will meet a large pink elephant. Luckily, you have been given a map where each road segment is labelled with the exact probability that someone driving on that road will not encounter a large pink elephant (<em>i.e.</em>, the probability of being safe from encountering a large pink elephant). You want to drive from New York to Los Angeles. What route should you take so as to have the smallest chance of meeting a large pink elephant?

More formally, you are given a directed graph <em>G </em>= (<em>V,E</em>), where every edge <em>e </em>has an independent safety probability <em>p</em>(<em>e</em>). The safety value of a path is the product of the safety probabilities of its edges. Design and analyze an algorithm to determine the safest path from a given start vertex <em>s </em>to a given target vertex <em>t</em>.

<strong>Problem 5.        </strong>Running Trails

I want to go for a run. I want to go for a long run, starting from my home and ending at my home. And I want the first part of the run to be only uphill, and the second part of the run to be only downhill. I have a trail map of the nearby national park, where each location is represented as a node and each trail segment as an edge. For each node, I have the elevation (value shown in the node). Find me the longest possible run that goes first uphill and then downhill, with only one change of direction.

<strong>Problem 6.         </strong>(Bad Dijkstra)

Give an example of a graph where Dijkstra’s Algorithm returns the wrong answer.

<strong>Problem 7.          </strong>(A Random Problem with a dude called Dan)

<strong>Problem 7.a. </strong>Dan is on his way home from work. The city he lives in is made up of <em>N </em>locations, labelled from 0 to (<em>N </em>− 1). His workplace is at location 0 and his home is at location (<em>N </em>− 1). These locations are connected by <em>M </em><strong>directed </strong>roads, each with an associated <em>(non-negative) </em>cost. To go through a road, Dan will need to pay the cost associated with that road. Usually, Dan would try to take the cheapest path home.

The thing is, Dan has just received his salary! For reasons unknown, he wants to flaunt his wealth by going through a <em>really expensive road. </em>However, he still needs to be able to make it back home with the money he has. Given that Dan can afford to spend up to <em>D </em>dollars on transportation, help him find <strong>the cost of the most expensive road that he can afford to go through </strong>on his journey back home.

Take note than Dan only cares about the most expensive road in his journey; the rest of the journey can be really cheap, or just as expensive, so long as the entire journey fits within his budget of <em>D </em>dollars. He is also completely focused on this goal and does not mind visiting the same location multiple times, or going through the same road multiple times.

For example, suppose Dan’s budget is <em>D </em>= 13 dollars. Consider the city given in Figure 1, consisting of <em>N </em>= 8 locations and <em>M </em>= 10 roads.

<strong>Figure 1: </strong>Example city 1

The path that Dan will take is 0 → 1 → 4 → 7. In this journey, the total cost is 11 dollars and the most expensive road has a cost of 7 dollars – the road from locations 1 to 4. Therefore, the expected output for this example would be “7”.

Note that this path is neither the cheapest path (0 → 3 → 4 → 7), nor is it the most expensive path that fits within his budget of 13 dollars (0 → 1 → 2 → 7).

There is also a more expensive road within this city – the road from locations 5 to 6 with a cost of 10 dollars. However, the only path that goes through this road, 0 → 5 → 6 → 7, has a total cost of 14 dollars which exceeds Dan’s budget.

<strong>Problem 7.b. </strong><em>(Optional) </em>Another month, another salary for Dan to flaunt. The situation is similar to that of the previous part.

This time, however, instead of maximizing the cost of the <em>most expensive road </em>in his journey, he wants to maximize the cost of <em>the second most expensive road </em>in his journey. In other words, he no longer cares about the most expensive road in his journey; that road can be 100 times more expensive than the second most expensive road in his journey for all he cares.

For example, consider the city in Figure 2 with <em>N </em>= 4 locations and <em>M </em>= 5 roads.

If Dan’s budget is <em>D </em>= 12 dollars, the path that he will take is 0 → 2 → 3. In this journey, the total cost is 11 dollars and the second most expensive road has a cost of 5 dollars, the road from locations 0 to 2. Therefore, the expected output for this example would be “5”.

Notice that while he can afford to go through the path 0 → 1 → 3 with an expensive 8 dollar road, the second most expensive road in that journey only costs 1 dollar.

<strong>Figure 2: </strong>Example city 2

If Dan’s budget is <em>D </em>= 20 dollars, then the path he will take is 0 → 1 → 3 → 0 → 1 → 3. As irrational as this 20 dollar journey is, it allows him to go through the road from locations 1 to 3 twice, thus making the second most expensive road in his journey cost 8 dollars.