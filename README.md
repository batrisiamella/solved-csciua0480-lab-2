Download Link: https://assignmentchef.com/product/solved-csciua0480-lab-2
<br>
In this lab you will implement a method for solving a modified version of the traveling salesman problem in OpenMP.

<strong>What is the problem definition? </strong>

You have a group of n cities (from 0 to n-1). The traveling salesman must start from city number 0, visit each city <em>once</em>, and does not have to come back to the initial city (This is why we said it is a modified version of the original traveling salesman problem). You will be given the distance between each city (cities are fully connected to each other). You must pick the path with shortest distance. Note that there may be several paths that satisfy the above conditions, you just need to find one of them.

<strong>What is the input? </strong>

The input to your program is a text file that contains an nxn matrix, one row per line, representing the distance between any two cities. Your program will be called tsm. The command line then will be:

&gt; tsm filename.txt

Where filename.txt is the file that contains the distance matrix.

<strong>What is output? </strong>

You program must output, to screen, the best path you found and the total distance.

Here is an example output:

Best path: 0 1 3 4 5 2

Distance: 36

This means the best path your program found is 0-&gt;1-&gt;3-&gt;4-&gt;5-&gt;2 with total distance of 36.




<strong>How will you solve this? </strong>




This problem is a combinatorial optimization problem (n! possible solutions for n cities). One of the straightforward way to solve it is through branch and bound. One way you might think about evaluating every possible route is to construct a tree that describes all of the possible routes from the first city. However, the tree may get too large. One way to reduce the size is to follow one path till the end. This path has a cost of w, for example. When you explore a second path, as soon as the cost becomes larger than w, then don’t pursue it and move to another branch. If another full path turns out to be of smaller cost, then it becomes your best path and record its cost.

Feel free to optimize the above scheme in any way you want. Also you have to decide about the total number of threads needed.




<strong>How will we grade this? </strong>




The total grade is out of 20

<ul>

 <li>5 points if your program outputs a legal solution (i.e. each city visited once) but not necessarily one of the shortest paths.</li>

 <li>5 points for the report</li>

 <li>10 points if your solution is within 10% of the optimal solution (more on this on the website)</li>

</ul>

We will provide you with few test files and their optimal solutions. We will test your programs with some non-distributed files.




<strong>The report </strong>




You need to write a report that includes the following:

<ul>

 <li>How did you parallelize your program?</li>

 <li>A graph that shows speedup over single-thread version</li>

 <li>Another graph showing the scalability of your code as the size of the problem (i.e. the number of cities) increases.</li>

 <li>Explain the above two graphs.</li>

</ul>





