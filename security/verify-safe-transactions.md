---
title: 🔰 Verify Safe transactions
tags: safe
description: Verify Safe transactions
image: https://pbs.twimg.com/profile_banners/8467082/1674046807/1500x500
---

<h1 style="text-align: center;">Verify Safe transactions</h1>

# About

- Verify transactions (txns) before approval.
- Ensure the data showing on Safe is the same as what is processed on the hardware account(s).
- Verifies off-chain confirmations made as part of a multisignature account.

# Multi-factor authentication (MFA)

## About

- It's best to verify and approve transactions using multiple devices
- Use both the Safe web and mobile apps to approve actions
- E.g. Approve on web with software account (MetaMask) and on mobile with hardware account (Ledger)

## Opportunties

#### Connect external approval accounts on Android (P0)

- This is essential to approve actions across multiple devices for security
- E.g. Approve on web with hardware account (Ledger) and on mobile with software account (MetaMask) or another account through WalletConnect
- Improved security than "Importing existing owner key"    
    - Separates concerns between the Safe approval UX on web and mobile and the software account's private key, e.g. MetaMask
    - Reduces the exposure of the software account, e.g. MetaMask, being shared across multiple apps
- Currently only available for iOS

## Resources

- [Sign transactions: Confirm transactions on-the-go using Safe Mobile](https://help.safe.global/en/?q=Sign+transactions%3A+Confirm+transactions+on-the-go+using+Safe+Mobile)
- [Connect external signer key](https://help.safe.global/en/?q=Connect+external+signer+key)
- [Import owner key](https://help.safe.global/en/?q=import+owner+key)
- [Increasing security of “multifactor” (MFA) Safe approval accounts 🔑](https://forum.safe.global/t/increasing-security-of-multifactor-safe-approval-accounts/4453) *on SafeDAO forum*

# Verify Off-chain transaction with the *safeTxHash*

## About

- [What is the Safe transaction hash (safeTxHash)?](https://help.safe.global/en/?q=What+is+the+Safe+transaction+hash+%28safeTxHash%29%3F)
    - Unique code generated for a transaction
    - Specific to the Safe protocol
- [How to verify Safe transactions on a hardware wallet](https://help.safe.global/en/?q=How+to+verify+Safe+transactions+on+a+hardware+wallet)
    - Off-chain confirmations with Ledger
    - On-chain executions with Ledger

## 1. Create a *New Transaction* with a signing account.

a. Verify the transaction (txn) details from `execTransaction` (Save this to verify the `safeTxHash` later).    
- `to`: Token contract address
- `value`: Amount of ETH to send ([Convert from Wei to Ether](https://www.wolframalpha.com/input/?i=1000000000000000000+wei+to+ether))
- `data`
- `null` = `0x`
- `gasPrice`: Amount of gas estimated to complete the txn
- `nonce`
    1. Count of txns executed from the Safe (Received txns don't count)
    2. Used to query the safe backend for txn data

## 2. *Confirm* in Safe with a second signing account.

a. Deselect *Execute transaction* (Does not execute immediately)

b. *Approve Transaction*

c. Do not select *Sign message* on the wallet until completing Step 3.

## 3. Compare the `safeTxHash`.

a. Query the Safe backend using the Safe contract address and `nonce` found in the Safe > *Transactions > Queue*.
- Format: `https://safe-transaction-mainnet.safe.global/api/v1/safes/{SAFE_WALLET_ADDRESS}/multisig-transactions/?nonce={TXN_NONCE}`
- E.g. [https://safe-transaction-mainnet.safe.global/api/v1/safes/0xA063Cb7CFd8E57c30c788A0572CBbf2129ae56B6/multisig-transactions/?nonce=52](https://safe-transaction-mainnet.safe.global/api/v1/safes/0xA063Cb7CFd8E57c30c788A0572CBbf2129ae56B6/multisig-transactions/?nonce=52)
    
b. Generate the `safeTxHash` on Etherscan.
1. Open the Safe account on Etherscan.   
2. Mark as a proxy: *Contract* > *More options* > *Is this a Proxy?* > [Verify Safe creation](https://help.safe.global/en/articles/4774916-verify-safe-creation).
3. Create the hash
    1. Fill in all of the parameter data from the query results in *Step 3.a* for `getTransactionHash`.
        - If there's an error check for the same capitalization in the `to address`.
    2. Select *Query*.
4. Compare the Safe and Etherscan txn hash.
    - The result should be equal to the `safeTxHash` from the Safe backend query in *Step 3.a*.
    
c. Compare the Safe and hardware wallet txn hashes.
1. Trezor and MetaMask: Compare the Safe `safeTxHash` with the  `safeTxHash` shown on the device.
2. Ledger
    1. [Convert](https://emn178.github.io/online-tools/sha256.html) the hash from *Step 3.b.4* into the `safeTxHash`.
        a. Remove the prepended `0x`.
        b. Input type: *Hex* or *bytes*
    2. Compare the resulting hash to Ledger's hash.

## 4. Sign with the approval account.

4a. Verify on-chain txn contract data (Ledger only)
- *See [How to verify Safe transactions on a hardware wallet > On-chain executions with Ledger](https://help.safe.global/en/?q=How+to+verify+Safe+transactions+on+a+hardware+wallet)*

## 5. Select _Execute_ in Safe.

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