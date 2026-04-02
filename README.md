# C16_MFC3_PRECONDITIONING-ADMM-FOR-FAST-DECENTRALIZED-OPTIMIZATION

## Project Description

This project focuses on improving the efficiency of **decentralized optimization** using an advanced technique called **Preconditioned ADMM (Alternating Direction Method of Multipliers)**.

In decentralized systems, multiple nodes (or agents) collaboratively solve a global optimization problem without relying on a central controller. Each node processes its **local data** and communicates only with its neighboring nodes to reach a **common solution (consensus)**.

---

##  What We Did in This Project

We implemented and analyzed different variants of ADMM to study their performance in distributed systems.

### Step-by-step work:

1. **Formulated the decentralized optimization problem**

   * Objective: Minimize a global function composed of local functions
   * Each node has its own data and objective

2. **Implemented Standard ADMM**

   * Basic decentralized optimization algorithm
   * Nodes update variables and exchange information

3. **Identified the problem**

   * Slow convergence when the system is **ill-conditioned**
   * High number of iterations and communication rounds

4. **Applied Preconditioning**

   * Introduced a **scaling (preconditioning matrix)**
   * Improved the condition of the optimization problem
   * Accelerated convergence significantly

5. **Simulated Distributed Network**

   * Used a **ring topology with random edges**
   * Mimics real-world communication networks

6. **Generated Ill-conditioned Data**

   * Created local matrices with high condition number (~100)
   * To test algorithm robustness

---

## Models / Algorithms Used

We compared multiple ADMM-based models:

### 1. Standard ADMM

* Basic algorithm
* Slower convergence
* High communication cost

### 2. Decentralized ADMM (DADMM)

* Fully distributed version
* Works on general network graphs
* Performance depends on topology

### 3. Weighted ADMM (WDADMM)

* Uses edge weights
* Improves performance compared to DADMM

### 4. Hybrid ADMM (HADMM)

* Combines local and group communication
* Better than standard decentralized methods

### 5. Preconditioned ADMM (Our Proposed Approach)

* Applies preconditioning matrix
* Optimizes convergence speed
* Maintains full decentralization

---

## Graphs & Network Topologies

### Star Graph
- Central node connects all  
- Fast but centralized  

### Ring Graph
- Each node connects to two neighbors  
- Fully decentralized  

### Lollipop Graph
- Combination of clique + chain  
- Slower in some cases  

### Random Graph
- Real-world network simulation  
- Performance depends on structure
---

## Which Model is Best?

**Preconditioned ADMM performed the best**

* Faster convergence
* Fewer iterations required
* Reduced communication overhead
* Robust to network changes

---

## Results & Observations

From our simulations and analysis (supported by the base paper ):

### Key Results:

* Convergence speed improved significantly
* Number of iterations reduced
* Communication rounds minimized
* Better performance for ill-conditioned problems

### Important Insight:

> Adding more edges in a network does NOT always improve performance.
> Proper weighting and preconditioning are more important.

---

## Performance Analysis

* MATLAB execution time: **~50–60 seconds**
* Faster convergence compared to standard ADMM
* Efficient even for complex network structures

---

## Real-World Applications

This project is useful in:

* Multi-robot coordination
* Sensor networks
* Federated learning
* Distributed machine learning
* Smart grid optimization

---

## Final Conclusion

In this project, we demonstrated that:

* Preconditioning is a **powerful technique** to improve ADMM
* It **does not change communication structure**, only local computation
* It provides **faster, scalable, and efficient optimization**
* It is suitable for **real-world distributed systems**

---

## Summary 

We took a slow decentralized algorithm (ADMM),
improved it using **preconditioning**,
tested it on network models,
and proved that it works **faster and better** than existing methods.
