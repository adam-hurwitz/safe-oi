---
title: 🔰 Safe multinetwork
tags: safe
description: Safe multinetwork
image: https://pbs.twimg.com/profile_banners/8467082/1674046807/1500x500
---

<h1 style="text-align: center;">Multinetwork</h1>

# Counterfactual accounts

- Accounts that have not been initialized onchain, i.e. There is no onchain activity
- Can still receive and store assets
- Used for externally owned accounts (EOAs) and smart contract accounts

# Externally owned accounts (EOAs) vs Smart contract accounts

*See [Account Abstraction in a Multichain Landscape - Part 1: Addresses](https://safe.mirror.xyz/4GcGAOFno-suTCjBewiYH4k4yXPDdIukC5woO5Bjc4w) by Safe*

## Externally owned accounts (EOAs)

- Compatible across many networks
- Each network uses the same account address
- Actions on each network are independent of each other
    - E.g. Sending or receiving an asset occurs only on the network it is initiated on

## Smart contract accounts

- Each account is associated to a specific network
- Actions on each network are independent of each other
    - E.g. Adding or removing an an approval account on a Safe account
- Downsides
    - Not possible to have the same address on non EVM networks
    - Assets can mistakenly be sent to the wrong network
    - Network bridging complexity
    - User management complexity
    - These issues arise when using counterfactual accounts to create accounts with the same address: Created using the Ethereum virtual machine (EVM) [counterfactual deployment (CREATE2)](https://docs.openzeppelin.com/cli/2.7/deploying-with-create2) opcode

# Account identification

- Network specific IDs
    - Safe accounts have a network specific ID prefixed to each address ([ERC-3770](https://eips.ethereum.org/EIPS/eip-3770))
    - Prevents assets or tokens to be sent to the wrong network
- Unified human readable account name 
    - ENS to link all associated network addresses
    - ENS supports [multichain address resolution](https://docs.ens.domains/ens-improvement-proposals/ensip-11-evmchain-address-resolution)

# Arbitrary message bridge (AMB)

## About

- *See [How can a Safe hold asset on multiple chains?](https://forum.safe.global/t/how-can-a-safe-hold-asset-on-multiple-chains/2242) by Martin Köppelmann on Safe forum*
- Network controls actions on any network that is connected via an Arbitrary message bridge (AMB)
- Bridge sends messages across 2 accounts on 2 different networks to each other
- Relies on bridge security which is a single point of failure

## Push vs Pull model

- *See [Vitalik Buterin's response](https://forum.safe.global/t/how-can-a-safe-hold-asset-on-multiple-chains/2242/13?u=adamhurwitz.eth) to [How can a Safe hold asset on multiple chains?](https://forum.safe.global/t/how-can-a-safe-hold-asset-on-multiple-chains/2242) on Safe forum*
- Push: The account on the "main" network pushes actions to other networks to sync
- Pull: The account on the "main" network does an action, and the other networks pull new actions from the "main" network
    - Transactions are faster
        - There is no asynchronous step required
        - It’s all one single synchronous transaction on chain 
    - Saves spending gas on the "main" network
    - Reduce complexity of paying for transaction fees on multiple networks

## Hashi

- *See [Safe on Hashi](https://www.gnosis.io/blog/safe-on-hashi) by Gnosis*
- Created by Gnosis as a [Safe module](https://hackmd.io/@safe/oi/https%3A%2F%2Fhackmd.io%2F%40safe%2Farchitecture#Pluginsmodules)
- Creates a main Safe that can control secondary Safes on other networks
- Built prototypes for both [push and pull strategies](#Push-vs-Pull-model)

## Deposit and withdrawal model

- *See [Hugo Montenegro's response](https://forum.safe.global/t/how-can-a-safe-hold-asset-on-multiple-chains/2242/19?u=adamhurwitz.eth) to [How can a Safe hold asset on multiple chains?](https://forum.safe.global/t/how-can-a-safe-hold-asset-on-multiple-chains/2242) on Safe forum*
- The account on the "main" network makes a deposit protected by a secret key
- An account on another network makes a withdrawal using the secret key
- E.g. Peanut Protocol
    - Site: [peanut.to](https://peanut.to)
    - [A new primitive to butter web3](https://peanutprotocol.notion.site/A-new-primitive-to-butter-web3-ac9260237d3f4075bf6e87a27912e65f)

# Keystore contract

## About

- *See [Deeper dive on cross-L2 reading for wallets and other use cases](https://vitalik.ca/general/2023/06/20/deeperdive.html) by Vitalik Buterin*
- The user has a main account on a layer 1 (L1) or layer 2 (L2) that manages all accounts
    - Verification key for accounts across all networks used, i.e. Action approval key
    - Rules for changing the key, e.g. Social recovery

## Strategies

### Light – Syncing a keystore account and network account approval keys

- There is a "main" account with a keystore state and a function to sync with other network account signing (approval) keys
- Other network accounts signing key
    - Cross-chain proof to check other network's current key
    - Update its own local current key
- When initializing on a new network the function will request the key from other networks
- Benefits
    - Secured onchain with account keys
    - Limited need for potentially expensive cross network proofs
- Downsides
    - Potentially expensive onchain account key change transactions
    - Lack of privacy because accounts can be linked publicly using the proof timestamps: [Deeper dive on cross-L2 reading for wallets and other use cases](https://vitalik.ca/general/2023/06/20/deeperdive.html) > [Preserving privacy](https://vitalik.ca/general/2023/06/20/deeperdive.html#preserving-privacy) *by Vitalik Buterin*

### Heavy – Verify every action

- Cross network proof for every onchain transaction to verify keystores
- Benefits
    - Less complexity due to not managing a keystore state
    - Updating keystores is inexpensive
- Downside
    - Currently expensive cross network proofs
    - Not easily compatible with ERC-4337: Does not support cross contract reading of mutable objects during validation

<p style="text-align: center; font-style: italic">This is not financial, technical, or legal advice. Consult professionals and do your own research.</p>

<style>
    .markdown-body h1 {
        font-weight: 700;
        font-size: 3.4rem;
    }
    .markdown-body {
        font-size: 1.8rem;
    }
    .markdown-body a:link {
        color: #3C8974
    }
    .markdown-body a:hover {
        color: #225347 
    }
    .markdown-body a:active {
        color: #225347
    }
</style>