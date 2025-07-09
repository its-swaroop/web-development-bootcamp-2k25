# MODULE 10.1: DEPLOY YOUR CV WEBSITE TO A BLOCKCHAIN (ICP)



#### 1. What Are Cycles?

* **Cycles** are the **fuel** for computation on the Internet Computer
* Every canister needs cycles to:

  * Deploy
  * Store state
  * Handle requests

**Think of it like:**
Cycles = Gas for Ethereum, but for ICP

---

#### 2. Set Up a Cycles Wallet

To deploy a canister (like your CV website), you need a **wallet**:

**Steps:**

1. Install the **DFX SDK** (DFINITY CLI tool):

   ```bash
   sh -ci "$(curl -fsSL https://internetcomputer.org/install.sh)"
   ```

2. Create a new identity:

   ```bash
   dfx identity new my-wallet
   ```

3. Create a wallet canister (if not already):

   ```bash
   dfx identity use my-wallet
   dfx wallet --network ic create
   ```

---

#### 3. Obtain Free Cycles from DFINITY (Cycles Faucet)

* Go to the **DFINITY Cycles Faucet**:
  [https://faucet.dfinity.org](https://faucet.dfinity.org)
* Login with **Internet Identity**
* Enter your wallet **canister ID**
* Receive testnet cycles (used for dev purposes only)

---

#### 4. Deploy Static CV Website to the Internet Computer

**Step-by-step:**

1. **Create your project:**

   ```bash
   dfx new cv_site
   cd cv_site
   ```

2. Replace contents of `frontend/index.html` with your **CV HTML file**

3. **Configure `dfx.json`:**
   Make sure `frontend` is set as the main entry:

   ```json
   "frontend": {
     "source": ["src/cv_site_assets"],
     "type": "assets"
   }
   ```

4. **Build & Deploy:**

   ```bash
   dfx deploy --network ic
   ```

   This:

   * Builds the site
   * Deploys the static content as a canister
   * Returns a **canister ID** + live URL (served from ICP)

---

#### 5. Manage Cycles Balance of a Canister

Check balance:

```bash
dfx wallet --network ic balance
```

Top up canister:

```bash
dfx wallet --network ic send <canister-id> <amount-in-cycles>
```

---

#### 6. Check How Many Cycles Were Used

Monitor cycles for a canister:

```bash
dfx canister --network ic status <canister-id>
```

Check fields like:

* **Memory size**
* **Cycle balance**
* **Module hash** (hash of your deployed code)

---

### Summary

| Task                      | Tool / Command                      |
| ------------------------- | ----------------------------------- |
| Set up wallet             | `dfx identity`, `dfx wallet create` |
| Get free cycles           | `https://faucet.dfinity.org`        |
| Build & deploy CV website | `dfx deploy --network ic`           |
| Manage cycles             | `dfx wallet balance`, `wallet send` |
| Check usage               | `dfx canister status <id>`          |

<footer>TO BE CONT...</footer>
