# MODULE 10.0: WEB3 BASICS & BLOCKCHAIN DEVELOPMENT


#### 1. What Is Web3?

| Web Version | Description                                             |
| ----------- | ------------------------------------------------------- |
| Web1        | Read-only (static websites, 1990s–2000s)                |
| Web2        | Read-Write (interactive apps, user-generated content)   |
| **Web3**    | Read-Write-Own (decentralized, blockchain-powered apps) |

**Core Ideas of Web3:**

* Users **own their data**
* No central authority (decentralized)
* Smart contracts replace backend logic
* Use of **cryptographic identities** (wallets)

Technologies:

* **Blockchain** (Ethereum, ICP, etc.)
* **Smart Contracts**
* **Decentralized Storage**
* **Cryptographic Wallets**

---

#### 2. Blockchain Development Overview

* Blockchain is a **distributed, immutable ledger**
* Backend logic is executed using **smart contracts**
* Data is stored in blocks, linked using cryptography
* Each transaction is **verified** and **recorded permanently**

**Popular Chains for Devs:**

* Ethereum (Solidity)
* Solana (Rust)
* Internet Computer (Motoko, Rust)

---

#### 3. What Is a Canister?

* **Canister = Smart Contract + Compute Unit** on the Internet Computer Protocol (ICP)
* It includes:

  * Code (e.g. written in Motoko or Rust)
  * State (persistent memory)
  * APIs (functions exposed to users or other canisters)

Think of a **canister** as a **decentralized microservice**.

**Key Features:**

* Runs independently on the blockchain
* Stores data securely
* Can talk to other canisters or external services

---

#### 4. What Is a Motoko Actor?

* **Motoko** is a language designed by DFINITY for developing on ICP
* An **Actor** is the fundamental programming unit in Motoko

**An Actor:**

* Encapsulates data and logic
* Exposes functions to the outside world
* Maintains private, secure state

**Example (Motoko syntax):**

```motoko
actor Counter {
  var count = 0;

  public func increment() : async Int {
    count += 1;
    return count;
  }

  public func get() : async Int {
    return count;
  }
};
```

This defines:

* A **smart contract (actor)** called `Counter`
* Internal state (`count`)
* Public functions (`increment` and `get`) for interacting with it

Actors are:

* **Isolated** (don’t share memory)
* **Asynchronous** (everything is `async`)
* **Secure by default**

---

### Summary

| Concept        | Description                                     |
| -------------- | ----------------------------------------------- |
| Web3           | Decentralized internet (blockchain-based)       |
| Blockchain     | Distributed ledger with secure, verifiable data |
| Canister (ICP) | Compute unit + contract on Internet Computer    |
| Motoko Actor   | A secure, async smart contract unit in Motoko   |

<footer>TO BE CONT...</footer>
