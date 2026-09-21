# LeetCode 207 - Course Schedule

## Problem Description

There are `numCourses` courses numbered from `0` to `numCourses - 1`.

Some courses have prerequisites. A prerequisite means that one course must be completed before another course.

The goal is to determine whether it is possible to finish all the courses.

If there is a cycle in the prerequisites, all courses cannot be completed.

## Example

Input:

numCourses = 2
prerequisites = [[1,0]]

This means:

Course 0 → Course 1

We can complete course 0 first and then course 1.

Output:

true

## Approach

This problem can be solved using **Topological Sorting** with **BFS**.

We calculate the number of prerequisites for every course using an `indegree` array.

Courses with zero prerequisites can be taken immediately, so we add them to a queue.

After completing a course, we remove it from the prerequisite list of the courses that depend on it.

If another course reaches an indegree of zero, we add it to the queue.

At the end, if all courses are completed, the schedule is possible. Otherwise, a cycle exists.

## Algorithm

1. Create an adjacency list to store course relationships.
2. Calculate the indegree of every course.
3. Add all courses with indegree `0` to the queue.
4. Remove courses from the queue one by one.
5. Decrease the indegree of their dependent courses.
6. Add newly available courses to the queue.
7. Count the completed courses.
8. Return `True` if all courses are completed.

## Time Complexity

**O(V + E)**

Where `V` is the number of courses and `E` is the number of prerequisite relationships.

## Space Complexity

**O(V + E)**

The graph, indegree array, and queue require extra space.

## Key Concepts

- Graph
- BFS
- Topological Sort
- Queue
- Indegree
- Cycle Detection

## Author

T.nandhini
