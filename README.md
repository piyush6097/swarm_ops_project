<p align="center">
  <img src="https://img.shields.io/badge/Python-3.8+-3776AB?style=for-the-badge&logo=python&logoColor=white" />
  <img src="https://img.shields.io/badge/HTML5-Dashboard-E34F26?style=for-the-badge&logo=html5&logoColor=white" />
  <img src="https://img.shields.io/badge/Status-Active-00ff9d?style=for-the-badge" />
  <img src="https://img.shields.io/badge/License-MIT-blue?style=for-the-badge" />
</p>

<h1 align="center">🐝 SwarmOps — Multi-Agent E-Commerce Operations Intelligence</h1>

<p align="center">
  <strong>An autonomous multi-agent system that simulates real-time e-commerce operations — from inventory optimization and dynamic pricing to fraud detection and customer service — coordinated by an intelligent Supervisor agent.</strong>
</p>

---

## 📋 Table of Contents

- [Overview](#-overview)
- [Architecture](#-architecture)
- [Agents](#-agents)
- [Tech Stack](#-tech-stack)
- [Project Structure](#-project-structure)
- [Getting Started](#-getting-started)
- [Simulation Scenarios](#-simulation-scenarios)
- [Dashboard](#-dashboard)
- [Knowledge Graph (Data Layer)](#-knowledge-graph-data-layer)
- [How It Works](#-how-it-works)
- [Sample Output](#-sample-output)
- [Contributing](#-contributing)
- [License](#-license)
- [Author](#-author)

---

## 🔍 Overview

**SwarmOps** is a multi-agent simulation framework designed for Indian e-commerce operations. It demonstrates how autonomous AI agents can collaboratively manage complex business workflows in real-time:

- **📦 Inventory Optimization** — monitors warehouse stock across Mumbai, Delhi, and Bangalore; triggers critical reorders.
- **💰 Dynamic Pricing** — tracks competitor prices (Flipkart, Amazon, Meesho) and recommends price adjustments.
- **🎧 Customer Service** — handles escalations, sentiment analysis, and legal threat detection.
- **🔐 Fraud Detection** — scores transactions using velocity checks, address mismatches, and behavioral rules.
- **🧠 Supervisor Coordination** — routes inputs to the right agents, resolves conflicts, and tracks KPIs.

---

## 🏗️ Architecture

```
                    ┌──────────────────────────┐
                    │      INPUT STREAM        │
                    │  (Orders, Alerts, Queries)│
                    └────────────┬─────────────┘
                                 │
                    ┌────────────▼─────────────┐
                    │    🧠 SUPERVISOR AGENT    │
                    │   (Router + Coordinator)  │
                    └────────────┬─────────────┘
                                 │
            ┌────────────────────┼────────────────────┐
            │                    │                     │
   ┌────────▼────────┐ ┌────────▼────────┐  ┌────────▼────────┐
   │  📦 Inventory   │ │  💰 Pricing     │  │  🔐 Fraud       │
   │    Agent        │ │    Agent        │  │    Agent        │
   └────────┬────────┘ └────────┬────────┘  └────────┬────────┘
            │                    │                     │
            └────────────────────┼────────────────────┘
                                 │
                    ┌────────────▼─────────────┐
                    │   🎧 CUSTOMER AGENT      │
                    │  (Service + Escalation)   │
                    └────────────┬─────────────┘
                                 │
                    ┌────────────▼─────────────┐
                    │   CONFLICT RESOLUTION     │
                    │   + KPI AGGREGATION       │
                    └────────────┬─────────────┘
                                 │
                    ┌────────────▼─────────────┐
                    │   📊 DASHBOARD / LOG      │
                    └──────────────────────────┘
```

---

## 🤖 Agents

| Agent | Role | Capabilities |
|-------|------|-------------|
| **🧠 SupervisorAgent** | Router & Coordinator | Classifies inputs, routes to agents, resolves conflicts, tracks KPIs |
| **📦 InventoryAgent** | Stock Optimization | Multi-warehouse monitoring, critical reorder triggers, cost impact analysis |
| **💰 PricingAgent** | Dynamic Pricing | Competitor price tracking, automatic price-match recommendations |
| **🎧 CustomerAgent** | Customer Service | Sentiment analysis, legal threat detection, policy-based escalation |
| **🔐 FraudAgent** | Fraud Detection | Risk scoring, velocity checks, address mismatch detection |

---

## 🛠️ Tech Stack

| Component | Technology |
|-----------|-----------|
| **Backend / Simulation** | Python 3.8+ (Standard Library only — no external dependencies) |
| **Dashboard** | HTML5, CSS3 (Grid Layout), Vanilla JavaScript |
| **Data Storage** | CSV, JSON, TXT (flat-file knowledge graph) |
| **Visualization** | Real-time browser-based command center |

---

## 📁 Project Structure

```
swarm_ops_project/
│
├── swarm_ops.py                  # Core multi-agent simulation engine
├── dashboard.html                # Real-time command center UI
├── swarm_simulation_log.json     # Generated simulation output log
│
├── data/                         # Knowledge graph & mock databases
│   ├── mock_inventory.csv        # Multi-warehouse inventory data
│   ├── mock_pricing.csv          # Competitor pricing intelligence
│   ├── fraud_rules.json          # Fraud detection rule engine
│   └── customer_policy.txt       # Customer service policy document
│
├── .gitignore
├── LICENSE
└── README.md
```

---

## 🚀 Getting Started

### Prerequisites

- **Python 3.8+** (uses only standard library — no `pip install` needed!)
- Any modern web browser (for the dashboard)

### Run the Simulation

```bash
# Clone the repo
git clone https://github.com/piyush6097/swarm_ops_project.git
cd swarm_ops_project

# Run the multi-agent simulation
python swarm_ops.py
```

This will:
1. Load the knowledge graph (inventory, pricing, fraud rules, policies)
2. Process 5 test scenarios through the agent swarm
3. Generate `swarm_simulation_log.json` with detailed results

### Launch the Dashboard

```bash
# Option 1: Simply open in browser
start dashboard.html          # Windows
open dashboard.html           # macOS
xdg-open dashboard.html      # Linux

# Option 2: Use a local server (recommended)
python -m http.server 8000
# Then open http://localhost:8000/dashboard.html
```

---

## 🎯 Simulation Scenarios

The system processes **5 real-world e-commerce scenarios**:

| # | Scenario | Agents Triggered | Key Action |
|---|----------|-----------------|------------|
| 1 | Delhi warehouse stock drops to 15 units | InventoryAgent | `CRITICAL_REORDER` — ₹4,500 cost savings |
| 2 | Flipkart undercuts price by 12% | PricingAgent, FraudAgent | `PRICE_MATCH` — adjust to ₹879 |
| 3 | Customer threatens consumer forum complaint | CustomerAgent | `ESCALATE_TO_HUMAN` — legal threat detected |
| 4 | Suspicious order: new account, 3 addresses, same IP | FraudAgent | `Manual Review` — fraud score 65 |
| 5 | Flash sale with low stock + fraud alerts | InventoryAgent, PricingAgent, FraudAgent | Multi-agent coordination with conflict resolution |

---

## 📊 Dashboard

The **SwarmOps Command Center** is a dark-themed, real-time dashboard featuring:

- **Live Swarm Activity Feed** — animated log entries with color-coded alerts
- **Agent Status Panel** — shows all 5 active agents with health indicators
- **Real-Time KPI Cards** — inventory savings, fraud blocked, queries resolved
- **Universal Input Stream** — text input for custom scenario testing

> 💡 **Tip:** The dashboard auto-plays simulation results with a staggered animation to simulate live agent processing.

---

## 📚 Knowledge Graph (Data Layer)

The agents operate on a **flat-file knowledge graph**:

| File | Purpose | Format |
|------|---------|--------|
| `mock_inventory.csv` | Stock levels across 3 warehouses (Mumbai, Delhi, Bangalore) | CSV |
| `mock_pricing.csv` | Price comparison with Flipkart, Amazon, Meesho | CSV |
| `fraud_rules.json` | Risk scoring rules: velocity, address mismatch, COD abuse | JSON |
| `customer_policy.txt` | Business policies for returns, escalation, refunds | TXT |

---

## ⚙️ How It Works

```
1. INPUT CLASSIFICATION
   └─► Supervisor scans keywords to identify relevant agents
   
2. AGENT EXECUTION  
   └─► Each routed agent processes the input against its knowledge base
   
3. CONFLICT RESOLUTION
   └─► Supervisor applies priority rules:
       • Fraud BLOCKS everything (highest priority)
       • Critical inventory OVERRIDES pricing discounts
       
4. KPI AGGREGATION
   └─► Results are tallied: cost savings, fraud prevented, queries resolved
   
5. OUTPUT
   └─► Full log saved to JSON, dashboard renders animated results
```

---

## 📄 Sample Output

```json
{
  "input": "SKU-4521 stock in Delhi warehouse dropped to 15 units",
  "classification": ["InventoryAgent"],
  "agent_responses": [
    {
      "agent": "InventoryAgent",
      "action": "CRITICAL_REORDER",
      "details": {
        "sku": "SKU-4521",
        "warehouse": "Delhi",
        "current_level": 15,
        "reorder_recommended": "Yes",
        "cost_impact_inr": 4500,
        "status": "Critical"
      }
    }
  ],
  "kpi_snapshot": {
    "inventory_saved": 4500,
    "fraud_blocked": 0,
    "queries_resolved": 0
  }
}
```

---

## 🤝 Contributing

Contributions are welcome! Here's how:

1. **Fork** the repository
2. **Create** a feature branch (`git checkout -b feature/amazing-feature`)
3. **Commit** your changes (`git commit -m 'Add amazing feature'`)
4. **Push** to the branch (`git push origin feature/amazing-feature`)
5. **Open** a Pull Request

### Ideas for Contribution
- Add LLM-based natural language classification (replace keyword routing)
- Implement real-time WebSocket dashboard updates
- Add more agent types (Logistics, Marketing, Returns)
- Connect to real e-commerce APIs

---

## 📜 License

This project is licensed under the **MIT License** — see the [LICENSE](LICENSE) file for details.

---

## 👤 Author

**Piyush Kumar**  
GitHub: [@piyush6097](https://github.com/piyush6097)

---

<p align="center">
  <strong>⭐ If you found this project useful, please give it a star!</strong>
</p>
