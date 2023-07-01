# Leetcode 1970. Last Day Where You Can Still Cross (Hard)


# Problem

There is a 1-based binary matrix where 0 represents land and 1 represents water. You are given integers row and col representing the number of rows and columns in the matrix, respectively.

Initially on day 0, the entire matrix is land. However, each day a new cell becomes flooded with water. You are given a 1-based 2D array cells, where cells[i] = [ri, ci] represents that on the ith day, the cell on the rith row and cith column (1-based coordinates) will be covered with water (i.e., changed to 1).

You want to find the last day that it is possible to walk from the top to the bottom by only walking on land cells. You can start from any cell in the top row and end at any cell in the bottom row. You can only travel in the four cardinal directions (left, right, up, and down).

Return the last day where it is possible to walk from the top to the bottom by only walking on land cells.

# My solution

Uses binary search to reduce the number of days to check if a path to cross exists

canCross() checks if a path exists on a specific day, by adding the first row of tiles that are land to a queue and then popping them off and adding their uncheked neighbors to the queue. I put the neighbors underneath at the front of the queue and the other neighbors at the end. It returns true if a neighbor is both land and on the bottom row, false otherwise.
