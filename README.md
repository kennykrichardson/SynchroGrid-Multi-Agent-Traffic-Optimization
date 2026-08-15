# 🚦 SynchroGrid

### Adaptive Multi-Agent Traffic Optimization Simulator

**SynchroGrid** is a Python-based traffic simulation that models an urban road network populated by autonomous vehicles and dynamically controlled traffic signals.

The project explores how different traffic-control strategies affect **congestion, waiting time, throughput, travel time, and emergency response**.

Instead of relying on fixed traffic-light schedules, SynchroGrid experiments with increasingly intelligent control strategies and evaluates them under the same simulated traffic conditions. 🚗🚕🚑

---

## 🧠 What Does SynchroGrid Do?

SynchroGrid creates a grid-based city where vehicles:

* 🚗 Spawn with random origins and destinations
* 🗺️ Calculate routes through the road network
* 🚦 Interact with traffic signals
* ⏳ Accumulate waiting time when signals prevent movement
* 📍 Track travel distance and travel time
* 🚑 Include emergency vehicles with priority behavior
* 🏁 Complete trips when they reach their destinations

The traffic-control system then determines how intersections should operate based on the selected strategy.

---

## 🚦 Traffic-Control Strategies

SynchroGrid compares three approaches.

### 1. 🕐 Fixed Control

A traditional baseline where traffic signals operate using a fixed timing schedule.

This provides a reference point for evaluating more intelligent strategies.

### 2. 📊 Adaptive Control

Signal duration changes according to the amount of traffic waiting at an intersection.

More traffic creates greater pressure for additional green time.

### 3. 🧠 Pressure Control

The most advanced controller in the simulation.

It considers traffic pressure across competing directions and gives greater importance to heavily congested approaches and emergency traffic.

The objective is to dynamically distribute intersection capacity where it is needed most.

---

## 🗺️ Simulation Architecture

```text
                 ┌──────────────────┐
                 │   Traffic Demand │
                 └────────┬─────────┘
                          ↓
                 ┌──────────────────┐
                 │ Vehicle Generator│
                 └────────┬─────────┘
                          ↓
                 ┌──────────────────┐
                 │   Route Planner  │
                 └────────┬─────────┘
                          ↓
                 ┌──────────────────┐
                 │ Traffic Network  │
                 └────────┬─────────┘
                          ↓
                 ┌──────────────────┐
                 │ Traffic Control  │
                 └────────┬─────────┘
                          ↓
                 ┌──────────────────┐
                 │ Vehicle Movement │
                 └────────┬─────────┘
                          ↓
                 ┌──────────────────┐
                 │ Metrics & Results│
                 └──────────────────┘
```

---

## 📈 Metrics

Each simulation records several performance indicators:

| Metric                    | Description                                              |
| ------------------------- | -------------------------------------------------------- |
| 🚗 Completed Trips        | Number of vehicles reaching their destinations           |
| 📊 Completion Rate        | Percentage of spawned vehicles completing their trips    |
| ⏳ Average Wait            | Average time vehicles spend waiting                      |
| 🕐 Average Travel Time    | Average duration of completed trips                      |
| 📏 Average Distance       | Average route distance                                   |
| 🚧 Maximum Queue          | Maximum number of active vehicles                        |
| 🚑 Emergency Completion   | Number of emergency vehicles reaching their destinations |
| ⚡ Emergency Response Time | Average travel time for completed emergency vehicles     |

These metrics allow different control strategies to be compared objectively.

---

## 🧪 Benchmarking

SynchroGrid does not rely on a single simulation run.

The notebook performs a **multi-run benchmark** using different random seeds to reduce the influence of one particular traffic configuration.

Each strategy is evaluated repeatedly and summarized using:

```text
Mean ± Standard Deviation
```

This makes the comparison more meaningful than simply running the simulation once and declaring whichever number looks nicest the winner. Humanity has suffered enough from that methodology. 📉

---

## 📊 Visualizations

The notebook generates several visual analyses:

* 📊 Average waiting-time comparison
* 🚗 Trip-completion comparison
* 🚧 Maximum congestion comparison
* 📈 Traffic population over time
* 🏁 Cumulative throughput
* 🗺️ City-state visualization
* 🚦 Intersection signal states
* 🚑 Emergency vehicle behavior

---

## 🛠️ Technologies

* 🐍 **Python**
* 🔢 **NumPy**
* 📊 **Matplotlib**
* 🧮 **Breadth-First Search (BFS)**
* 🎲 **Procedural/randomized simulation**
* 🤖 **Multi-agent simulation concepts**
* 📈 **Statistical benchmarking**

---

## ▶️ Running the Project

### 1. Clone the repository

```bash
git clone https://github.com/your-username/SynchroGrid.git
cd SynchroGrid
```

### 2. Install dependencies

```bash
pip install numpy matplotlib
```

### 3. Launch the notebook

```bash
jupyter notebook SynchroGrid.ipynb
```

Then run the cells from top to bottom.

---

## 🔬 Experimental Design

SynchroGrid is structured around a controlled comparison:

```text
Same City
   +
Same Traffic Demand
   +
Same Random Seed
   ↓
┌──────────────┐
│ Fixed        │
├──────────────┤
│ Adaptive     │
├──────────────┤
│ Pressure     │
└──────────────┘
        ↓
Performance Comparison
```

This allows the effect of the **traffic-control strategy itself** to be studied rather than mixing different traffic scenarios together.

---

## 🚀 Future Improvements

SynchroGrid provides a foundation for more advanced experimentation.

Potential extensions include:

* 🧬 Genetic Algorithm-based signal optimization
* 🧠 Reinforcement Learning traffic controllers
* 🚑 Advanced emergency-vehicle preemption
* 🚧 Dynamic accidents and road closures
* 🌧️ Weather-dependent traffic behavior
* 🚗 Different vehicle classes
* 🛣️ More realistic road networks
* 📡 Communication between neighboring intersections
* 🔥 Real-time congestion propagation
* 📊 Larger-scale statistical experiments
* 🎮 Interactive simulation visualization

A particularly interesting next step would be training or optimizing a controller specifically to minimize a weighted objective such as:

```text
Traffic Cost =
    waiting time
  + congestion penalty
  + travel time
  + emergency response penalty
```

That would turn SynchroGrid from a simulation benchmark into a genuine **traffic-control optimization problem**.

---

## 🎯 Project Goal

The goal of SynchroGrid is not simply to move vehicles around a virtual map.

It is to investigate how **adaptive decision-making can improve the behavior of a complex multi-agent system**.

By comparing increasingly intelligent traffic-control strategies under controlled experimental conditions, the project provides a compact environment for exploring:

> **Simulation → Optimization → Evaluation → Intelligent Control**

---

## 📜 License

This project is intended for educational, experimental, and research purposes.
