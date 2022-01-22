Constraint satisfaction problems
A k-coloring of a map is an assignment of k colors, one to each country, in such a way that no two countries sharing a border have the same color. This problem can be translated into a constraint graph. A coloring of a graph G assigns a color to each vertex of G, with the restriction that two adjacent vertices never have the same color. The chromatic number of G, written χ(G), is the smallest number of colors needed to color G. 
Constraint satisfaction problems on finite domains are typically solved using a form of search. The most used techniques are variants of backtracking, constraint propagation, and local search.

There are 3 approaches we have used in this project Depth First Search, DFS with forward checking, DFS with forward checking and propagation through singleton.
Depth first search(Backtracking):
The concept in backtracking applied to map coloring is that once any variables domain reaches 0 then the algorithm goes back to previous states and see if using other options in the domain would yield a color for the one with the empty set in its domain. Every time the algorithm checks the next state only after reaching there, there are no prechecks done.
DFS With Forward Checking:-
The concept here is exactly same as backtracking only that next check is pre-checked making the algorithm smarter than Just BACKTRACKING. Number of backtracks are significantly reduced.
DFS With Forward Checking and Propagation through Singleton Domain:-
Here the algorithm checks among all possibilities of next states and choses the one with domain value equal to 1 and propagates to the next unassigned variables from the one with domain =1. Number of backtracks are further reduced and the algorithm is relatively faster.
Heuristics Used:-
There may be a number of options or nodes to chose from the next states. Any one of the states may be chosen at random and we could progress the map coloring algorithm. With using heuristics we get an order of chosing the variables depending on some factors. Some of the most commonly used heuristics are as follows below. 

1.)MINIMUM REMAINING VALUES:-
In this heuristic propagation follows in the order of those nodes with least number of values in it’s domain . With respect to map coloring problem If one state has 2 permissible values in its domain and another state has 3 then the state with 2 values would be chosen first , here permissible refers to reducing domain size because of constraints imposed that adjacent states cannot have same color.

2.) DEGREE HEURISTIC:-
The idea here is assign a value to the variable that is involved in the largest number of constraints on other unassigned variables. It is often used as a means to reduce the number of same next possibilities ie as a tie breaker with Minimum remaining values heuristic to chose the best next when all next nodes have the same number of domain values after a variable assignment is done using Mrv.

3.)LEAST CONSTRAINING VALUE:-	
Under the "least-constraining-value" heuristic for ordering values, prefer the value that rules out the fewest choices for the neighboring variables in the constraint graph.


Results:
USA:
1. DFS without heuristics:
Number of executions	Number of backtracks	Time taken
1	1012451	23.047109603881836seconds
2	1012451	14.418904542922974seconds
3	1012451	17.300964369135966seconds
4	1012451	17.913596630096436seconds
5	1012451	20.690044164657593seconds

Sample Output:
Choose The Map : 1. USA  2. Australia 
1
(1, {'Maine': 'red', 'Minnesota': 'red', 'South Dakota': 'blue', 'Illinois': 'red', 'Utah': 'red', 'Wyoming': 'green', 'Texas': 'blue', 'Idaho': 'blue', 'Wisconsin': 'blue', 'Connecticut': 'red', 'Pennsylvania': 'red', 'Kansas': 'green', 'West Virginia': 'blue', 'North Carolina': 'green', 'Colorado': 'blue', 'California': 'red', 'Florida': 'red', 'Vermont': 'red', 'Virginia': 'red', 'North Dakota': 'green', 'Michigan': 'green', 'New Jersey': 'blue', 'Nevada': 'green', 'Arkansas': 'green', 'Mississippi': 'red', 'Iowa': 'green', 'Kentucky': 'green', 'Maryland': 'green', 'Louisiana': 'black', 'Alabama': 'green', 'Oklahoma': 'red', 'New Mexico': 'green', 'Rhode Island': 'blue', 'Massachusetts': 'green', 'South Carolina': 'red', 'Indiana': 'blue', 'Delaware': 'black', 'Tennessee': 'blue', 'Georgia': 'black', 'Arizona': 'black', 'Nebraska': 'red', 'Missouri': 'black', 'New Hampshire': 'blue', 'Ohio': 'black', 'Oregon': 'black', 'Washington': 'red', 'Montana': 'red', 'New York': 'black'})
NUMBER OF BACKTRACKS: 1012451
TIME TAKEN FOR EXECUTION: 14.418904542922974seconds

2. DFS [With heuristics]  :

Number of executions	Number of backtracks	Time taken
1	701287	23.99692907333323seconds
2	701287	25.51555614474487seconds
3	701287	21.274975299835205seconds
4	701287	24.516575299835205seconds
5	701287	20.44617414474487seconds

Sample Output:
Choose The Map : 1. USA  2. Australia 
1
 (1, {'Maine': 'red', 'Minnesota': 'red', 'South Dakota': 'blue', 'Illinois': 'red', 'Utah': 'red', 'Wyoming': 'green', 'Texas': 'blue', 'Idaho': 'blue', 'Wisconsin': 'blue', 'Connecticut': 'red', 'Pennsylvania': 'red', 'Kansas': 'green', 'West Virginia': 'blue', 'North Carolina': 'green', 'Colorado': 'blue', 'California': 'red', 'Florida': 'red', 'Vermont': 'red', 'Virginia': 'red', 'North Dakota': 'green', 'Michigan': 'green', 'New Jersey': 'blue', 'Nevada': 'green', 'Arkansas': 'green', 'Mississippi': 'red', 'Iowa': 'green', 'Kentucky': 'green', 'Maryland': 'green', 'Louisiana': 'black', 'Alabama': 'green', 'Oklahoma': 'red', 'New Mexico': 'green', 'Rhode Island': 'blue', 'Massachusetts': 'green', 'South Carolina': 'red', 'Indiana': 'blue', 'Delaware': 'black', 'Tennessee': 'blue', 'Georgia': 'black', 'Arizona': 'black', 'Nebraska': 'red', 'Missouri': 'black', 'New Hampshire': 'blue', 'Ohio': 'black', 'Oregon': 'black', 'Washington': 'red', 'Montana': 'red', 'New York': 'black'})
Number Of Backtracks: 701287
TIME TAKEN FOR EXECUTION: 20.997653245925903seconds




3. DFS with forward checking [without heuristic]
Number of run	Number of backtrack	Time taken
1	10231	70.232476857348957 seconds
2	10231	71.977283452746982seconds
3	10231	70.593252454327954seconds
4	10231	72.086287346735237seconds
5	10231	71.112123245546576seconds

Sample Output:
Choose The Map : 1. USA  2. Australia 
1
(1, {'New Hampshire': 'red', 'Oklahoma': 'red', 'Tennessee': 'red', 'Illinois': 'red', 'New Mexico': 'blue', 'Kentucky': 'blue', 'West Virginia': 'green', 'Maryland': 'red', 'Maine': 'blue', 'Wisconsin': 'blue', 'Missouri': 'green', 'Minnesota': 'red', 'Montana': 'red', 'Massachusetts': 'blue', 'South Carolina': 'red', 'North Dakota': 'blue', 'Pennsylvania': 'blue', 'Arizona': 'green', 'South Dakota': 'green', 'Ohio': 'red', 'Oregon': 'red', 'Alabama': 'blue', 'Indiana': 'green', 'Rhode Island': 'red', 'Virginia': 'black', 'Idaho': 'green', 'Nevada': 'blue', 'Nebraska': 'red', 'New York': 'green', 'Utah': 'red', 'Michigan': 'black', 'Kansas': 'blue', 'Florida': 'red', 'Connecticut': 'black', 'Iowa': 'black', 'Wyoming': 'blue', 'Louisiana': 'red', 'California': 'black', 'Vermont': 'black', 'Texas': 'green', 'Georgia': 'green', 'New Jersey': 'red', 'North Carolina': 'blue', 'Washington': 'blue', 'Delaware': 'green', 'Colorado': 'black', 'Mississippi': 'green', 'Arkansas': 'blue'}) 
Number Of Backtracks: 10231
TIME TAKEN FOR EXECUTION: 70.232476857348957 seconds


4. DFS with forward checking [with heuristic]
Number of run	Number of backtrack	Time taken
1	1713	0.12491655349731445seconds
2	1713	0.07805252075195312seconds
3	1713	0.07978534698486328seconds
4	1713	0.07878468768327873seconds
5	1713	0.11237462387288990seconds

Sample Output:
Choose The Map : 1. USA  2. Australia 
1
(1, {'Illinois': 'red', 'Oklahoma': 'red', 'California': 'red', 'Utah': 'red', 'Wyoming': 'blue', 'Missouri': 'blue', 'Michigan': 'green', 'Texas': 'blue', 'Iowa': 'green', 'Delaware': 'red', 'Tennessee': 'red', 'Maryland': 'blue', 'Kentucky': 'green', 'Montana': 'red', 'Minnesota': 'red', 'Connecticut': 'red', 'Louisiana': 'red', 'West Virginia': 'red', 'Pennsylvania': 'green', 'Nebraska': 'red', 'Kansas': 'green', 'Indiana': 'blue', 'Rhode Island': 'blue', 'Arizona': 'blue', 'Florida': 'red', 'Massachusetts': 'green', 'South Dakota': 'black', 'Nevada': 'green', 'South Carolina': 'red', 'Ohio': 'black', 'New Hampshire': 'red', 'Idaho': 'black', 'Washington': 'red', 'Colorado': 'black', 'Oregon': 'blue', 'New Jersey': 'blue', 'Mississippi': 'blue', 'Arkansas': 'green', 'Vermont': 'blue', 'Wisconsin': 'blue', 'Alabama': 'green', 'Georgia': 'blue', 'Maine': 'blue', 'New Mexico': 'green', 'North Carolina': 'green', 'New York': 'black', 'Virginia': 'black', 'North Dakota': 'blue'})
Number Of Backtracks: 1713
TIME TAKEN FOR EXECUTION: 0.12491655349731445seconds

5. DFS with forward checking and propagation through singleton domains    [With heuristic]:
Number of run	Number of backtrack	Time taken
1	24371	0.4998853206634521seconds
2	24371	0.4998810291290283seconds
3	24371	0.5623590946197512seconds
4	24371	0.5357866878278409seconds
5	24371	0.4928348286472676seconds

Sample Output:
Choose The Map : 1. USA  2. Australia 
1
(1, {'Kansas': 'green', 'New Hampshire': 'green', 'Idaho': 'green', 'Louisiana': 'brown', 'New Jersey': 'green', 'Arkansas': 'green', 'Kentucky': 'green', 'Maine': 'brown', 'Minnesota': 'brown', 'Missouri': 'yellow', 'West Virginia': 'yellow', 'North Carolina': 'green', 'Massachusetts': 'brown', 'Michigan': 'green', 'Indiana': 'yellow', 'Illinois': 'brown', 'Virginia': 'brown', 'Oklahoma': 'brown', 'Montana': 'brown', 'North Dakota': 'green', 'Texas': 'yellow', 'Colorado': 'yellow', 'South Carolina': 'brown', 'Maryland': 'green', 'California': 'green', 'New York': 'yellow', 'Florida': 'green', 'Vermont': 'blue', 'Utah': 'brown', 'Georgia': 'yellow', 'Oregon': 'brown', 'Wisconsin': 'yellow', 'Rhode Island': 'green', 'Nebraska': 'brown', 'New Mexico': 'green', 'Mississippi': 'green', 'Alabama': 'brown', 'Nevada': 'yellow', 'Tennessee': 'blue', 'Iowa': 'green', 'South Dakota': 'yellow', 'Ohio': 'brown', 'Pennsylvania': 'blue', 'Washington': 'yellow', 'Wyoming': 'blue', 'Arizona': 'blue', 'Delaware': 'brown', 'Connecticut': 'blue'})
Number Of Backtracks: 24371
TIME TAKEN FOR EXECUTION: 0.4998853206634521seconds



6. DFS with forward checking and propagation through singleton domains    [Without heuristic]:
Number of run	Number of backtrack	Time taken
1	9691	2.0298960208892822 seconds
2	9691	0.16092705726623535seconds
3	9691	0.15959963909444808seconds
4	9691	1.5394909594480896seconds
5	9691	1.348089599094496seconds

Sample Output:
Choose The Map : 1. USA  2. Australia 
1
Time taken for execution = 2.0298960208892822 seconds
Number of Backtracks = 9691
{'Ohio': 'blue', 'Hawaii': 'blue', 'Vermont': 'blue', 'Maine': 'blue', 'Tennessee': 'blue', 'Oklahoma': 'blue', 'Colorado': 'green', 'Alabama': 'green', 'Oregon': 'blue', 'Minnesota': 'blue', 'New Mexico': 'red', 'Mississippi': 'red', 'Kansas': 'red', 'New Hampshire': 'green', 'Louisiana': 'blue', 'Rhode Island': 'blue', 'Montana': 'blue', 'Wisconsin': 'green', 'Michigan': 'red', 'Arkansas': 'green', 'Maryland': 'blue', 'Missouri': 'orange', 'Massachusetts': 'red', 'North Dakota': 'green', 'Nevada': 'green', 'South Dakota': 'orange', 'Illinois': 'blue', 'Washington': 'green', 'Virginia': 'green', 'Indiana': 'green', 'Alaska': 'blue', 'Connecticut': 'green', 'North Carolina': 'red', 'New York': 'orange', 'New Jersey': 'blue', 'Iowa': 'red', 'Kentucky': 'red', 'South Carolina': 'blue', 'West Virginia': 'orange', 'Idaho': 'orange', 'Florida': 'blue', 'Delaware': 'green', 'Nebraska': 'blue', 'Arizona': 'orange', 'Wyoming': 'red', 'California': 'red', 'Utah': 'blue', 'Texas': 'orange', 'Pennsylvania': 'red', 'Georgia': 'orange'}








  Australia:
1. DFS without heuristics:
Number of executions	Number of backtracks	Time taken
1	0	2.759106515555e-05seconds
2	0	2.799106443125e-05seconds
3	0	2.239104453125e-05seconds
4	0	2.611556453545e-05seconds
5	0	2.551064156514e-05seconds

Sample Output:
Choose The Map : 1. USA  2. Australia 
2
(1, {'wa': 'red', 'nt': 'blue', 'q': 'red', 'nsw': 'blue', 'v': 'red', 'sa': 'green'})
NUMBER OF BACKTRACKS: 0

TIME TAKEN FOR EXECUTION: 2.239104453125e-05seconds

2. DFS [With heuristics] :
Number of executions	Number of backtracks	Time taken
1	0	1.259106515555e-05seconds
2	0	2.399106443125e-05seconds
3	0	1.939104453125e-05seconds
4	0	2.011556453545e-05seconds
5	0	2.751064156514e-05seconds

Sample Output:
Choose The Map : 1. USA  2. Australia 
2
(1, {'wa': 'red', 'nt': 'blue', 'q': 'red', 'nsw': 'blue', 'v': 'red', 'sa': 'green'})
Number Of Backtracks: 0
TIME TAKEN FOR EXECUTION: 2.751064156514e-05seconds

3. DFS with forward checking [without heuristic]
Number of run	Number of backtrack	Time taken
1	0	0.156218290328975seconds
2	0	0.142836816973192seconds
3	0	0.144676872613895seconds
4	0	0.156090993276456seconds
5	0	0.151213489876993seconds

Sample Output:
Choose The Map : 1. USA  2. Australia 
2
['wa', 'nt', 'q', 'nsw', 'v', 'sa']
 (1, {'wa': 'blue', 'nt': 'yellow', 'q': 'blue', 'nsw': 'yellow', 'v': 'blue', 'sa': 'brown'})
Number Of Backtracks: 0
TIME TAKEN FOR EXECUTION: 0.1562182903289795seconds


4. DFS with forward checking [with heuristic]
Number of run	Number of backtrack	Time taken
1	0	0.000997304916388seconds
2	0	0.000912975424654seconds
3	0	0.000187235452656seconds
4	0	0.000971893277347seconds
5	0	0.000196380875545seconds

Sample Output:
Choose The Map : 1. USA  2. Australia 
2
 (1, {'wa': 'red', 'nt': 'blue', 'q': 'red', 'nsw': 'blue', 'v': 'red', 'sa': 'green'})
Number Of Backtracks: 0
TIME TAKEN FOR EXECUTION: 0.000997304916388seconds


5. DFS with forward checking and propagation through singleton domains    [With heuristic]:
Number of run	Number of backtrack	Time taken
1	0	0.000935676746352seconds
2	0	0.000965356879976seconds
3	0	0.000193427877659seconds
4	0	0.000957886643458seconds
5	0	0.000186454690854seconds

Sample Output:
Choose The Map : 1. USA  2. Australia 
2
 (1, {'wa': 'green', 'nt': 'brown', 'q': 'green', 'nsw': 'brown', 'v': 'green', 'sa': 'yellow'})Number Of Backtracks: 0
TIME TAKEN FOR EXECUTION: 0.000935676746352seconds

6. DFS with forward checking and propagation through singleton domains    [Without heuristic]:
Number of run	Number of backtrack	Time taken
1	0	2.0298960208892822 seconds
2	0	0.16092705726623535seconds
3	0	0.15959963909444808seconds
4	0	1.5394909594480896seconds
5	0	1.348089599094496seconds

Sample Output:
Choose The Map : 1. USA  2. Australia 
2
Time taken for execution = 2.11024808883667 seconds
Number of Backtracks = 0
{'wa': 'blue', 'nt': 'green', 'q': 'blue', 'nsw': 'green', 'v': 'blue', 'sa': 'red'}
