# Sudoku-Grid-Solver
sudoku grid solver which spawns the sudoku puzzle with various difficulty levels and also spawns solutions. 

Packages Used : random, contextlib, io

Steps:

1. Works by creating empty board with null values
2. Enters a random number at a random (row, column)
3. checks it the same value is present in the 3x3 grid that it is and if the same value is in the same row/column
4. Do this for all values
5. It is possible that after this the code couldn't solve the puzzle as it encountered some same value at the same row/column at the end, thus run the loop over and over till a sudoku board can be created if so return the board before and after solving
6. I used contextlib to get the state of the board before being solved to output it first
