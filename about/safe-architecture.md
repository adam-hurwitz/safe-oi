---
title: 🔰 Architecture
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