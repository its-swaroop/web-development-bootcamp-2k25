# MODULE 10.3: CREATE YOUR OWN CRYPTO TOKEN — Web3 Tokenization on ICP



#### 1. Understanding Tokens in dApps & Web3

**Tokens = Digital Assets**

Used in:

* Decentralized Finance (DeFi)
* Governance (DAOs)
* Micropayments (content rewards, tipping)
* Access Control (NFTs, memberships)

**Types:**

* Fungible (e.g., ERC-20: interchangeable, like coins)
* Non-Fungible (e.g., ERC-721: unique items like NFTs)

You’ll be building a **fungible token (ERC-20 equivalent)** on ICP using **Motoko**.

---

#### 2. Token Contract — ERC-20 Equivalent in Motoko

Basic functions include:

* `name`, `symbol`, `totalSupply`
* `balanceOf(principal)`
* `transfer(from, to, amount)`

**Motoko Example (simplified):**

```motoko
actor Token {
  stable var ledger : Trie.Trie<Principal, Nat> = Trie.empty();

  public func balanceOf(p: Principal) : async Nat {
    switch (Trie.get(ledger, p)) {
      case null { return 0 };
      case (?bal) { return bal };
    }
  };

  public func transfer(to: Principal, amount: Nat) : async Bool {
    let from = Principal.fromActor(this); // or use caller
    let senderBal = await balanceOf(from);

    if (senderBal < amount) return false;

    ledger := Trie.put(ledger, from, senderBal - amount);
    ledger := Trie.put(ledger, to, (await balanceOf(to)) + amount);
    return true;
  };
}
```

---

#### 3. Faucet Contract

Allows new users to **get a small amount of tokens** for free.

**Motoko Example:**

```motoko
actor Faucet {
  let tokenCanister : Principal = ...;

  public func dispense() : async Text {
    let user = Principal.fromActor(this); // or `msg.caller`
    // Call tokenCanister.transfer() to user
    return "Tokens sent!";
  }
}
```

Faucet is used to onboard users and test token interactions.

---

#### 4. Working with Principal IDs

| What                        | Meaning                                   |
| --------------------------- | ----------------------------------------- |
| `Principal`                 | Unique ID representing a user or canister |
| `msg.caller`                | Authenticated caller of the function      |
| `Principal.fromActor(this)` | Principal of the canister itself          |

Used for:

* Identifying users
* Managing balances
* Controlling access (admin-only functions)

---

#### 5. Use the Plug Wallet

**Plug Wallet** = Browser extension for Internet Identity

**Purpose:**

* Hold ICP tokens and custom tokens
* Interact with canisters via UI
* Display token balances

**Steps:**

1. Install Plug Wallet (Chrome extension)
2. Create Internet Identity
3. Connect to your deployed token canister
4. Use token’s canister interface to check `balanceOf` and call `transfer`

---

#### 6. Token Transfers Between Accounts

**Transfer Logic:**

* User initiates transfer (via frontend or Plug)
* Call `transfer(to, amount)` on the canister
* Update balances accordingly

**Security:** Always validate:

* Sufficient balance
* Valid recipient principal
* Avoid overflow using `Nat` checks

---

### Summary

| Feature                | Tool / Code                                     |
| ---------------------- | ----------------------------------------------- |
| Token Logic (ERC-20)   | Motoko actor with `balanceOf`, `transfer`       |
| Faucet for Free Tokens | Separate actor calling token contract           |
| Identity System        | `Principal`, `msg.caller`                       |
| Wallet UI              | Plug Wallet for Web3 users                      |
| Token Transfer         | Contract → transfer() method between principals |

<footer>TO BE CONT...</footer>
