# Group-18 Distributed Payment Processing System

**Fault-Tolerant Distributed Payment Processing System**  
Distributed Systems Group Assignment

---

## 👥 Team Members

| Role | Member Name | Registration # | Email |
|------|-------------|-----------------|-------|
| **Member 1: Fault Tolerance** | G.K.D.K Wickramasinghe | IT24101516 | - |
| **Member 2: Data Replication & Consistency** | Wijesinghe K | IT24102587 | - |
| **Member 3: Time Synchronization** | M.D.C Yavindi | IT24101636 | - |
| **Member 4: Consensus & Agreement** | K.T.L Perera | IT24610793 | - |

---

## 📋 Project Overview

This project implements a **Fault-Tolerant Distributed Payment Processing System** for an e-commerce platform. The system supports concurrent payment transactions with consistency guarantees even in the presence of node failures or network delays.

### Key Features
- ✅ Multiple concurrent payment clients
- ✅ Redundant payment server nodes
- ✅ Failure detection and automatic failover
- ✅ Distributed ledger with replication
- ✅ Time synchronization across nodes
- ✅ Consensus-based agreement mechanisms
- ✅ Historical transaction access from any node

---

## 🎯 Tasks & Responsibilities

### 1️⃣ Fault Tolerance (Member 1: G.K.D.K Wickramasinghe)

**Objective:** Ensure the system continues functioning even in case of failures.

**Tasks:**
- Implement redundancy mechanisms across multiple servers
- Design a failure detection system to identify unavailable payment server nodes
- Develop automatic failover mechanism to redirect payments on server failures
- Propose recovery mechanism for nodes that rejoin the system
- Evaluate impact of redundancy on system performance and storage overhead

**Deliverables:**
- Failure detection module
- Failover mechanism implementation
- Performance analysis report

---

### 2️⃣ Data Replication & Consistency (Member 2: Wijesinghe K)

**Objective:** Ensure payment ledger is replicated across multiple nodes while maintaining consistency and availability.

**Tasks:**
- Design replication strategy (quorum-based, primary-backup, or sharding)
- Choose consistency model (strong consistency, eventual consistency) with justification
- Implement deduplication mechanism to handle retries/failovers
- Optimize payment performance while ensuring consistency
- Analyze replication impact on latency and storage

**Deliverables:**
- Replication strategy implementation
- Deduplication mechanism
- Performance benchmarks

---

### 3️⃣ Time Synchronization (Member 3: M.D.C Yavindi)

**Objective:** Ensure payment timestamps are accurate for event correlation and debugging.

**Tasks:**
- Implement time synchronization protocol (NTP, PTP) across logging nodes
- Analyze clock skew impact on log ordering and consistency
- Develop mechanism to reorder out-of-sequence logs due to network delays
- Implement log timestamp correction techniques
- Evaluate synchronization accuracy vs. system overhead trade-offs

**Deliverables:**
- Time synchronization module
- Clock skew analysis
- Log reordering mechanism

---

### 4️⃣ Consensus & Agreement (Member 4: K.T.L Perera)

**Objective:** Ensure distributed payment servers agree on log storage, indexing, and retrieval policies.

**Tasks:**
- Research and implement consensus algorithm (Raft or Paxos)
- Design leader election mechanism for payment coordination
- Evaluate consensus performance under high payment processing rates
- Propose optimizations to reduce consensus overhead
- Test system under different failure scenarios

**Deliverables:**
- Consensus algorithm implementation
- Leader election mechanism
- Performance evaluation under stress

---

## 📁 Project Structure

```
Group-18-distributed-payment-system/
├── cmd/
│   ├── server/
│   │   └── main.go              # Payment server entry point
│   └── client/
│       └── main.go              # Payment client entry point
├── internal/
│   ├── fault_tolerance/         # Member 1: Failure detection & failover
│   ├── replication/             # Member 2: Data replication & consistency
│   ├── time_sync/               # Member 3: Time synchronization
│   └── consensus/               # Member 4: Consensus algorithms
├── pkg/
│   ├── models/                  # Data structures (Payment, Ledger, etc.)
│   ├── utils/                   # Utility functions
│   └── network/                 # Network communication
├── configs/
│   └── config.yaml              # System configuration
├── docs/
│   ├── DESIGN.md                # Architecture design document
│   ├── SETUP.md                 # Setup and installation guide
│   └── API.md                   # API documentation
├── go.mod                        # Go module definition
└── README.md                     # This file
```

---

## 🚀 Getting Started

### Prerequisites
- **Go 1.22+** installed on your system
- **Git** for version control
- Basic understanding of distributed systems

### Installation

1. **Clone the repository:**
   ```bash
   git clone https://github.com/Kunchana-Wijesinghe/Group-18-distributed-payment-system.git
   cd Group-18-distributed-payment-system
   ```

2. **Download dependencies:**
   ```bash
   go mod tidy
   ```

3. **Build the project:**
   ```bash
   go build -o bin/server ./cmd/server/main.go
   go build -o bin/client ./cmd/client/main.go
   ```

---

## 💻 Running the System

### Start Payment Server (Node 1)
```bash
go run cmd/server/main.go --port 8001 --node-id 1
```

### Start Payment Server (Node 2)
```bash
go run cmd/server/main.go --port 8002 --node-id 2
```

### Start Payment Server (Node 3)
```bash
go run cmd/server/main.go --port 8003 --node-id 3
```

### Start Payment Client
```bash
go run cmd/client/main.go --server-list localhost:8001,localhost:8002,localhost:8003
```

---

## 📊 Evaluation Criteria

| Criteria | Weight | Description |
|----------|--------|-------------|
| **Fault Tolerance** | 20% | Effectiveness of failure detection, redundancy, and recovery mechanisms |
| **Data Replication** | 20% | Efficiency of replication, consistency guarantees, and retrieval speed |
| **Time Synchronization** | 20% | Accuracy of timestamps and resolution of out-of-order events |
| **Consensus & Agreement** | 20% | Reliability and efficiency of consensus algorithm |
| **Overall Integration** | 20% | Seamless operation of all components and system scalability |

---

## 📦 Deliverables

1. **Report (10-12 pages)**
   - Design choices and justifications
   - Log replication strategies
   - System optimizations and trade-offs

2. **Implementation**
   - Working prototype in Go
   - All components integrated
   - Tested under various failure scenarios

3. **Presentation**
   - 15-minute presentation slides
   - Architecture diagrams
   - Implementation walkthrough

4. **GitHub Repository**
   - Complete source code
   - Maintained commit history from project start
   - Meaningful commit messages for each feature

5. **Video Presentation**
   - YouTube link to demonstration
   - Architecture explanation
   - System testing under failures

---

## 📝 Git Commit Guidelines

**Important:** Commit history is evaluated, so follow these guidelines:

✅ **Good Commits:**
```
Add failure detection mechanism for node health monitoring
Implement primary-backup replication strategy
Add NTP synchronization module
Implement Raft consensus algorithm
```

❌ **Bad Commits:**
```
final code
update
bug fix
```

**Commit frequently with meaningful messages!**

---

## 🔗 Important Resources

- **Go Documentation:** https://golang.org/doc/
- **Raft Consensus:** https://raft.github.io/
- **NTP Protocol:** https://en.wikipedia.org/wiki/Network_Time_Protocol
- **Distributed Systems:** https://en.wikipedia.org/wiki/Distributed_computing

---

## 📞 Contact

For questions or issues, contact any team member:

- G.K.D.K Wickramasinghe (Fault Tolerance)
- Wijesinghe K (Data Replication)
- M.D.C Yavindi (Time Synchronization)
- K.T.L Perera (Consensus & Agreement)

---

**Last Updated:** March 4, 2026
