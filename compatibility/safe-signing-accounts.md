---
title: 🔰 Signing accounts
tags: safe
description: Signing accounts
image: https://pbs.twimg.com/profile_banners/8467082/1674046807/1500x500
---

Signing accounts
===

## Powered by Blocknative

- Site: [Blocknative](https://www.blocknative.com/)
- Uses Onboard.js SDK to provide crypto account integrations
    - Blocknative adds support for the crypto account SDKs
    - Crypto accounts work with Blocknative to have their SDK added to the API library.
- Compatible accounts: [Web3-Onboard](https://docs.blocknative.com/onboard#wallet-modules)
- GitHub: [github.com/blocknative/onboard](https://github.com/blocknative/onboard)

## Hardware accounts

*See [Hardware accounts guide](https://docs.google.com/document/d/1_E7RjMZAfkoNH7ZqF63p9ZUWpeKXzo9QC9L32K3raPs/)*

#### Compatible

- [Trezor](https://docs.google.com/document/u/0/d/1Gr9ogLVNu9f7CL852RUfy6iEtKSV29P3gsyT3VKuhus/edit)
- [Ledger](https://docs.google.com/document/u/0/d/17j_9Qpc2qB5dqYWTP20TAnqWHbmjx1NkPdgGDZo1M2Y/edit)
- [GridPlus](https://docs.google.com/document/u/0/d/1iLxHcMr5nBVahFPvpCdHi5DYy0iyY0c0PRmBM2p0cj4/edit)

#### Not compatible

- [Status](https://docs.google.com/document/d/1_E7RjMZAfkoNH7ZqF63p9ZUWpeKXzo9QC9L32K3raPs/edit#bookmark=kix.oaqeyspwy9jr) + Keycard
    - Safe is waiting for the desktop app from Status
- [KeepKey](https://docs.google.com/document/d/1_E7RjMZAfkoNH7ZqF63p9ZUWpeKXzo9QC9L32K3raPs/edit#bookmark=id.6fh4iy9b03w3)
    - [In-progress](https://discord.com/channels/554694662431178782/554694662896615436/848638645438906438) *on Discord 2021-05-30*
    - [Launched](https://discord.com/channels/477106835862716416/477391201708802058/855211798517121057) *on Discord 2021-06-17*
- CoolWallet
    - Looking into it *by Email 2021-05-31*
- BitBox
    - [Not planned](https://github.com/digitalbitbox/bitbox02-firmware/issues/754) *on GitHub 2021-05-31*

## Software accounts

*See [Software accounts guide](https://docs.google.com/document/d/11HKTi5Z3HTFrn7sejQckkkmreA3zzfKwhEQyOudnD8g/edit#heading=h.i6hgh1nbdhb4)*

#### Compatible

- MetaMask
    - Safe desktop app
        - More secure
        - Connect with MetaMask mobile app via WalletConnect.
    - Safe web app: [app.safe.global](https://app.safe.global/)
        - Connect with MetaMask add-on/extension.
- Coinbase Wallet
- Portis (Shapeshift)
- WalletConnect

#### Not compatible

- MyEtherWallet
- MyCryptoWallet

## Safe apps

- *See [What are Safe Apps?](https://help.gnosis-safe.io/en/articles/4022022-what-are-safe-apps)*
- Interact with apps directly from the Safe app.
- Safer than interacting with web extension wallets.
    - Implements HTML iframes
- Connect with any app outside Safe Apps with [WalletConnect](https://docs.google.com/document/d/11HKTi5Z3HTFrn7sejQckkkmreA3zzfKwhEQyOudnD8g/edit#bookmark=kix.oynbkhfgpm9s).
    - [WalletConnect Safe App](https://help.safe.global/en/articles/4356253-walletconnect-safe-app)
    - [Connect to dApps with WalletConnect on mobile](https://help.safe.global/en/articles/5307197-connect-to-dapps-with-walletconnect-on-mobile)

## Mobile

- Features: Confirm or reject transactions
- Sign transactions initiated from desktop/web app: *[Sign transactions](https://help.safe.global/en/articles/4592015-sign-transactions)*
- [Signing on Mobile](https://help.safe.global/en/collections/2378018-safe-mobile#signing-on-mobile)
    - [Connect external signer key](https://help.safe.global/en/articles/5335651-connect-external-signer-key) (Only on iOS as experimental 2023-02-22)
    - [Import owner key](https://help.safe.global/en/articles/5334002-import-owner-key)
        - Import in airplane/offline mode for improved security.
    - [Generate new signer key](https://help.safe.global/en/articles/5333937-generate-new-signer-key) (12-word seed phrase)

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