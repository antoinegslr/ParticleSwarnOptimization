---
marp: true
theme: sorbonne
math: katex
paginate: true
---

<!-- _class: lead -->
<div class="lead-content">

# Bibliographic project
## Generation of optimized structures through Particle Swarm Optimization
**Antoine GISSLER** - Sorbonne Université
January 2023
<div style="font-family:'Avenir', 'Avenir Next','Calibri'; color:gray; font-size:0.7em; text-align: left;">Repository: <a href="https://github.com/antoinegslr/ParticleSwarmOptimization">https://github.com/antoinegslr/ParticleSwarmOptimization</a></div>
</div>

---
<style>
div.twocols {
  margin-top: 35px;
  column-count: 2;
}
div.twocols p:first-child,
div.twocols h1:first-child,
div.twocols h2:first-child,
div.twocols ul:first-child,
div.twocols ul li:first-child,
div.twocols ul li p:first-child {
  margin-top: 0 !important;
}
div.twocols p.break {
  break-before: column;
  margin-top: 0;
}
</style>
# Introduction
<div class="twocols">
<br><br><br>
<center>

## Novel phases in ammonia-water mixtures under pressure
<h3 style="color:gray;">Victor Naden Robinson, Miriam Marqués, Yanchao Wang, Yanming Ma, Andreas Hermann</h3>
<br>
<h6 style="color:black;">Crystal structure prediction in Saturn and Uranus' mantles</h6>
</center>
<p class="break"></p>

<center>
<img src="figures/Article.png" height=600px style="border:3px solid grey;" />


</center>
</div>

---
# Introduction


<div class="twocols">
<br><br>

Crystal structure prediction requires **sampling** of multiple structures<br>
**Some existing methods:**
* Monte Carlo
* Simulated annealing
* Minima/basin hopping
* Metadynamics
* Genetic algorithm

<p class="break"></p>

![right height:450px](figures/egg_holder.png)
<center>

**Figure 1:** Eggholder function
(Nathan Rooy on [GitHub](https://github.com/nathanrooy/landscapes))

</center>
</div>

---
# Introduction

<div class="twocols">
<br>

**Crystals in Saturn and Uranus:**
* Presence of water ices and ammonia in similar quantities
* High pressures and temperatures

**Problems using previous methods:**
* High computational cost
* High energetic barriers to cross
* Has everything been sampled?
* Everything is unknown

<p class="break"></p>

![right height:400px](figures/saturn.jpeg)
<center>

**Figure 2:** Saturn by Hubble telescope
([Nasa](https://solarsystem.nasa.gov/resources/2490/saturns-rings-shine-in-hubble-portrait/?category=planets_saturn), September 2019)

</center>
</div>

---
<!-- footer: Wang et al., Crystal structure prediction via particle-swarm optimization. *Phys. Rev. B 82* (2010), 094116 -->
# Particle Swarm Optimization (PSO)
<br>

> Population-based optimization algorithm based on behaviors of birds in a flock
<div class="twocols" style="margin-top:10px; margin-bottom: -5px;">
<center>

![right height:275px](figures/bird_flock.jpg)
**Figure 3:** Bird flock, by P. D. van de Velde
</center>
<p class="break"></p>
<center>

![right height:275px](figures/PSO.png)
**Figure 4:** PSO principle, by Wang et al.


</center>
</div>

$$v_{i,j}^{t+1}=\omega v_{i,j}^t+c_1r_1(\verb+pbest+_{i,j}^t-x_{i,j}^t)+c_2r_2(\verb+gbest+_{i,j}^t-x_{i,j}^t)$$
---
<!-- footer: ""-->
# How does it work?
1. Generation of one random structure per symmetry
2. Local optimization of every structure
3. Exclusion of similar structures *(through bond characterization matrix)*
4. Generation of new structures by PSO, using personal and flock's hystories (global best minimum $\verb+gbest+$ and personnal best minimum $\verb+pbest+$)
5. Repetition of the three last steps until convergence (difference between two consecutive minimal values less than a defined epsilon)
> The program then returns the configuration associated to the lowest energy

---

# Trial over a basic 2D function

<div class="twocols" style="margin-top:10px; margin-bottom: -5px;">
<center>

![right height:400px](figures/PSO1.gif)
**Figure 5:** Global minimum over time
</center>
<p class="break"></p>
<center>

![right height:400px](figures/PSO2.gif)
**Figure 6:** Evolution of particles over time


</center>
</div>

---
<!--footer: Bethkenhagen et al., Superionic phases of the 1:1 water-ammonia mixture. *J. Phys. Chem. A 119* (2015), 10582-10588 -->
# PSO for crystal structure prediction
<br><br>

<div class="twocols" style="margin-top:10px; margin-bottom: -5px;">

## Results from previous studies
Three stable mixtures were found
* **AMH**  $\small\longrightarrow( \mathrm{H}_2\mathrm{O})(\mathrm{N}\mathrm{H}_3)$
* **ADH** $\small\longrightarrow( \mathrm{H}_2\mathrm{O})_2(\mathrm{N}\mathrm{H}_3)$
* **AHH** $\small\longrightarrow( \mathrm{H}_2\mathrm{O})(\mathrm{N}\mathrm{H}_3)_2$

For each mixture, **various phases** depending on pressure (see Figure)
<center>

$\small P4/nmm \overset{38.3}{\rightarrow} Ima2 \overset{149}{\rightarrow} Pma2 \overset{527}{\rightarrow} Pm$

</center>
<p class="break"></p>
<center>

![right height:375px](figures/Bethkenhagen.png)
**Figure 7:** Phase diagram determined by Bethkenhagen et al. (using genetic algorithm)


</center>
</div>


---
<!--footer: Naden Robinson et al., Novel phases in ammonia-water mixtures under pressure. *J. Chem. Phys. 149* (2018), 234501-->
# PSO for crystal structure prediction
<br><br>

> Using PSO, authors were able to show that new stuctures might be more stable


<center><img src="figures/PD_AMH.png" width=58% />

**Figure 7:** Relative enthalpies of AMH structures
</center>

---
# PSO for crystal structure prediction
<br>

> Authors also discovered the existence of another mixture : AQH $\footnotesize\longrightarrow( \mathrm{H}_2\mathrm{O})(\mathrm{N}\mathrm{H}_3)_4$
<center>

![height:370px](figures/AQH.png)
**Figure 8:** AQH-$\small P2_1/m$ structure at 40 GPa
</center>

---
# Elaboration of final phase diagram
<br><center>

![height:500px](figures/phase-diagram.png)
**Figure 9:** Phase diagram for binary ammonia-water mixtures as a function of pressure

</center>

---
<!--footer: ""-->
# Conclusion
* Discovery of **a new phase and new stable structures** using Particle Swarm Optimization
* Techniques implemented in the algorithm by Wang et al. (symmetry constraints, bond characterization matrix), make it possible to **reduce the number of iterations**
* PSO seems like a good method for this study case
* But will certainly not become the gold standard
  - Dynamics are not implemented
  - When starting point is given, some techniques might be faster
