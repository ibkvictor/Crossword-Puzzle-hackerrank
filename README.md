# Crossword-Puzzle-hackerrank

This is a repo of my solution to the challenge: Crossword Puzzle. By successful programming a computer agent to solve any crossword puzzle.
The repo contains a file crosswordPuzzle.py that can be run to solve a crossword puzzle

## Method
I chose to solve the problem using a method called backtracking while also appropriating node consistency. 

First, I create a framework for all the variable of the puzzle and the properties these variables would possess. Next, I created a method/function "creating_variables()" that essientially checks through each space in the puzzle and creates of variable of spaces expected to be filled with words. The function returns a list of all the variables found.

To solve the puzzle using backtracking a couple of steps are involved, namely:
selecting unassigned variable (parts of the puzzle yet to be solved)
looping through the domain of this selected variable to try out values
checking if the value is consistent with the assignments (if it fit in the puzzle)
appending the value
recursively backtracking using the new set of assigments
repeatedly checking if assignment is complete (if the puzzle is solved)

Thus requiring that I created a function to check for unassigned variables, the function returns a variable that is yet to be assigned. Next, I "checked for consistency" by creating functions that check for overlaps in variables that have letters in common (parts of the puzzle that had intersections), "overlaps()"; enforced node consistency ensuring that length of words in the domain of a variable correspond with the nubmer of cells in the variable, "node_consistency()"; and checked based on the constraint that words fit in the space for the cells of the variable without conflicting intersection with other words for other variables, "consistent()".

Finally, I proceed ot implement backtracking using my abstractions from the previously defined functions and implemented a function to present the resulting puzzle as one with the words put in their correct position.

## Challenges
Scaling: Due to the complex nature of the algorithm, I fear that it may not provide a quick solution to problems 

## Future Improvements
Including Heuristics like:

Arc Consistency for inference

Mimimium Remaining value for selecting unassigned variable optimally by variables with lowest number of remaining values in domain.

Degree for selecting unassigned variable in an optimal manner, selecting the variables with the most number of variables link to it (constraint to it) thus elemination early possibility of failures.

Least Common Value for selecting vales to assign an unassigned variable by ordering the domain in highest to lowest values (words) that rule out other words in domain of overlapping variables from being assigned.

## Results

![alt text](https://github.com/ibkvictor/Crossword-Puzzle-hackerrank/blob/main/Screen%20Shot%202020-11-21%20at%2004.01.07.png?raw=true)

Passing all the test cases on Hackerrank:
![alt text](https://github.com/ibkvictor/Crossword-Puzzle-hackerrank/blob/main/Screen%20Shot%202020-11-21%20at%2004.01.29.png?raw=true)

The unsolved puzzle
!(https://github.com/ibkvictor/Crossword-Puzzle-hackerrank/blob/main/Screen%20Shot%202020-11-21%20at%2004.01.29.png)

The solved puzzle
!(https://github.com/ibkvictor/Crossword-Puzzle-hackerrank/blob/main/Screen%20Shot%202020-11-21%20at%2004.01.07.png)


## Challenge Source
https://www.hackerrank.com/challenges/crossword-puzzle/problem
