---
title: 🔰 Safe architecture
tags: safe
description: Safe account architecture
image: https://pbs.twimg.com/profile_banners/8467082/1674046807/1500x500
---

# Architecture

# Resources

- [Safe Modular Smart Account Architecture – Explained](https://safe.mirror.xyz/t76RZPgEKdRmWNIbEzi75onWPeZrBrwbLRejuj-iPpQ) by Safe 2023-07-10
- [Safe documentation > 🔰 Learn](https://docs.safe.global/learn)

# Foundation

## Singleton contract

- Contains the Safe business logic functions
- Functions modify the Safe proxy contract state data
- Not upgradeable (Immutable): Requires a new contract deployment for each version upgrade
    - Users can decide whether to upgrade through the Safe native app
- Deployed on each network where Safe is available

## Proxy contract

- Forwards requests to the Singleton contract
- Contains the Safe state data, e.g., Owners, threshold, plugin addresses, and hook addresses
- Upgradeable (Mutable)

## Safe SDK/API

- 3rd party apps can make requests to the Safe Singleton using the SDK/API.
- 3rd party apps act as wrappers to Safe accounts.
- E.g. Create new Safe accounts (Proxy instances), read and display Safe info

## Factory contracts

- Used to deploy Singleton and Proxy contracts

# Interfaces

## Plugins/modules

- Apps that connect onchain contracts and web APIs
    - Connect to web APIs through oracle systems
- Sample use cases: Recovery mechanisms, session keys, and payment streaming
- Enabled through a Safe account approval
    - The transaction is implemented through the Singleton
    - The Singleton updates the proxy contract with the plugin address

## Hooks/guards contract

- Smart contracts that verify and enforce onchain conditions before and after transactions occur
- Similar to event listeners

## Function handlers/fallback handlers contract

- Default functions when a function is called within the Safe Proxy that does not exist
- Forwards the call to an external contract
- Usually these functions are nested within other contracts as an error handler

## Signature verifiers

- Validates transactions for the Safe account
- Compatibility with externally owned accounts (EOAs) which have a private key to sign transactions, e.g. [EIP-1271](https://eips.ethereum.org/EIPS/eip-1271)

# ERC-4337

## About

- Site: [eips.ethereum.org/EIPS/eip-4337](https://eips.ethereum.org/EIPS/eip-4337)
- Creates a standard for smart accounts to customize verification
- Uses a new transaction object and separate mempool

## Resources

- [Safe wallet adds 'ERC-4337' to boost account abstraction features](https://www.theblock.co/post/239386/safe-wallet-erc-4337-account-abstraction) *by The Block*
- [Ethereum’s ERC-4337 Standard: Explained](https://www.ledger.com/academy/ethereum-erc-4337-standard-explained) *by Ledger*


# Safe protocol

## About

- Whitepaper: [Safe{Core} Protocol
](https://docs.google.com/document/d/1y6jRyU6ty0VS0HbiiJrYXRJy5QFPZyH5Ymn2BftgtsU/edit#heading=h.1xlete5fb6vd)
- FAQ: [Safe{Core} Protocol FAQ](https://safe-global.notion.site/Safe-Core-Protocol-FAQ-19cfbf4aee934bb0b439ec602d7bd43f)
- Forum: [Safe{Core} Protocol Whitepaper](https://forum.safe.global/t/safe-core-protocol-whitepaper/3949)
- Github: [Safe{Core} Protocol Specification](https://github.com/safe-global/safe-core-protocol-specs)

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