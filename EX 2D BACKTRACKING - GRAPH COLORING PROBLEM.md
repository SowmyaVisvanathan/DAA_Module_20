# EX 2D BACKTRACKING - GRAPH COLORING PROBLEM
## DATE: 15/03/2025
## AIM:
To solve the Graph Coloring Problem using backtracking, assigning colors to the vertices of a graph such that no two adjacent vertices share the same color while minimizing the number of colors used.

## Algorithm
1. Input:
   - A graph represented by an adjacency matrix.
   - An integer m — maximum number of colors allowed.
2. Initialize:
   - Set all vertex colors to 0 (unassigned).
   - Start coloring from the first vertex (v = 0).
3. Recursive Coloring (graphColourUtil):
   - If all vertices are assigned a color (i.e., v == V), return True.
   - For each color c from 1 to m:
   - Check if color c can be assigned to vertex v using isSafe:
   - Make sure no adjacent vertex has color c.
4. If safe:
   - Assign color c to vertex v.
   - Recur for the next vertex v + 1.
   - If recursion returns True, propagate success upward.
   - Else, backtrack: remove color (colour[v] = 0).
5. No Solution:
   - If no color leads to a valid solution, return False.
6. Print Result:
   - If a solution exists, print the assigned colors for each vertex.
## Program:
```
/*
Program to implement Graph Coloring Problem using backtracking.
Developed by: Sowmya V
Register Number: 212222110045
*/

class Graph():
    def __init__(self, vertices):
        self.V = vertices
        self.graph = [[0 for column in range(vertices)]for row in range(vertices)]
    def isSafe(self, v, colour, c):
        for i in range(self.V):
            if self.graph[v][i] == 1 and colour[i] == c:
                return False
        return True
    def graphColourUtil(self, m, colour, v):
        if v==self.V:
            return True
        for c in range(1,m+1):
            if self.isSafe(v,colour,c)==True:
                colour[v]=c
                if self.graphColourUtil(m,colour,v+1)==True:
                    return True
                colour[v]=0
    def graphColouring(self, m):
        colour=[0]*self.V
        if self.graphColourUtil(m,colour,0)==None:
            return False
        print ("Solution exist and Following are the assigned colours:")
        for c in colour:
            print (c,end=' ')
        return True
```

## Output:
![image](https://github.com/user-attachments/assets/27828d10-30bd-4e03-b2c2-e75e532ccfa1)

## Result:
The Graph Coloring program executed successfully, and the colors were assigned to the vertices such that no two adjacent vertices share the same color.
