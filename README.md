# Artificial Intelligence Nanodegree
## Introductory Project: Diagonal Sudoku Solver

# Question 1 (Naked Twins)
Q: How do we use constraint propagation to solve the naked twins problem?  
A: This strategy is very similar to eliminate strategy.  We build the strategy as follows 
* for each unit , find the possible naked twins , aka. two boxes with identical two character values
  * build a value-->[box1, box2,...] map for len(value)==2
  * if len(value) == len([[box1, box2,...]]) , then, this is a naked twins
* All other boxes in that unit are not allowed to contain either of the characters.  So for all box in the unit but not naked twins, eliminate the naked twins value. 
We will put this strategy after only_choice. So we will apply eliminate-->only_choice-->naked_twins to reduce_puzzle until we solved the sudoku. 

# Question 2 (Diagonal Sudoku)
Q: How do we use constraint propagation to solve the diagonal sudoku problem?  
A: To solve diagonal sudoku problem, we need to add two diagonal units ([[A1,B2,C3,...,I9],[A9,B8,C7,...I1]]) to the sudoku units. By doing this the diagonals box constraint are also added to the peers list. This constraint will be applied to all our strategies (e.g elimination, only choice, naked twins). 
 For Example , in elimination strategy, we will also eliminate numbers in those diagonal peers. 
 

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