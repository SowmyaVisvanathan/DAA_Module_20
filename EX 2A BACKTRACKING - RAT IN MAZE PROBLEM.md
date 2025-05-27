# EX 2A BACKTRACKING - RAT IN MAZE PROBLEM
## DATE: 04/03/25
## AIM:
To implement the Rat in a Maze problem using backtracking and find all possible paths from the start to the destination in a given maze.

## Algorithm
1. Start
2. Input: A 2D binary matrix maze[N][N] where:
   - 1 represents open paths
   - 0 represents blocked cells
3. Initialize: sol[N][N] – a solution matrix of the same size as maze, initialized with 0s
4. Call solveMazeUtil(maze, 0, 0, sol)
   - Start from the top-left corner (0,0)
5. If (x, y) is the destination (N-1, N-1):
   - Set sol[x][y] = 1
   - Return True
6. If maze[x][y] is a valid move (i.e., safe):
   - Mark current cell as part of the path → sol[x][y] = 1
   - Try moving in the following directions:
   - Move down → solveMazeUtil(x+1, y, sol)
   - Move right → solveMazeUtil(x, y+1, sol)
   - If either returns True, propagate the success upward by returning True
   - If both moves fail: Backtrack: set sol[x][y] = 0
   - Return False
7. If the cell is not safe, return False 

## Program:
```
/*
Program to implement Rat in a Maze.
Developed by: Sowmya V
Register Number: 212222110045
*/

N = 4
def printSolution( sol ):
    for i in sol:
        for j in i:
            print(str(j) + " ", end ="")
        print("")
def isSafe( maze, x, y ):
    if x >= 0 and x < N and y >= 0 and y < N and maze[x][y] == 1:
        return True
    return False
def solveMaze( maze ):
    sol = [ [ 0 for j in range(4) ] for i in range(4) ]
    if solveMazeUtil(maze, 0, 0, sol) == False:
        print("Solution doesn't exist");
        return False
    printSolution(sol)
    return True
def solveMazeUtil(maze, x, y, sol):
    if x == N - 1 and y == N - 1:
        sol[x][y] = 1
        return True
        "add code here"
    if isSafe(maze,x,y)==True:
        sol[x][y]=1
        if solveMazeUtil(maze,x+1,y,sol)==True:
            return True
        if solveMazeUtil(maze,x,y+1,sol)==True:
            return True
        sol[x][y]=0
        return False

if __name__ == "__main__":
    maze = [ [1, 0, 0, 0],
             [1, 1, 0, 1],
             [0, 1, 0, 0],
             [1, 1, 1, 1] ]
              
    solveMaze(maze)
```
## Output:
![image](https://github.com/user-attachments/assets/9480dd1c-1019-45ac-b49a-e2906f8bb44f)

## Result:
The Rat in a Maze program executed successfully, and a valid path from the start to the destination was found and display.
