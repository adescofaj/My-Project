ROUTING OPTIMISATION FOR AERONAUTICAL NETWORKS
ABSTRACT

With a growing demand for internet access among passenger airplanes, aeronautical ad-hoc networks (AANETs) have stepped up to meet this demand. But there is a limited transmission, and it is quite expensive to transmit the internet. To provide this, there needs to be an optimal routing path to a ground station (GS). The end-to-end data transmission rate and end-to-end latency are very important to determine the optimal data packet route. Passenger airplanes can also serve as mobile ground stations. In this paper, we have two objectives. A single objective of finding a route that has the maximum end-to-end data transmission rate among airplanes that can connect to ground stations and multiple objectives of finding the maximum end-to-end data transmission rate with a minimum end-to-end latency for all airplanes that can connect to ground stations. Two algorithms are deployed to solve this problem, the A-star algorithm, and the Ant Colony algorithm. It was concluded that A-star has the shortest routing path, but ACO shows more reliability in terms of performance.
INTRODUCTION

When collecting quantitative methods used in decision-making and physical system analysis at individual and communal levels, optimization is a very important technique. To implement this technique, it is very important to make a quantitative assessment of the performance of the system under exploration, which is the objective. This objective is determined by certain features of the system, these are called variables, and are usually unknown (Nocedal and Wright 2006). The values of a group of independent variables that minimize a known value objective function are deduced by optimization (Hocking et al. 2002). Mathematically, optimization is the minimization or maximization of a function subject to constraints on its variables (Brownlee 2021).
Modelling is the process of establishing the objectives, variables, and constraints for a specific task. The first step in the optimization process—and occasionally the most crucial step—is the creation of a suitable model (Nocedal and Wright 2006). Function optimization is the problem of finding the set of inputs to a target objective function that results in the minimum or maximum of the function.
Local or global optimization is a common way to describe optimization issues. Techniques for local and global optimization Investigate various options to find the best solution. In general, local optimization techniques are “greedier” because they tend to ignore other search spaces in favour of going down the most promising path already established. This kind of optimization ought to work better for straightforward systems with a limited number of well-defined variables that need to be optimized.
Despite its likeliness to take more time, global optimization concentrates on locating the route to the best potential solution throughout the entire search space. This enables the development of more trustworthy solutions, though it might take a little longer to get there. This could be a good strategy to use if the system's various variables have an unknowable relationship to one another or if the system is more complicated or a "black box."
PROBLEM
Even as all wireless generation systems have improved in transmission and throughput, there has only been a focus on traditional coverage, hence the improvement and predictions for higher profit margins for service providers. 5G wireless system is now able to transmit between 100 Megabits-per-second (Mbps) and 20 Gigabits-per-second (Gbps) at peak times. However, passenger airplanes have limited internet access, and are also expensive.

This has brought the emergence of aeronautical ad-hoc networks (AANETs) to provide internet to airplanes (Zhang et al. 2021). Passenger airplanes can also be used as mobile ground stations to provide internet to places that are difficult to transmit and maintain wireless provision. To provide Internet access to passengers onboard, each airplane needs to find an optimal data packet routing path to a ground station (GS) in terms of one or two more objectives to be optimized.
 
Figure 1: Airplanes connecting from ground stations.

To find an optimal data packet routing path, there are two metrics to be considered, end-to-end data transmission rate and end-to-end latency. The end-to-end latency is the sum of all delays imposed by each link (passenger airplanes) and is traditionally calculated in milliseconds (Ms) while the end-to-end data transmission rate is the minimum transmission rate of each link (passenger airplanes) in the routing path, which is calculated in megabits-per-second (Mbps).
 
Figure 2: Latency is the delay (time in between) imposed by each connecting airplane.
 
Figure 3: The end-to-end latency is the sum of all delays imposed by each link (85ms)

 
Figure 4: End-to-End Data Transmission Rate is the minimum transmission rate of each link in the routing path (5m^2/h)

The transmission rate of a link is determined by the distance between a pair of communicating airplanes which are given in the table in (Fig 5). With 740 km being the maximum switching threshold. If the distance between a pair of communication airplanes is 200km, so 190km < 200km < 300km, the data transmission rate between both airplanes will be 63.970 Mbps. If the distance is 680km, then 500km < 680km < 740km, the data transmission rate between them will be 31.895 Mbps. For more than 740km, there will be no data transmission.
 
Figure 5: Data Transmission Rate
The locations of the communicating airplanes are represented in 3D Cartesian coordinates and the distance between a pair of airplanes is given as:
 
Figure 6: Where "Px,a", "Py,a" and "Pz,a" are the 3D Cartesian coordinates of a pair of communicating airplanes, while "Px,b", "Py,b" and "Pz,b" are those of the other pair of communicating airplanes.

OPTIMIZATION PROBLEMS

1.	Single-objective optimization: Finding a routing path having the maximum end-to-end data transmission rate for each airplane that can access any of a GS, either at Heathrow Airport (LHR) (Latitude, Longitude, Altitude) = (51.4700° N, 0.4543° W, 81.73 feet) or Newark Liberty International Airport (EWR) (Latitude, Longitude, Altitude) = (40.6895° N, 74.1745° W, 8.72 feet).
2.	Multiple-objective optimization: Finding a routing path having the maximum end-to-end data transmission rate and minimum end-to-end latency for each airplane that can access any of a GS, either at Heathrow airport (Latitude, Longitude, Altitude) = (51.4700° N, 0.4543° W, 81.73 feet) or Newark Liberty International Airport (Latitude, Longitude, Altitude) = (40.6895° N, 74.1745° W, 8.72 feet).

METHODOLOGY

Two optimization algorithms will be implemented in solving these two problems, they are the “Ant Colony” and the “A-star” optimization algorithm respectively.

Ant colony optimization algorithms (ACO)
ACO is a population-based search technique influenced by ant behaviour for resolving multimodal optimization issues. Naturally, some ant species roam at first, then return to their colony after locating food as well as leaving pheromone trails. If other ants discover such a route, they are more likely to follow it rather than continue moving at random, revisiting and strengthening the pheromone trails if they subsequently find food. The shorter the distance, the longer the pheromone trail lasts, and as more ants follow the pheromone trail, the longer the trail lasts because they all will be leaving trails.
Because the pheromone levels are equal in the first cycle, the decisions are based on distances and some noise. On the way back all ants or the selected number of best ants deposit pheromones on the paths they travelled, this is done to encourage ants to give more priority to shorter routes.

A-Star Algorithm
A-star is a graph traversal and route search algorithm that is widely used in computer science because of its thoroughness and allocative efficiency. A-star is a best-first search method that is written in terms of weighted graphs. It starts at a particular starting node in a network and seeks to find the shortest path to the specified goal node (end-to-end transmission rate, shortest distance, etc.). It accomplishes this by keeping track of a tree of paths leading from the start node and extending each of those paths by one edge until its termination requirement is met (Wikipedia Contributors 2019).
It must decide which of its paths to extend to for every iteration of its main loop. It bases its decision on the cost of the path as well as an estimate of the cost of extending the path leading to the target. A-star does this by choosing the path that minimizes “f(n) = g(n) + h(n)”, where n is the subsequent node on the path, g(n) is the cost of the path from the first node to n, and h(n) is an objective function that estimates the cost of the cheapest path from n to the destination. The iteration ends when the path it selects to extend is a path from beginning to destination, or when there are no paths qualified for an extension. If the objective function does not exceed the real cost of getting to the destination, A-star will always return the minimum cost path from start to destination.

CONCLUSION

A-Star has the shortest routing path with an average delay of 222.22ms and an average data transmission rate of 35.40Mbps, but ACO shows more reliability in terms of performance with a higher average data transmission rate of 48.42Mbps but an average delay of 799.07ms.





Reference list
Brownlee, J., 2021. Local Optimization Versus Global Optimization [online]. MachineLearningMastery.com. Available from: https://machinelearningmastery.com/local-optimization-versus-global-optimization/#:~:text=Local%20optimization%20involves%20finding%20the.
Hocking, D., Nougués, J. M., Rodríguez, J. C. and Sama, S., 2002. Chapter 3.3 - Simulation, Design & Analysis [online]. ScienceDirect. Available from: https://www.sciencedirect.com/science/article/abs/pii/S1570794602800104 [Accessed 12 Jan 2023].
Nocedal, J. and Wright, S. J., 2006. Introduction. Springer Series in Operations Research and Financial Engineering, 1–9.
Wikipedia Contributors, 2019. A* search algorithm [online]. Wikipedia. Available from: https://en.wikipedia.org/wiki/A.
Zhang, J., Xiang, L., Liu, D., Cui, J., Ng, S. X., Maunder, R. G., Graeupl, T., Carsten-Fiebig, U. and Hanzo, L., 2021. Semi-Stochastic Aircraft Mobility Modelling for Aeronautical Networks: An Australian Case-Study Based on Real Flight Data. IEEE Transactions on Vehicular Technology [online], 70 (10), 10763–10779. Available from: https://ieeexplore.ieee.org/document/9511787 [Accessed 12 Jan 2023].

