# 🏭 Warehouse Robot Autonomy (Reinforcement Learning)

## Overview

This project simulates an autonomous warehouse robot that learns to efficiently navigate a grid-based environment, pick up an item, and deliver it to a designated drop-off location. The system is designed to model core challenges in warehouse automation, including path planning, obstacle avoidance, and task completion under constraints.

Using reinforcement learning, the robot learns optimal policies through interaction with the environment, improving its efficiency over time.

---

## Problem Setting

A robot operates in a **6×6 warehouse grid** containing static obstacles (shelves). Its objective is to:

1. Navigate to a fixed pickup location
2. Pick up the item
3. Deliver it to a fixed drop-off location

The agent must learn to complete this task while minimizing penalties and avoiding collisions.

---

## Environment Details

### Grid Configuration

* **Grid size:** 6 × 6
* **Obstacles:** Static shelves that block movement
* **Start state:** Random agent position
* **Pickup & Drop-off:** Fixed locations

### Action Space

* Move: `Up`, `Down`, `Left`, `Right`
* Task actions: `Pick-up`, `Drop-off`

### Reward Structure

* ✅ +100 → Successful delivery
* 📦 +25 → First successful pickup
* ⏱️ -1 → Per step (encourages efficiency)
* 🚧 -20 → Collision with obstacle

### Terminal State

* Episode ends when the item is successfully delivered.

---

## State Representation

Each state is defined as:

(agent_position, carrying_status)

* `agent_position`: (x, y) coordinates on the grid
* `carrying_status`: Boolean indicating whether the robot is holding the item

Total state space size:
2 × (grid cells) = 2 × 36 = 72 states

---

## Reinforcement Learning Approach

This project implements:

* **Q-Learning**
* **SARSA (State-Action-Reward-State-Action)**

Both methods use a tabular approach to learn optimal policies for:

* Efficient navigation
* Task sequencing (pickup → delivery)
* Avoiding penalties

---

## Key Features

* Custom-built warehouse environment (Gymnasium-style)
* Tabular RL implementation (Q-table)
* Deterministic & Stochastic environment dynamics
* Collision handling with obstacles
* Reward shaping for efficiency optimization

---

## Results

* Achieved improved episodic rewards (~10% increase during training for both Deterministic and Stochastic environments).
* Learned stable policies for consistent task completion
* Demonstrated effective navigation and decision-making under constraints

---

## Limitations

* Fixed pickup and drop-off locations
* Single-task episodes (no multi-delivery sequences)

---

## Future Improvements

* Introduce **randomized pickup and drop-off locations**
* Support **multiple deliveries per episode**
* Simulate **multi-agent environments** (multiple robots)
* Extend to **function approximation (Deep RL)**


## Why This Project Matters

This project reflects real-world challenges in:

* Warehouse automation
* Robotics task planning
* Autonomous decision-making systems

It demonstrates how reinforcement learning can be applied to optimize sequential decision-making in constrained environments.

---
