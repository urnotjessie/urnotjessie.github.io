---
layout: post
title:      "Algorithm - BFS vs. DFS"
date:       2018-12-24 21:58:14 +0000
permalink:  algorithm_-_bfs_vs_dfs
---


### Breadth-First Search

Impelementing by Queue

**Advantage: **

A BFS will find the shortest path between the starting point and any other reachable node

**Disadvantage: **

A BFS on a binary tree generally requires more memory than a DFS



### Depth-First Search

Impelementing by Stack

**Advantage: **

DFS on a binary tree generally requires less memory than BFS, because the tree's breadth can  as much as double each time it gets one level deeper, depth-first traversal of a tree uses memory proportinal to the depth of the tree, while breadth-first traversal uses memory proportinal to the breadth of the tree (how many nodes there are on the "level" that has the most nodes)

**Disadvantage: **

DFS does not necessarily find the shortst path to a node
