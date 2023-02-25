---
title: 🔰 Verify Safe transactions
tags: Safe
description: Verify Safe transactions
image: https://pbs.twimg.com/profile_banners/8467082/1674046807/1500x500
---

Verify transactions
===

## About

- Verify transactions (txns) before approval.
- Ensure the data showing on Safe is the same as on the hardware wallet(s).
- Verifies off-chain confirmations made as part of a multisig account.
- [What is the Safe transaction hash (safeTxHash)?](https://help.safe.global/en/articles/5246870-what-is-the-safe-transaction-hash-safetxhash)
    - Unique code generated for a transaction
    - Specific to the Safe protocol

## Verify Off-chain transaction with the *safeTxHash*

*See [How to verify Gnosis Safe transactions on a hardware wallet](https://help.safe.global/en/articles/4818770-how-to-verify-gnosis-safe-transactions-on-a-hardware-wallet)*
- [Off-chain confirmations with a Ledger](https://help.safe.global/en/articles/4818770-how-to-verify-gnosis-safe-transactions-on-a-hardware-wallet#h_4236c727a5)
- [On-chain executions with a Ledger](https://help.safe.global/en/articles/4818770-how-to-verify-gnosis-safe-transactions-on-a-hardware-wallet#h_012f77a72f)

#### 1. Create a *New Transaction* with a signing account.

a. Verify the transaction (txn) details from `execTransaction` (Save this to verify the `safeTxHash` later).    
- `to`: Token contract address
- `value`: Amount of ETH to send ([Convert from Wei to Ether](https://www.wolframalpha.com/input/?i=1000000000000000000+wei+to+ether))
- `data`
- `null` = `0x`
- `gasPrice`: Amount of gas estimated to complete the txn
- `nonce`
    1. Count of txns executed from the Safe (Received txns don't count)
    2. Used to query the safe backend for txn data

#### 2. *Confirm* in Safe with a second signing account.

a. Deselect *Execute transaction* (Does not execute immediately)

b. *Approve Transaction*

c. Do not select *Sign message* on the wallet until completing Step 3.

#### 3. Compare the `safeTxHash`.

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

#### 4. Sign with the cosigner wallet/address.

### Verify on-chain txn contract data (Ledger only)

*See [On-chain executions with Ledger](https://help.safe.global/en/articles/4818770-how-to-verify-gnosis-safe-transactions-on-a-hardware-wallet#h_012f77a72f)*

#### 5. Select _Execute_ in Safe.

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