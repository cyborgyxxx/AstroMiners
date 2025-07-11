# 🚀 AstroMiners Smart Contract

**AstroMiners** is a Clarity-based smart contract simulating space mining operations using upgradable NFT mining rigs. Operators deploy, upgrade, and trade rigs based on fluctuating commodity prices, operational efficiency, and mining activity.

---

## 📦 Features

* **NFT Mining Rigs**: Each rig is minted as a unique non-fungible token (`astro-rig`).
* **Dynamic Upgrades**: Rigs can be upgraded based on commodity prices, rig age, and efficiency.
* **Operator Analytics**: Tracks mining expertise and operation history per user.
* **Shipyard Marketplace**: List and purchase rigs via a decentralized marketplace.
* **Efficiency System**: Active operation increases rig efficiency and operator reputation.
* **Admin Controls**: Manage commodity prices and shipyard fees.

---

## 📐 Data Structures

### 🛠 `rig-metadata`

Tracks rig-specific details:

* `model`: Rig model name.
* `description`: Details about the rig.
* `image-uri`: Asset image URL.
* `upgrade-tier`: Current upgrade level.
* `deployed-block`: Deployment block height.
* `last-operated`: Last activity timestamp.
* `efficiency-score`: Performance metric.

### ⚙️ `operator-stats`

Tracks miner/operator activity:

* `total-rigs`: Number of owned rigs.
* `total-operations`: Number of operations performed.
* `last-activity`: Last block activity occurred.
* `mining-expertise`: Aggregate mining performance.

---

## 🔧 Public Functions

### 🛠 Deployment & Operation

* `deploy-rig(model, description, image-uri)`: Mint a new rig NFT.
* `operate-rig(rig-id)`: Increase a rig’s efficiency score.

### ⛏ Upgrade System

* `upgrade-rig(rig-id)`: Update rig tier based on calculated conditions.
* `calculate-upgrade-tier(rig-id)`: Read-only tier prediction.

### 🧑‍🚀 Ownership & Transfers

* `transfer-rig(rig-id, recipient)`: Transfer ownership to another operator.
* `get-rig-owner(rig-id)`: Get current rig owner.

### 🏪 Shipyard Marketplace

* `list-in-shipyard(rig-id, price)`: List rig for sale.
* `remove-from-shipyard(rig-id)`: Unlist a rig.
* `purchase-rig(rig-id)`: Buy a listed rig.

### 💼 Admin Functions

* `update-commodity-price(new-price)`: Set market price for resource.
* `set-shipyard-fee(new-fee)`: Update trading fee (max 10%).

---

## 📊 Read-Only Functions

* `get-rig-metadata(rig-id)`
* `get-operator-stats(operator)`
* `get-shipyard-listing(rig-id)`
* `get-shipyard-fee()`

---

## 🔐 Error Codes

| Code | Meaning              |
| ---- | -------------------- |
| 100  | Not authorized       |
| 101  | Item not found       |
| 102  | Already exists       |
| 103  | Insufficient balance |
| 104  | Invalid price        |
| 105  | Transfer failed      |

---

## 🧪 Example Interaction

```clojure
;; Deploy a rig
(deploy-rig "X-9 HyperMiner" "Top-tier rig for asteroid mining" "https://image.link/x9.png")

;; Operate the rig
(operate-rig u1)

;; List the rig
(list-in-shipyard u1 u1000000)

;; Purchase the rig
(purchase-rig u1)
```

---

## 🔒 Access Control

Only the contract owner (`MINING-CHIEF`) can:

* Update commodity prices.
* Adjust shipyard fee.

All other actions require ownership of the NFT.

---

Let me know if you’d like a diagram or test suite added as well.
