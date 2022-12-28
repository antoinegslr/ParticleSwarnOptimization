---
marp: true
theme: sorbonne
class: invert
---

<!-- _class: lead -->
<div class="lead-content">

# Bibliographic project
## Generation of optimized structures through Particle Swarn Optimization
By **Antoine GISSLER** - Sorbonne Université
2022-2023
</div>

---
# Introduction

<table>
    <tr>
    <th width=50%><img src="figures/bird_flock.jpg" width=100%/></th>
    <th>s</th>
    </tr>
</table>

---
# Slide 1: Introduction

Definition: Particle Swarm Optimization (PSO) is a population-based optimization algorithm that simulates the social behavior of birds or insects, such as flocking or swarming.
Objective: The goal of PSO is to find the optimal solution to a given optimization problem, such as finding the minimum or maximum of a function, or the best configuration of a system.

---
# Slide 2: How it works

Each "particle" in the swarm represents a potential solution to the optimization problem.
The particles move through the solution space and update their position based on their own experience and the experience of other particles.
The position of each particle is updated using a velocity vector, which is influenced by the particle's current position, the best position it has found so far (called the "personal best"), and the best position found by the entire swarm (called the "global best").
The velocity and position updates are performed iteratively until a satisfactory solution is found or a predetermined number of iterations is reached.

---
# Slide 3: Advantages and disadvantages

## Advantages: 
PSO is simple to implement, has few parameters to tune, and can handle large and complex optimization problems. It is also robust and can find good solutions quickly.
## Disadvantages: 
PSO is sensitive to the initial positions of the particles and can get stuck in local optima. It may also require more computational resources compared to some other optimization algorithms.

---
# Slide 4: Applications

PSO has been applied to various fields, including engineering, computer science, finance, and biology. Some examples of problems that have been solved using PSO include:
* Function optimization
* Feature selection
* Clustering
* Neural network training
* Scheduling
* Control
* Data mining

---
# Slide 5: Conclusion

In summary, PSO is a powerful and versatile optimization algorithm that can find good solutions to a wide range of problems. However, it may not always be the best choice for every problem, and it is important to consider the trade-offs and limitations of using PSO.
