# Artificial Intelligence Nanodegree
## Introductory Project: Diagonal Sudoku Solver

# Question 1 (Naked Twins)
Q: How do we use constraint propagation to solve the naked twins problem?  
A: Constraint propogation: is an inferential form of establishing and eliminating improbable values for a solution.
Naked Twins: If two boxes within an unit have the same probable two values, we can infer positively confidently that no other box in the same unit can have those two values. We can eliminate those two values as probable values for all other boxes in that unit.

As an example, if in an unit [A3, B3, C3, D3, E3, F3, G3, H3, I3] the boxes F3 and I3 have "23" as possible values.
The boxes F3 and I3 are called Naked Twins as if "2" were the solution for F3 then the only solution for I3 would be "3" and vice versa.
Therefore no box other than F3 and I3 in the unit can have "2" or "3" as possible values and can be removed.

This same concept can be extended to triplets, quadruplets etc...

# Question 2 (Diagonal Sudoku)
Q: How do we use constraint propagation to solve the diagonal sudoku problem?  
A: Diagonoal Sudoku: is similar to regular sudoku with the added constraint that the units formed by the diagonals ['A1', 'B2', 'C3', 'D4', 'E5', 'F6', 'G7', 'H8', 'I9'] and ['A9', 'B8', 'C7', 'D6', 'E5', 'F4', 'G3', 'H2', 'I1'] should also adhere to the rule that the numbers 1 to 9 should all appear exactly once.

We use two constraint propogation techniques

1) Elimination: If a box has a value assigned then none of its peers can have this value.
For example if box A1 has a value of "2" then none of its peers in its square unit - [ A1, A2, A3, B1, B2, B3, C1, C2, C3], column unit - [A1, B1, C1, D1, E1, F1, G1, H1, I1], row unit - [A1, A2, A3, A4, A5, A6, A7, A8, A9] and diagonal unit - ['A1', 'B2', 'C3', 'D4', 'E5', 'F6', 'G7', 'H8', 'I9'] can have the value "2"

2) Only Choice: If in an unit, there is only one box which has a certain digit as a possible solution then that box can be assigned that value.

Example:
![Only choice example](images/only-choice.png "Only choice example")
In the above image, that depicts a square unit, the top right box is the only box that has "1" as a possible solution. Hence that box can be assigned the value "1"


### Install

This project requires **Python 3**.

We recommend students install [Anaconda](https://www.continuum.io/downloads), a pre-packaged Python distribution that contains all of the necessary libraries and software for this project. 
Please try using the environment we provided in the Anaconda lesson of the Nanodegree.

##### Optional: Pygame

Optionally, you can also install pygame if you want to see your visualization. If you've followed our instructions for setting up our conda environment, you should be all set.

If not, please see how to download pygame [here](http://www.pygame.org/download.shtml).

### Code

* `solutions.py` - You'll fill this in as part of your solution.
* `solution_test.py` - Do not modify this. You can test your solution by running `python solution_test.py`.
* `PySudoku.py` - Do not modify this. This is code for visualizing your solution.
* `visualize.py` - Do not modify this. This is code for visualizing your solution.

### Visualizing

To visualize your solution, please only assign values to the values_dict using the ```assign_values``` function provided in solution.py

### Data

The data consists of a text file of diagonal sudokus for you to solve.
