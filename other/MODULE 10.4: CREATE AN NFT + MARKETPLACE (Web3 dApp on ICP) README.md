# MODULE 10.4: CREATE AN NFT + MARKETPLACE (Web3 dApp on ICP)


#### 1. What Is an NFT?

* **NFT = Non-Fungible Token**
* Unique, indivisible digital asset stored on a blockchain
* ERC-721 = Ethereum's NFT standard (1 token ≠ 1 token)
* Commonly used for:

  * Digital art (.jpeg, .png)
  * Music, videos, files
  * Virtual land, in-game items

---

#### 2. NFT Canister: ERC-721 Model in Motoko

**Essential Functions:**

* `mint(recipient: Principal, asset: Blob)`
* `transfer(from: Principal, to: Principal, tokenId: Nat)`
* `ownerOf(tokenId: Nat): Principal`
* `getAsset(tokenId: Nat): Blob`

**Motoko NFT Snippet:**

```motoko
actor class NFT() {
  stable var tokenOwners : [Principal] = [];
  stable var assets : [Blob] = [];

  public func mint(to: Principal, asset: Blob) : async Nat {
    let id = assets.size();
    assets := assets # [asset];
    tokenOwners := tokenOwners # [to];
    return id;
  };

  public func transfer(from: Principal, to: Principal, tokenId: Nat) : async Bool {
    if (tokenOwners[tokenId] != from) return false;
    tokenOwners[tokenId] := to;
    return true;
  };

  public func ownerOf(tokenId: Nat) : async Principal {
    return tokenOwners[tokenId];
  };

  public func getAsset(tokenId: Nat) : async Blob {
    return assets[tokenId];
  };
}
```

* **`Blob`** stores the `.jpeg` or image file in binary format
* Token ID (`Nat`) uniquely identifies each NFT

---

#### 3. Build the NFT Marketplace Frontend (Like OpenSea)

**Use:**

* **React** + **Plug Wallet**
* ICP canister backend

**Features:**

* Show all minted NFTs
* Allow users to:

  * **Connect wallet**
  * **Mint new NFT** (upload image)
  * **Buy NFT** (transfer token ownership)
  * **View ownership history**

**Connect React with Canister:**

```js
import { Actor, HttpAgent } from '@dfinity/agent';
import { idlFactory, canisterId } from '../../declarations/nft_backend';

const agent = new HttpAgent();
const nftActor = Actor.createActor(idlFactory, { agent, canisterId });

// Mint example
const imageBlob = await fetch('my-art.jpeg').then(res => res.blob());
const tokenId = await nftActor.mint(currentUserPrincipal, imageBlob);
```

---

#### 4. Buy and Sell NFTs (Transfer Ownership)

* The **current owner** can call the `transfer()` function
* Marketplace logic controls:

  * Listing NFT for sale
  * Setting price
  * Handling token transfer on purchase

**Optional:**
Use ICP’s native **ICP token or custom fungible token** for payment

---

#### 5. Ownership Logic

* Ownership tracked via `tokenOwners[tokenId]`
* Must validate:

  * `msg.caller == ownerOf(tokenId)` before allowing transfer
* Can also implement access control (only owner can update metadata)

---

### Summary

| Component              | Role                                                 |
| ---------------------- | ---------------------------------------------------- |
| NFT Standard           | ERC-721 → Unique, non-fungible Motoko canister       |
| Canister Functions     | `mint`, `transfer`, `ownerOf`, `getAsset`            |
| React Frontend         | Marketplace: display, mint, buy, connect Plug wallet |
| Storage                | `Blob` image → stored in on-chain state              |
| Ownership Verification | Based on `Principal` → `tokenOwners[tokenId]`        |

---

### Full-Stack Workflow (End-to-End)

1. User connects Plug wallet
2. Uploads .jpeg to mint NFT → stores Blob in canister
3. NFT listed on marketplace frontend
4. Buyer initiates transfer → ownership changes in smart contract
5. Owner can view, download, resell NFT via UI

---

Congratulations — this concludes the **entire Angela Yu Full-Stack + Web3 Developer Course revision**.

<footer>THE END</footer> 
