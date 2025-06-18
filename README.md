# ✈️ Airport Security Queue Simulation

This project models airport security queues using **queuing theory (M/G/1)** and simulates how various system parameters—such as arrival rates, the number of service stations, and the probability of additional screening—affect system performance. The simulation helps analyze queue length, waiting times, and utilization under different scenarios, providing insights for potential real-world optimization.

---

## 📂 Files in This Repository

- `airport_queue_simulation.ipynb`: Jupyter notebook containing the simulation code, implemented in Python.
- `Report_airport.pdf`: Full analytical report including theoretical background, simulation methodology, plots with confidence intervals, and discussion of results.
- `README.md`: Project summary and usage instructions (this file).

---

## 🧠 Problem Description

The project simulates a simplified version of an airport security system with:

- **Single server per queue**
- **Arrival process**: Poisson (exponential inter-arrival time), λ = 10 travelers/min
- **Service time**: Truncated normal distribution (μ = 0.5 min, σ = 1/6 min)
- **Additional screening**: With probability *p = 0.05*, adds extra truncated normal service time (μ = 2 min, σ = 2 min)

The system is modeled as an **M/G/1 queue**, chosen for its ability to accommodate general service distributions and single-server assumptions. The model operates under typical assumptions: FIFO queuing, independent arrivals and service times, and infinite queue capacity.

---

## 🔬 Simulation Scenarios

The simulation explores three scenarios, each tested under multiple parameter settings and compared (when applicable) with theoretical expectations.

### 1. Single Queue, No Senior Officer

- Varying arrival rates (λ ∈ [0.1, 1.9])
- 200 trials for 1000 minutes
- Closely aligned with theoretical M/G/1 expectations
- Demonstrated system instability as ρ (utilization) → 1

### 2. Multiple Queues, No Senior Officer

- Varying number of service stations (1–10)
- 100 trials for 500 minutes
- Arrival rate distributed across queues
- Queue length and wait times decrease as number of servers increases
- Theoretical and simulated results closely aligned (for n > 6)

### 3. Multiple Queues with Senior Security Officer

- Adds screening step with *p = 0.05*
- Single officer serves all queues (introduces bottleneck)
- 300 simulation trials
- Significant divergence from theory due to real-world limitations
- Queue length minimized at 5 servers; wait times continue to drop as servers increase

---

## 📊 Key Metrics

- **Average Queue Length**
- **Average Waiting Time**
- **Maximum Queue Length**
- **Utilization (ρ)**

All simulations are run with 95% confidence intervals across multiple trials for statistical robustness.

---

## 📈 Sample Results

Key findings illustrated in plots:

- Simulated results match theoretical predictions in baseline tests
- Bottlenecks caused by a single senior officer significantly increase queue lengths
- A “dip” in average queue length observed at 5 servers, explained by load distribution vs. bottleneck effects

For detailed graphs and analysis, refer to [`Report_airport.pdf`](./Report_airport.pdf)

---

## 🧰 Technologies Used

- Python
- NumPy
- SciPy
- Matplotlib
- Jupyter Notebook

---
## 🛠️ Future Improvements

- Add support for multiple senior officers to reduce bottlenecking
- Implement dynamic queue choice logic (e.g., avoid queues with pending officer checks)
- Conduct sensitivity analysis on arrival and service rates
- Create real-time visualizations or animations of queue states
