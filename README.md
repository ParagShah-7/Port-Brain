
# 🚢 PortBrain – Reinforcement Learning for Dynamic Ship Handling  
### Deep Q-Learning (DQN) for Real-Time Port Optimization

PortBrain is a Reinforcement Learning (RL) simulation where an AI agent learns  
to manage a port by dynamically handling incoming ships.  
The goal is to minimise congestion, handle ships efficiently,  
and maximise total reward using a **DQN (Deep Q-Network)**.

---

## 📌 Features

- **Dynamic Environment**:  
  Ships arrive according to a Poisson process, and the agent must decide  
  how many ships to handle at each timestep.

- **Deep Q-Learning Agent**  
  Uses:
  - Experience Replay  
  - Target Network  
  - Epsilon-Greedy Exploration  
  - SmoothL1 Loss & Gradient Clipping  

- **Detailed Episode Logging**  
  Cinematic “ship logs” printed for selected episodes.

- **Visual Analytics**
  - Episode Rewards  
  - Ships Handled vs Remaining  
  - Epsilon Decay  
  - Average Q-Values  

- **Training History Exported to CSV**

---

## 🧠 How It Works

### **State Representation (3 values)**
1. Ships waiting  
2. Ships handled  
3. Current timestep  

### **Action Space**
Agent chooses how many ships to handle:  
`0, 1, 2, ..., MAX_HANDLE_PER_STEP`

### **Reward Function**
Reward =  

+2 × ships_handled
-1 × ships_waiting
-0.1 time penalty

Encourages efficiency and discourages congestion.

---

## 💻 Running the Code

Install dependencies:

```bash
pip install torch numpy pandas matplotlib tqdm
Run the training script:
python portbrain_dqn.py
```
    
Output includes:

Training progress bar

Cinematic episode summaries

---
Visual plots

A CSV: portbrain_training_history.csv

📊 Visualisations

The notebook generates 4 plots:

Total Reward Over Episodes

Ships Handled vs Remaining

Epsilon Decay Curve

Average Q-Value Trend

These help analyse learning quality and stability.

📁 Project Structure
PortBrain
│── portbrain_dqn.py
│── portbrain_training_history.csv
│── README.md
└── images/ (optional plot storage)

📌 Future Improvements
  - Double DQN
  - Dueling Networks
  - Prioritized Experience Replay
  - Streamlit Real-Time Dashboard
  - Multi-Agent Port Handling

👨‍💻 Authors

Group 8
Kapil Bhardwaj
Parag Shah

Course: Reinforcement Learning – CSCN8020
Project: PORTBRAIN
