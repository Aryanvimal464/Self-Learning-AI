              ┌──────────────────────┐
              │      User / UI        │
              │  Maze + Controls      │
              └──────────┬───────────┘
                         │
                         ▼
              ┌──────────────────────┐
              │    Maze Environment   │
              │  10 × 10 Grid        │
              │  Wall / Pit / Start  │
              │       / Goal         │
              └──────────┬───────────┘
                         │
                         ▼
              ┌──────────────────────┐
              │    RL Agent          │
              │  Q-Learning Engine   │
              └──────────┬───────────┘
                         │
              ┌──────────┴──────────┐
              ▼                     ▼
       ┌──────────────┐      ┌──────────────┐
       │ Exploration  │      │ Exploitation │
       │ Random Move  │      │ Best Q Move  │
       └──────┬───────┘      └──────┬───────┘
              └──────────┬──────────┘
                         ▼
              ┌──────────────────────┐
              │   Reward System      │
              │ Goal     → +1        │
              │ Pit      → -1        │
              │ Step     → -0.02     │
              │ Wall     → -0.05     │
              └──────────┬───────────┘
                         ▼
              ┌──────────────────────┐
              │     Q-Table          │
              │ State × 4 Actions    │
              │ Up / Right / Down /  │
              │ Left                 │
              └──────────┬───────────┘
                         │
                         ▼
              ┌──────────────────────┐
              │ Updated Knowledge    │
              │ Better route learned │
              └──────────────────────┘
              # 🧠 Seekhu — Self-Learning Maze Agent

Seekhu is an interactive **Reinforcement Learning (RL) based self-learning maze agent** that learns how to reach a goal by exploring a maze and learning from rewards and penalties.

The agent starts with **no predefined route and no map-based solution**. Instead, it learns through repeated interaction with the maze environment. Every movement produces feedback in the form of rewards or penalties, and the agent uses this experience to improve its future decisions.

The project demonstrates the core concept of **Q-Learning**, where an agent gradually learns which actions are more useful for reaching a desired goal.

---

## 🚀 Project Overview

Seekhu provides a visual and interactive way to understand how a reinforcement learning agent learns.

The maze is represented as a **10 × 10 grid**, and the agent can move in four directions:

- ⬆️ Up
- ➡️ Right
- ⬇️ Down
- ⬅️ Left

Initially, the agent explores the maze mostly through random actions. As training continues, it learns from the rewards and penalties received from previous actions.

Over time, the agent starts identifying useful paths and avoiding actions that lead to walls, pits, or unnecessary movement.

The learning process is displayed visually through:

- Agent movement
- Learned useful cells
- Avoided cells
- Reward progress
- Episode statistics
- Learned route visualization

---

## 🎯 Main Objective

The main objective of Seekhu is to demonstrate how an AI agent can learn a decision-making strategy **without being explicitly programmed with the correct path**.

Instead of telling the agent:

> "Move from Start to Goal using this exact route."

the system allows the agent to discover a good route through:

1. Exploration
2. Trial and error
3. Rewards
4. Penalties
5. Q-value updates
6. Repeated training

This makes the project a practical demonstration of **Reinforcement Learning and Q-Learning**.

---

## 🧩 How the Agent Learns

Seekhu uses the **Q-Learning algorithm**.

The agent maintains a Q-table containing a value for each possible:

**State + Action**

The maze contains:

- 100 possible cells
- 4 possible actions per cell

Therefore, the Q-table contains:

**100 × 4 = 400 Q-values**

Each Q-value represents how useful an action is expected to be from a particular cell.

For example:

```text
Current State: Cell 42

Actions:
Up       → Q-value
Right    → Q-value
Down     → Q-value
Left     → Q-value
