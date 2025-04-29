# EX 2B BACKTRACKING - NQUEEN PROBLEM
## DATE: 08/03/2025
## AIM:
To solve the N-Queen problem using backtracking, which places N queens on an N*N chessboard such that no two queens threaten each other.

## Algorithm

## Program:
```
/*
Program to implement N-Queen problem using backtracking.
Developed by: Sowmya V
Register Number: 212222110045
*/
global N
N = int(input())
def printSolution(board):
    for i in range(N):
        for j in range(N):
            print(board[i][j], end = " ")
        print()
def isSafe(board, row, col):
    for i in range(col):
        if board[row][i] == 1:
            return False
    for i, j in zip(range(row, -1, -1),
                    range(col, -1, -1)):
        if board[i][j] == 1:
            return False
    for i, j in zip(range(row, N, 1),
                    range(col, -1, -1)):
        if board[i][j] == 1:
            return False
    return True
def solveNQUtil(board, col):
    if col>=N:
        return True
    for row in range(N):
        if isSafe(board,row,col):
            board[row][col]=1
            if solveNQUtil(board,col+1):
                return True
            board[row][col]=0
    return False

def solveNQ():
    board = [ [0, 0, 0, 0],
              [0, 0, 0, 0],
              [0, 0, 0, 0],
              [0, 0, 0, 0]]
              
    if solveNQUtil(board, 0) == False:
        print ("Solution does not exist")
        return False
    printSolution(board)
    return True
solveNQ()
```
## Output:
![image](https://github.com/user-attachments/assets/78712159-b42e-4be1-82fb-87c6742d4177)

## Result:
The N-Queens program executed successfully, and a valid board configuration was generated.
