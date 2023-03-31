def n_queens(n):
    def is_safe(board, row, col):
        for i in range(row):
            if board[i] == col or \
               abs(board[i] - col) == abs(i - row):
                return False
        return True

    def solve_n_queens(board, row):
        if row == n:
            print(board)
            return
        for col in range(n):
            if is_safe(board, row, col):
                board[row] = col
                solve_n_queens(board, row + 1)
                board[row] = None

    board = [None] * n
    solve_n_queens(board, 0)

num_queens = int(input("Enter the number of queens: "))
n_queens(num_queens)