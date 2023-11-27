---
title: 🔰 Decentralizing Safe
tags: safe
description: Safe decentralizing service
image: https://pbs.twimg.com/profile_banners/8467082/1674046807/1500x500
---

<h1 style="text-align: center;">Decentralizing Safe</h1>

# Safe web app

- Dependent on the Safe transaction service (indexer)
- Alternatives
    - If the Safe web app is down
    - E.g. Apps that run their own parallel instance of the Safe transaction service
        - Coinshift: [coinshift.xyz](https://coinshift.xyz)
        - Multis: [multis.com](https://multis.com)
    - [Safe command line interface (Safe CLI)](#Safe-command-line-interface-Safe-CLI)

# Safe command line interface (Safe CLI)

- Safe CLI tutorials
    - Common use cases
    - GitHub: [github.com/5afe/safe-cli](https://github.com/5afe/safe-cli)
    - [Trustless interface](https://help.safe.global/en/articles/40866-trustless-interface) *by Safe*
    - [Summoning a Decentralised Safe Registry](https://mirror.xyz/0013700.eth/HAxUoydAAvcEnygRvGsqecAhC1XcfcQlAy6x_htY3ZQ) *by Daoism Systems*

# Safe transaction service features

1. Off-chain signature aggregation
    a. This is difficult to built in a more decentralized approach
    b. Potential solutions
    - Use Waku for signature aggregation
    - Post the signatures to a significantly less expensive execution layer instead of mainnet
2. Transaction history
3. Show token balances automatically
    a. Cannot be handled with a simple RPC connection, it requires an index
    
# Opportunities

## Simple app for users

- A working UI where users can use basic Safe account features if the main Safe Ecosystem Foundation hosted service is unavailable
- E.g. Basic app hosted by IPFS
    - Enables onchain approvals (signatures) only
    - Or it could present approvals to the user for manual aggregation/import/export
    - Also useful for deploying infrastructure on chains that don't yet have Safe transaction service support

## More distributed backend service for builders

- Alternative backend services for developers to build on that are not reliant on the Safe Ecosystem Foundation hosted service
- E.g. Use Ceramic + ComposeDB to move towards a more distributed framework that also allows apps to perform a high amount of transactions
    - [Summoning a Decentralised Safe Registry](https://mirror.xyz/0013700.eth/HAxUoydAAvcEnygRvGsqecAhC1XcfcQlAy6x_htY3ZQ) *by Daoism Systems*
    - [Setting up a decentralized Safe registry with ComposeDB](https://daoismsystems.notion.site/Setting-up-a-decentralized-Safe-registry-with-ComposeDB-01aad3c49eba4f90a8648dcd83f9dd6e) *by Daoism Systems*
    - [ceramic.network/composedb](https://ceramic.network/composedb)

## Risks

- IPFS hosted solution will not be sufficient due to the backend service dependencies
- Maintaining a workable app with good UX is not trivial and requires ongoing support and resources

# Sample apps

## Powered by Waku

#### Waku

- Site: [waku.org](https://waku.org/)
- About
    - Decentralized messaging service for transaction history data (indexer)
    - Uses zero-knowledge encryption
    - Powers the Status app: [Peer-to-Peer Messaging – Where Whisper Falls Short and Waku Picks Up](https://our.status.im/peer-to-peer-messaging-where-whisper-falls-short-and-waku-picks-up/) *by Status*

#### Safe apps

- Waku Powered Gnosis Safe: [github.com/Soptq/gnosis-safe-waku](https://github.com/Soptq/gnosis-safe-waku)
- Rugged Multisig: [github.com/shafayeatsumit/rugged-multisig](https://github.com/shafayeatsumit/rugged-multisig)

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