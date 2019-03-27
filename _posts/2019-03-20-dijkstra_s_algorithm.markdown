---
layout: post
title:      "Dijkstra’s Algorithm"
date:       2019-03-20 21:02:32 -0400
permalink:  dijkstra_s_algorithm
---


![](https://farm8.staticflickr.com/7909/32489335677_d40418fb39_z.jpg)

One of the question in my resent code challenge was related to a physical algorithm.  I've been explained ahead of time that during the test I will be  asked to write an algorithm to solve a problem related to the physical world. e.g. Given the topology of a mountain pass as an array, write an algorithm to figure out the cheapest way to build a road over the pass. 

First what came to my mind after reading that was Dijkstra's algorithm  also known as Dijkstra’s Shortest Path First algorithm or, SPF algorithm.  In many real world situations we are looking for the efficient solution  - optimal distance or cheapest cost. Conceived by computer scientist Edsger W. Dijkstra in 1956 and published three years later the algorithm that is used to calculate the shortest path between two nodes on a graph, now days even has applications in routing network traffic, machine learning, and artificial intelligence. 

For the algorithm to work, the graph must meet three conditions:
1.	Edges have non-negative weights 
2.	Weights are  directional  A->B may be not equal  B->A
3. The graph is acyclic,  after moving A->B, we will not consider moving back to vertex B from vertex A as this would create an infinite number of routes


The algorithm would take the Graph and starting and eding point.

1  function Dijkstra(Graph, start, end):
 2
 3      create vertex set Q
 4
 5      for each vertex v in Graph:             
 6          dist[v] ← INFINITY                  
 7          prev[v] ← UNDEFINED                 
 8          add v to Q                      
10      dist[start] ← 0                        
11      
12      while Q is not empty:
13          u ← vertex in Q with min dist[source]    
14                                              
15          remove u from Q 
16          
17          for each neighbor v of u:           
18              alt ← dist[u] + length(u, v)
19              if alt < dist[v]:               
20                  dist[v] ← alt 
21                  prev[v] ← u 
22
23      return dist[], prev[]

This algorithm calculates the shortest path from start point to all the nodes in the Graph. If we are interested in only calculating the shortest path from start to end we can terminate algorithm after line 15 when u is equal to end. 

A more general problem would be to find all the shortest paths between source and target (there might be several different ones of the same length). Then instead of storing only a single node in each entry of prev[] we would store all nodes satisfying the relaxation condition.

One of the variations of this algorithm uses a priority queue. Such data structure leads to a faster computing time. 
Algorithm in Javascript  could be found [here.](https://www.tutorialspoint.com/Dijkstra-s-algorithm-in-Javascript) 

