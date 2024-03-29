---
title: 🔰 Safe setup
tags: safe
description: Safe setup
image: https://pbs.twimg.com/profile_banners/8467082/1674046807/1500x500
---

Setup
===

*See [What Safe setup should I use?](https://help.safe.global/en/articles/40835-what-safe-setup-should-i-use)*

#### 1. Go to [app.safe.global](https://app.safe.global)

#### 2. Add ETH addresses as signers.

*See [Creating a Safe on a Web browser](https://help.safe.global/en/articles/40868-creating-a-safe-on-a-web-browser)*
    
a. Ensure the first account has an ETH balance to sign the first transaction.
    
b. Hardware accounts
    
- Ledger
    - *See [Sign transactions with a Ledger device](https://help.safe.global/en/articles/40850-sign-transactions-with-a-ledger-device)*
    1. Choose *Ethereum Ledger Live - m/44'/60'*
    2. Configure settings: ETH app > *Settings*
        1. *Contract data* > Select *Allowed*
        2. *Debug data* > Select *Displayed - [Disable display of full contract data for approvals on Ledger hardware wallet](https://help.safe.global/en/articles/40851-disable-display-of-full-contract-data-for-approvals-on-ledger-hardware-wallet) (Not recommended)*
        3. *Nonce* > Select *Displayed*
        4. Turn the Ledger off and reconnect.
- Trezor
    - *See [Sign transactions with a Trezor hardware wallet](https://help.safe.global/en/articles/40832-sign-transactions-with-a-trezor-hardware-wallet)*

c. Choose X out of T threshold for key approval.

#### 3. [Verify Safe creation](https://help.safe.global/en/articles/40834-verify-safe-creation)

a. Mark as a proxy: 1 txn must be executed with the Safe or ETH received

#### 4. Manage cosigners

a. Share the account address with cosigners.
1. Copy and paste the public address from the drawer menu in the top-left.
2. Cosigners import/load the account address
 
   a. Select *Safe* in the top-left corner of the screen or the right arrow `>` in the left navigation menu > Select *Add Safe*
   
   b. Select *Load Existing Safe*

b. Provide confirmation for transactions (txns)
1. Left drawer menu > Select *Transactions*
2. Select *Pending* under the *Status* column and confirm.
3. [Verify](https://hackmd.io/@safe/oi/https%3A%2F%2Fhackmd.io%2F%40safe%2Fverify-transactions) the smart contract details.

c. Review ownership
1. *Settings* > *Owners*
2. Add/remove cosigners

#### 5. Back up the Safe account.

- *See [Backup and recovery](https://hackmd.io/@safe/oi/https%3A%2F%2Fhackmd.io%2F%40safe%2Fbackup-and-recovery)*

#### 6. Upgrades

a. Important to prevent against latest attacks and vulnerabilities

b. Safe App: Left navigation menu > *Settings* > *Safe Details* > *Contract Version* > Select *Update Safe*

c. Requires an on-chain txn

d. May skip version updates, e.g. Can upgrade from 1.0 to 2.0 while skipping 1.5

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