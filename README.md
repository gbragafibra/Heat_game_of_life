# Heat - Game Of Life

## Rules

Each cell will have a mass parameter $m$ attached to itself, such that $0 \leq m \leq 5$. According to the following expression (with $\alpha < 1$, tipically $\alpha = 3/4$):


$$
\langle \Delta Q \rangle \propto m^{\alpha}
$$


after an iteration with time-period $\tau$ each cell  will have a loss of $m$ according to the previous expression (given that $m$ is minimally capped at 0). Furthermore, each cell may have a random energetic input over said iteration of $[-2m, -m, 0, m, 2m]$. To finish, if adjacent cells have their mass parameters as:


$$
\sum_{i} m_{i} \geq \lambda 
$$

with for example $\lambda = 7$, the respective cells will form a unit that releases heat (and loses mass after said iteration) after the whole network of cells that follow the condition previously stated. 

---

Example: If two cells (with $m_{1} = m_{2} = 5$), $\sum_{i} m_{i} = 10 \geq 7$, given that $\langle \Delta Q_{1} \rangle = \langle \Delta Q_{2} \rangle \propto \frac{10^{3/4}}{2} \simeq 2.8 J$. If no such rule had been implemented, $\langle \Delta Q_{1} \rangle = \langle \Delta Q_{2} \rangle \propto 5^{3/4} \simeq 3.3 J$.

---


Finally, if:


$$
\sum_{i} m_{i} < \lambda 
$$

break unit.
