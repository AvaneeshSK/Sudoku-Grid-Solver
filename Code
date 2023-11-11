import random
from contextlib import redirect_stdout
from io import StringIO


def solve_sudoku(board):
    # Find the first empty cell (cell with 0 value)
    empty_cell = find_empty_cell(board)

    # If there are no empty cells, the puzzle is solved
    if not empty_cell:
        return True

    row, col = empty_cell
    # Try filling the cell with a number from 1 to 9
    for num in range(1, 10):
        if is_valid_move(board, row, col, num):
            # If the move is valid, assign the number to the cell
            board[row][col] = num

            # Recursively try to solve the rest of the puzzle with the same num
            if solve_sudoku(board):
                return True

            # If the puzzle cannot be solved with the current assignment, backtrack
            board[row][col] = ' '

    # If none of the numbers (1-9) work, return False to trigger backtracking
    return False


def find_empty_cell(board):
    # Find the first empty cell (cell with a 0 value)
    for i in range(9):
        for j in range(9):
            if board[i][j] == ' ':
                return (i, j)
    return None


def is_valid_move(board, row, col, num):
    # Check if 'num' is a valid move for the cell at (row, col)

    # Check the row
    if num in board[row]:
        return False

    # Check the column
    if num in [board[i][col] for i in range(9)]:
        return False

    # Check the 3x3 subgrid
    if (row == 0 or row == 3 or row == 6) and col <= 2:
        for i in range(row, row+3):
            for j in range(3):
                if board[i][j] == num:
                    return False
    elif (row == 1 or row == 2) and col <= 2:
        for i in range(0, 3):
            for j in range(3):
                if board[i][j] == num:
                    return False
    elif (row == 1 or row == 2) and col > 2 and col <= 5:
        for i in range(0, 3):
            for j in range(3, 6):
                if board[i][j] == num:
                    return False
    elif (row == 4 or row == 5) and col > 5 and col <= 8:
        for i in range(3, 6):
            for j in range(6, 9):
                if board[i][j] == num:
                    return False
    elif (row == 4 or row == 5) and col <= 2:
        for i in range(3, 6):
            for j in range(3):
                if board[i][j] == num:
                    return False
    elif (row == 4 or row == 5) and col > 2 and col <= 5:
        for i in range(3, 6):
            for j in range(3, 6):
                if board[i][j] == num:
                    return False
    elif (row == 7 or row == 8) and col <= 2:
        for i in range(6, 9):
            for j in range(3):
                if board[i][j] == num:
                    return False
    elif (row == 7 or row == 8) and col > 2 and col <= 5:
        for i in range(6, 9):
            for j in range(3, 6):
                if board[i][j] == num:
                    return False
    elif (row == 7 or row == 8) and col > 5 and col <= 8:
        for i in range(6, 9):
            for j in range(6, 9):
                if board[i][j] == num:
                    return False
    elif (row == 0 or row == 3 or row == 6) and col > 2 and col <= 5:
        for i in range(row, row+3):
            for j in range(3, 6):
                if board[i][j] == num:
                    return False
    elif (row == 0 or row == 3 or row == 6) and col > 5 and col <= 8:
        for i in range(row, row+3):
            for j in range(6, 9):
                if board[i][j] == num:
                    return False

    return True


def board_design(board):

    print(' ___________  ___________  ___________ ')
    for i in range(9):
        if i % 3 == 0 and i != 0:
            print(' -----------  -----------  ----------- ')
        print(f'| {board[i][0]} | {board[i][1]} | {board[i][2]} || {board[i][3]} | {board[i][4]} | {board[i][5]} || {board[i][6]} | {board[i][7]} | {board[i][8]} |')
    print(' -----------  -----------  ----------- ')


def assign(board):
    count = 0
    while count < 25:
        num = random.randint(1, 9)
        row = random.randint(0, 8)
        col = random.randint(0, 8)
        if board[row][col] == ' ':
            flag = False
            # check the rows and cols
            for i in range(9):
                if board[row][i] == num or board[i][col] == num:
                    flag = True
                    continue
            # check the subgrid
            if flag == False:
                flag2 = False
                if (row == 0 or row == 3 or row == 6) and col <= 2:
                    for i in range(row, row+3):
                        for j in range(3):
                            if board[i][j] == num:
                                flag2 = True
                elif (row == 1 or row == 2) and col <= 2:
                    for i in range(0, 3):
                        for j in range(3):
                            if board[i][j] == num:
                                flag2 = True
                elif (row == 1 or row == 2) and col > 2 and col <= 5:
                    for i in range(0, 3):
                        for j in range(3, 6):
                            if board[i][j] == num:
                                flag2 = True
                elif (row == 4 or row == 5) and col > 5 and col <= 8:
                    for i in range(3, 6):
                        for j in range(6, 9):
                            if board[i][j] == num:
                                flag2 = True
                elif (row == 4 or row == 5) and col <= 2:
                    for i in range(3, 6):
                        for j in range(3):
                            if board[i][j] == num:
                                flag2 = True
                elif (row == 4 or row == 5) and col > 2 and col <= 5:
                    for i in range(3, 6):
                        for j in range(3, 6):
                            if board[i][j] == num:
                                flag2 = True
                elif (row == 7 or row == 8) and col <= 2:
                    for i in range(6, 9):
                        for j in range(3):
                            if board[i][j] == num:
                                flag2 = True
                elif (row == 7 or row == 8) and col > 2 and col <= 5:
                    for i in range(6, 9):
                        for j in range(3, 6):
                            if board[i][j] == num:
                                flag2 = True
                elif (row == 7 or row == 8) and col > 5 and col <= 8:
                    for i in range(6, 9):
                        for j in range(6, 9):
                            if board[i][j] == num:
                                flag2 = True
                elif (row == 0 or row == 3 or row == 6) and col > 2 and col <= 5:
                    for i in range(row, row+3):
                        for j in range(3, 6):
                            if board[i][j] == num:
                                flag2 = True
                elif (row == 0 or row == 3 or row == 6) and col > 5 and col <= 8:
                    for i in range(row, row+3):
                        for j in range(6, 9):
                            if board[i][j] == num:
                                flag2 = True
            if flag2 == False and flag == False:
                board[row][col] = num
                count += 1
            else:
                continue


def remove_vals(board, difficulty):
    if difficulty == 'easy':
        n = 45
    elif difficulty == 'medium':
        n = 55
    else:
        n = 70
    count = 0
    while count < n:
        rr, cc = random.randint(0, 8),  random.randint(0, 8)
        # access by (val, val)
        if board[rr][cc] != ' ':
            board[rr][cc] = ' '
            count += 1


# MAIN DRIVER: sometimes it is possible that the sudoku cannot be solved with current combinations therefore we run it continuously using True loop continuously to find a sudoku that can be solved if so return that sudoku without solutions and then with solutions
while True:

    board = [[' ' for _ in range(9)] for _ in range(9)]
    assign(board)
    solve_sudoku(board)
    # check if sudoku is solved
    status_flag = False
    for i in range(0, 9):
        for j in range(0, 9):
            if board[i][j] == ' ':
                status_flag = True
    if status_flag == False:
        print('Welcome to Sudoku by Avi')
        difficulty = input('Select Difficulty (easy, medium, hard) : ').lower()

        output_buffer = StringIO()
        with redirect_stdout(output_buffer):
            board_design(board)
        captured_output = output_buffer.getvalue()

        print('Sudoku:')
        remove_vals(board, difficulty)
        board_design(board)

        print('Sudoku Solution: ')
        print(captured_output)

        break
