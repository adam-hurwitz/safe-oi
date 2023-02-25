---
title: 🔰 Safe backup and recovery
tags: Safe
description: Safe backup and recovery
image: https://pbs.twimg.com/profile_banners/8467082/1674046807/1500x500
---

Backup and recovery
===

## Steps

1. Save [information](#Information-to-save) offline with multiple redundancies.
2. Test the recovery process.
    a. Setup
    1. Use a new wallet addresses that will only be used for testing.
    2. Use a low amount of funds.
    
    b. Optional interoperability test
    1. Swap the seed phrases between signing accounts/devices when going through the recovery process.
    2. You may need the original derivation path(s) for the wallet addresses.
3. Verify the cosigners/owners have the expected address.
    a. Verify the receive address in each signing account/device's app.
    b. Verify the Safe account address when loaded into the Safe app after recovery.

## Information to save

- The Safe account's require threshold of private signing accounts/keys
    - Seed phrase(s)
- All signing accounts
    - Derivation paths (If a hardware wallet)
- Recommended
    - Safe account address
        - This can be found in the transaction history in a worst-case.

## Without the Safe team

#### About

- Use in a worst-case scenario where the core Safe team no longer exists.
- *See [Trustless interface](https://help.safe.global/en/articles/3940868-trustless-interface)*

#### Components

1. User Interface (UI) options
    - Download the Safe app.
        - [GitHub releases](https://github.com/safe-global/safe-react/releases)
        - Or use the last desktop app with a checksum and [verify the download](https://help.safe.global/en/articles/4062072-verifying-the-desktop-app-authenticity).
    - Use the web app: [app.safe.global](https://app.safe.global)
    - Previous Safe smart contract versions work with the Safe app UIs: *[Add hardware wallet support #29](https://github.com/5afe/safe-cli/issues/29#issuecomment-838723509)*

2. Smart contracts, backend infrastructure, and transaction indexer
    a. [Command Line Interface](https://github.com/5afe/safe-cli#safe-cli) (CLI)
    - Use the commands in the computer's terminal.
    - The CLI will not work if all signing accounts are hardware wallets.
        - You must use a version of the Safe app in step 1.
        - *See [Add hardware wallet support #29](https://github.com/5afe/safe-cli/issues/29)*
    
    b. Advanced users (Requires testing 2023-02-23)
    - *Note*: Test without as many as Safe backend services and dependencies as possible.
    1. Interact with the smart contract directly: [Guide: Integrating the Safe Core SDK](https://github.com/safe-global/safe-core-sdk/blob/main/guides/integrating-the-safe-core-sdk.md)
    2. Run the code with the [Safe Transaction Service](https://github.com/safe-global/safe-transaction-service#safe-transaction-service).
        - Connect to an Ethereum node to run the service.

<p style="text-align: center; font-style: italic">This content is not financial, technical, or legal advice. Always consult a financial professional and do your own research.</p>

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