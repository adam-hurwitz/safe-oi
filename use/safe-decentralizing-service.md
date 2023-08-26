---
title: 🔰 Safe decentralizing service
tags: safe
description: Safe decentralizing service
image: https://pbs.twimg.com/profile_banners/8467082/1674046807/1500x500
---

<h1 style="text-align: center;">Safe decentralizing service</h1>

# Safe web app

- Dependent on the Safe transaction service
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

# Safe transaction service

Useful features

1. Off-chain signature aggregation
    a. This is difficult to built in a more decentralized approach
    b. Potential solutions
    - Use Waku for signature aggregation
    - Post the signatures to a significantly less expensive execution layer instead of mainnet
2. Transaction history
3. Show token balances automatically
    a. Cannot be handled with a simple RPC connection, it requires an index
    
# Decentralizing Safe transaction service

## Proof-of-concept (PoC)

- Minimalist UI
- An IPFS hosted version could enable onchain signatures only
- Or it could present them to the user for manual aggregation/import/export
- Also useful deploy infrastructure on chains that doesn’t yet have Safe transaction service support

## Risks

- IPFS hosted solution will not be sufficient due to the backend service dependencies
- Maintaining a workable app with good UX is not trivial and requires ongoing support and resources

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