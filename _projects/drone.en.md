---
layout: page
title: Urban Environment UAV Flight Path Planning and Design
lang: en
date: 2026-04-18
---

This is a group designed drone planning project that implements functions such as urban environment drone logistics path planning, flight control, and obstacle recognition. I mainly participated in the design of path planning methods

<!-- excerpt -->

# Urban Environment UAV Flight Path Planning and Design

Drones are commonly seen in daily life and have taken on applications such as urban low-altitude logistics, power line inspections, and emergency rescue operations. 
This project was implemented through collaboration among multiple students from three teams, including the drone flight control group, dynamic obstacle detection and recognition group, and drone flight path planning group. 
I primarily participated in the flight path planning group, with specific tasks including:

(1) constructing grid environmental data for drone flight test zones based on elevation models (DEM) and on-site obstacle measurement data; 

(2) learning the A* algorithm and completing static global optimal flight path planning design; 

(3) implementing dynamic rapidly-exploring random trees (RRT) path planning with adaptive step sizes and dynamic obstacle considerations, effectively reducing planning time, improving obstacle avoidance success rates, and enhancing flight smoothness.

## 1 Definition and Current Status of Path Planning 

### 1.1 Definition
Drone path planning mainly solves the problem of designing the flight path of a drone from the starting point to the endpoint to complete a specified task under constraints such as obstacles and drone power characteristics, meeting safety, timeliness, efficiency, and other goals; Describe mathematically and graphically as follows:
Find a safe, collision free, and efficient path Path from the starting point Xinit to the target point Xgoal in the given flight space C, where Path is a path segment composed of a series of points in space C, Path=(Xinit,x1,x2,...,Xgoal)， Depending on the task, Path satisfies the shortest time or shortest path, as shown in the figure

![本地图片](/images/drone/fig1.jpg "define")

For dynamic urban environments, in addition to fixed flight restriction zones (obstacles), dynamic obstacles such as motor vehicles, low-speed moving maintenance vehicles, etc. should also be considered.

### 1.2 Current path planning algorithms
According to the research, it can be seen that drone path planning methods can be divided into two categories:

1) Global static planning: such as Dijkstra, A *, ant colony algorithm, etc. These algorithms are globally optimal but only suitable for static prior environments. When new dynamic obstacles are added, global replanning is required, resulting in high computational latency;

2) Local dynamic programming: such as artificial potential field method, dynamic window method (DWA), RRT series algorithms, which randomly sample without target orientation, have slow convergence speed, have a large number of inflection points in the path, and have no dynamic obstacle local reconstruction mechanism.

In practical applications, it is necessary to have a globally optimal path to save energy and improve endurance, as well as dynamic obstacle avoidance capabilities to deal with temporary obstacles in the air. Therefore, a path planning scheme of "static grid modeling+global optimal planning+dynamic real-time planning" is constructed

## 2 Construction of Static Grid for Basic Geographic Data
According to different application scenarios, the grid resolution is set to different sizes. Resolution affects the real-time performance of path planning calculations, and a balance needs to be struck between processing accuracy and real-time performance. The grid resolution chosen in this experiment is 5m * 5m

### 2.1 Grid mathematical model
Discretization the continuous two-dimensional flight space uniformly into an M × N grid matrix, defined as:

C(i,j) = 0，  (i,j)grid is the obstacle free flying area    
C(i,j) = k，  (i,j)grid is the static obstacle area, obstacle height k, if its unknown k=1
 
To ensure flight safety, when C (i, j) is a static obstacle area, expand 1-2 grids outward as a safety buffer zone to avoid drone obstacle flying.

### 2.2 Grid generation steps
1) Multi source geographic data is uniformly projected onto the same plane coordinate system;

2) Vector terrain and DEM elevation threshold segmentation, extracting obstacle contours;  

3) Contour grid marking, assigning corresponding heights to obstacle areas, setting 1 for unknown heights, and setting 1-2 surrounding grids as safety buffer zones.

## 3  A*  algorithm
### 3.1 objective function
Path planning has different objective requirements in different applications. In group experiments, flight distance is set as the overall objective function, and the goal is to minimize the flight distance while ensuring flight safety.
The objective function is defined as:

f (n)=g (n)+h (n)

g(n): Actual flight distance from the starting point to the current node n;

h(n): The planned flight distance from the current node to the target point.

There are also multiple ways to calculate g(n) and h(n), and common methods include:
Euler distance:      ![本地图片](/images/drone/dis1.png "Euler distance")

Manhattan distance:  ![本地图片](/images/drone/dis2.png "Manhattan distance") 

Chebyshev distance:  ![本地图片](/images/drone/dis3.png "Chebyshev distance")


In this experiment, the Manhattan distance commonly used for urban street grids was employed

### 3.2 Standard A * Path Planning
The standard A * algorithm is a path planning algorithm based on heuristic search, which considers both the Manhattan distance from the point to the starting point and the estimated distance from the point to the endpoint (i.e. estimated distance) when determining the next point to be searched, in order to ensure the rationality of the search. More precisely, the extension order of the standard A * algorithm is based on the minimum sum of the actual distance from the point to the starting point and the estimated distance from the point to the endpoint. During the search process, the standard A * algorithm ensures that the shortest path passing through each point, and when reaching the endpoint, the resulting path is always the optimal solution from the starting point to the endpoint. The algorithm process is as follows:

![本地图片](/images/drone/fig2.jpg "A* alg")

Open is initialized as the starting point, and the Close linked list is initially empty. Starting from the initial point of the Open linked list, adjacent neighboring points are searched in static data, and the nearest node n is selected to join the Close linked list. When node n is the destination node, it ends. Otherwise, node n continues to search for neighboring nodes
The standard A * algorithm is a widely used shortest path algorithm that is highly effective in solving shortest path problems on directed and undirected graphs. However, the A * algorithm also has some limitations: 

(1) Scalability problem: The A * algorithm can only solve the single source shortest path problem, but cannot solve the multi-source shortest path problem.

(2) Accuracy issue of estimation function: A * algorithm requires accurate estimation function for state prediction and evaluation, so inappropriate estimation function may lead to inaccurate search, and even the algorithm cannot terminate the loop.

(3) State space problem: Algorithm A is only applicable to problems where the state space is computable. For some complex state space problems, the computational complexity of Algorithm A * may be too high to obtain reasonable results.

## 4 RRT algorithm and Dynamic RRT

### 4.1 RRT algorithm
The Fast Search Random Tree RRT algorithm was proposed by Lavalle and is an incremental random sampling algorithm used to solve high-dimensional space problems with algebraic and differential constraints. The advantage of this algorithm is that it does not require system modeling or geometric partitioning of the search area, thus it has the characteristics of high coverage and extensive search, but its computational cost is relatively high.
The RRT algorithm gradually generates a tree structure in an incremental manner, utilizing random sampling and expansion strategies to explore the state space and quickly generate feasible paths. Due to its randomness and incremental nature, the RRT algorithm can adapt well to non holonomic constraints and avoid modeling the specific dynamic model of the mobile robot during the search process. Therefore, the RRT algorithm can quickly search for feasible paths for mobile robots while considering incomplete constraints, thus achieving efficient path planning.
The basic processing algorithm is as follows:
![本地图片](/images/drone/fig3.jpg "RRT Alg")

In this algorithm, M is the data structure of the map, Xinit is the starting point, and Xgoal is the target point. The main process of the algorithm is as follows:

- Random sampling: Randomly generate a node Xrand in the feasible area of the map.
- Nearest Point Search: Find the point Xear in the current map that is closest to Xrand.
- Node extension: Attempt to extend a new node Xnew along the step size direction between Xrand and Xear.
- Collision detection: Use the CollisionFree (M, E) function to check if the newly generated edges (Xnew, Xear) do not conflict with obstacles in the map.
- Node addition: If the newly generated edges do not conflict, Xnew is added to the map as a new node and connected to Xear.
- Path search: Repeat the above steps until you find the path from the starting point to the endpoint.

This algorithm utilizes random sampling and local search to gradually explore feasible paths in the map, avoiding obstacles until a path connecting the starting point and the target point is found.

### 4.2 Improved RRT Algorithm - Dynamic RRT Algorithm
Introducing real-time path updates and environment aware mechanisms, when the environment changes, the already planned path may no longer be feasible and needs to be re planned. Obtain environmental information through sensors for timely path updates and adjustments.  
Compared to the RRT algorithm, the Dynamic RRT algorithm requires pruning and merging operations based on environmental awareness, and continues random search after removing invalid nodes. The basic steps include:
1. Initialize the tree structure, including the starting and ending points, as well as the starting tree nodes;
2. Continuously expanding the tree structure through random sampling and node expansion to explore unknown regions;  
3. When the environment changes, update the tree structure based on real-time environmental information, delete paths that are no longer feasible, and re plan the path;  
4. When a feasible path is found, output the path and end the algorithm.
In dynamic environments, the efficiency and feasibility of path planning are crucial. To improve the efficiency of path planning, accelerated tree search methods can be used, such as introducing heuristic information, setting node extension ranges, etc. In order to improve the feasibility of path planning, it is necessary to introduce reward mechanisms, simplify map models, and other strategies to ensure that the planned path is feasible

Our group will conduct some experiments in the future and supplement the relevant experimental results.



---

[← Back](javascript:history.back()) [🏠 Home](/)