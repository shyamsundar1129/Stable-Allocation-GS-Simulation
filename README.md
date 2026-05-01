# Gale-Shapley Algorithm: Stable Matching Simulation

## Project Overview
This project is an object-oriented Python simulation of the **Gale-Shapley Deferred Acceptance Algorithm (1962)**[cite: 6]. It mathematically models and solves the Stable Matching Problem for two disjoint sets of equal size (e.g., Medical Residents and Hospitals) based on strict ordinal preferences[cite: 6]. 

In economic markets where price cannot dictate allocation, this algorithm ensures a perfectly stable matching where no "blocking pairs" exist meaning no two agents would mutually prefer each other over their assigned partners[cite: 6]. This work fundamentally underpins modern market design and earned Lloyd Shapley the 2012 Nobel Memorial Prize in Economic Sciences[cite: 6].

## How It Works
The algorithm utilizes a **Proposer-Reviewer** dynamic (Deferred Acceptance)[cite: 6]:
1. **Initialization:** All participants begin as "Free"[cite: 6].
2. **Proposals:** Unmatched Proposers (e.g., Residents) apply to their most preferred Reviewer (e.g., Hospital) that hasn't rejected them yet[cite: 6, 7].
3. **Deferred Acceptance:** If the Reviewer is free, they tentatively accept the proposal. If they are already matched, they compare the new proposer against their current match. They "trade up" if the new proposer is ranked higher on their preference list, freeing the old match[cite: 6, 7].
4. **Termination:** The cycle repeats until all participants are matched, guaranteeing a Proposer-Optimal stable allocation[cite: 6].

## Features & Implementation
* **Object-Oriented Design:** Implemented via a robust `GaleShapley` Python class that handles data ingestion, preference matrix tracking, and proposal logic[cite: 6, 7].
* **Dynamic Conflict Resolution:** Automatically evaluates and resolves tentative match conflicts by cross-referencing multi-dimensional preference arrays[cite: 7].
* **Algorithmic Analytics:** Tracks system states and logs "Acceptances," "Swaps," and "Rejections" to visually trace the path to equilibrium[cite: 7].

## Complexity Analysis
Because every Proposer proposes to every Reviewer at most once, the total number of operations is strictly bounded, ensuring the algorithm reaches a stable matching in a worst-case time complexity of **$\mathcal{O}(n^2)$**[cite: 6].

## How to Run the Simulation
1. Clone this repository to your local machine.
2. Ensure you have Python installed. You can also utilize the provided Jupyter Notebook (`.ipynb`) for an interactive walkthrough[cite: 7].
3. The preference dictionaries can be modified in the main script to simulate different market scenarios[cite: 7].
4. Execute the script to view the step-by-step proposal trace and the final stable matching output[cite: 7].

## Real-World Applications
Variations of this exact algorithm are used today in high-stakes allocation systems, including:
* **The National Resident Matching Program (NRMP):** Matching tens of thousands of medical graduates to residency programs annually without market unravelling[cite: 6].
* **Kidney Paired Donation:** Facilitating organ swap cycles between incompatible donor-recipient pairs[cite: 6].
