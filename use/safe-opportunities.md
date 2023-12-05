---
title: 🔰 Safe opportunities
tags: safe
description: Safe opportunities
image: https://pbs.twimg.com/profile_banners/8467082/1674046807/1500x500
---

<h1 style="text-align: center;">Safe opportunities</h1>

# Security

#### Token approval management (P1)

- Native feature or close integration with [Revoke.cash](https://revoke.cash) as Safe module (Similar to [spending limits](https://hackmd.io/@safe/og/https%3A%2F%2Fhackmd.io%2F%40safe%2Fperform-transactions#Spending-approvals-and-limits))
- View current and set specific token approval amounts (Similar to MetaMask's advanced token allowance field)
- Manually set smart contract token approval amount
    - Not natively supported: *[Safe Community Discord #safe-web](https://discord.com/channels/907968493134155807/908129365345312768/948697325411401778) 2022-03-02*
    - Can use [Transaction Builder](https://help.safe.global/en/articles/4680071-transaction-builder) app

#### Access control (P1)

- About
    - [Crypto account access control](https://hackmd.io/@openinfo/crypto-access-control)
    - Safe forum: [🫱🏻‍🫲🏼 Safe access control to improve security and UX](https://forum.gnosis-safe.io/t/delegate-safe-access-to-improve-security-and-ux/2646) *2023-02-06*
- Potential features
    - Safe module for delegation of permissions with [Delegate.cash](https://delegate.cash) registry
    - Manage delegations: Set permissions, view, and revoke
        - Build custom permissions
        - View all active and past permissions
        - Revoke
            - E.g. All or specific owners can revoke access.
            - Time parameters
    - More convenient access to other apps
        - E.g. Social and gaming
    - Compartmentalize access
        - E.g. Different levels of access for social and gaming apps vs finance vs treasury
    - Social recovery governance permission
        - Specific permissions to apps, features, and limits
    - Issue shares by delegating NFTs or tokens
        - Instead of sharing multiple signing keys
    - Improve *[Spending Limit](https://help.safe.global/en/articles/4667979-set-up-and-use-spending-limits)* module
        - Extend spending limits to non-owner accounts
    - Question: Is there potential to build off of or improve Snapshot delegation of $SAFE governance tokens?
        - Snapshot does not offer voting for people's roles and their access to sign-in with Ethereum (SIWE) apps.
        - Currently $SAFE is non-transferable and will be made transferable in the future.
- Module naming: Be mindful of overlap with [token approval management](#Token-approval-management-P1), e.g. [Revoke.cash](https://revoke.cash/).
- Collaborations
    - Customization/white-labeling
        - Can abstract the Delegate.cash technology completely from the UX or partner with Delegate.cash to showcase it.
    - Delegate.cash (Including [@0xfoobar](http://twitter.com/0xfoobar)'s team) have communicated interest in supporting co-marketing efforts, e.g. Push for upgrade from custodians to Safe adoption.
- Safe app adoption
    - Castle: [@CastleLinkHQ tweet 2023-01-16](https://twitter.com/CastleLinkHQ/status/1615044250596708354)

#### Show who you know has used a given contract (P1)

- Similar to social proof on Twitter seeing who you follow follows another account to make sure you don't follow a fake account.
- Based on your contact list of addresses saved.
- Shows contact's transaction count with a given contract.
- Can message contacts about questions on a given contract based on their experience.
- *See [@adamshurwitz Tweet 2023-03-11](https://twitter.com/adamshurwitz/status/1634709915066327040)*

#### Verify cosigners with an off-chain transaction (P2)

- Show cosigner info on the hardware devices directly for users to verify prior to signing a transaction.


# UX

#### Multinetwork support (P1)

- *See [How can a Safe hold asset on multiple chains?](https://forum.gnosis-safe.io/t/how-can-a-safe-hold-asset-on-multiple-chains/2242) on Safe forum 2023-01-03*
- Filters
    - v1: Provide multi-select filters to customize each feature view.
        - Each feature view may have different importance and use cases based on the filter
    - v2: Save filter views.
        - Quickly save and view saved filters.
    - v3: Export saved filter settings to back up.
    - E.g. Screenshots of [MetaMask](https://drive.google.com/file/d/1chzPea899SFTOjn4T9IEJAvOXHsSzF8S/view?usp=share_link) and [TaxBit](https://drive.google.com/file/d/1kTa9O0RUqEwP-6nw6wSWkud1ocW3WGqo/view?usp=share_link) filters
- Filter types
    - Protocol, e.g., Ethereum, Gnosis Chain (xDAI), Arbitrum, and etc.
    - Assets, e.g., BTC, ETH, SAFE, and etc.
    - Apps, e.g., Safe, CowSwap, Uniswap, and etc.
    - Date, e.g., 2023-02-01 to 2023-02-09
- Feature views
    - Assets (Includes all tokens and NFTs)
    - Transactions
    - Address Book
    - Apps
    - Settings
- Multinetwork products
    - [portfolio.metamask.io](https://portfolio.metamask.io/)
    - [app.taxbit.com](https://app.taxbit.com/)

#### Create end user account (EOA) address on web and desktop (P2)

- Available on mobile
- Choose between 12 and 24-word seed phrase: [Generate new signer key](https://help.safe.global/en/articles/5333937-generate-new-signer-key)

#### Safe sub accounts for different use cases (P2)

- E.g. Ledger Live can create and label multiple ETH and BTC account addresses under one BIP39 seed.
- Workaround: Create separate Safe accounts with the same signing accounts.

#### Transaction management (P2)

- Speed up an approved and pending transaction.
    - Feature: Add more gas.
    - E.g. Too low of a gas price was initially paid.
    - Workaround: Submit a new transaction with the same `nonce`.
        1. Restart Safe to clear the pending transaction from the app's local memory.
        2. [Resubmit and overwrite the transaction.](https://hackmd.io/@safe/og/https%3A%2F%2Fhackmd.io%2F%40safe%2Fperform-transactions#Advanced-options)
- Cancel an approved and pending transaction.
    - Workaround: Submit a new transaction with the same nonce.
        1. Restart Safe to clear the pending transaction from the app's local memory.
        2. [Cancel the transaction.](https://hackmd.io/@safe/og/https%3A%2F%2Fhackmd.io%2F%40safe%2Fperform-transactions#Advanced-options)

#### Add custom networks in the app (P2)

- Similar to [MetaMask](https://docs.google.com/document/d/12SxCBnZ18YjKYg7f6xzlaqy4GyAS4nih8yrQXpmaoac/edit#heading=h.r6seu1m60dp4).
    - Support custom RPCs (Remote Procedure Call) in the app.
- Workaround: Use [Safe-CLI](https://github.com/5afe/safe-cli#safe-cli)
    - Tutorial: [How to use the command line to send out assets from a Safe on BSC](https://help.safe.global/en/articles/5505933-how-to-use-the-command-line-to-send-out-assets-from-a-safe-on-bsc)

#### Safe transactions (P3)

1. Main Safe account creates a new "temporary" account address
2. Moves specified assets to the temporary address
    a. Sets token approval limit(s)
    b. Performs transaction(s), e.g. trade
3. Move assets from the temporary address back to the main Safe account

#### Yubikey (P3)

- Verify/sign a transaction with a Yubikey.
- Generate an account address with a Yubikey.
- Potential security concerns since the software is the trusted source of transaction information instead of a hardware device to read information off of.


# Governance

#### Structure of SafeDAO<>Safe Ecosystem Foundation (SEF) (P0)

- [SafeDAO > Governance > Incorporation](https://hackmd.io/@safedao/og#Incorporation)
- [DAOs > Related organizations](https://docs.google.com/document/d/109xrmTFRvI1nBPEOKb8O2sunNJ7HkENNqVM_8t3804E/edit#heading=h.i4o711hu29l3)

#### Safe open guides (P1)

- [Safe open guides](https://forum.gnosis-safe.io/t/safe-open-guides/2539) _on Safe forum 2023-01-28_
- v1: Complementary and separate core team documentation and community guides
- Long-term vision
    - Potentially unified core team documentation and community guides
    - Attribution of contributions (Similar to StackOverflow)
    - Useful to know what content is from the core team vs the community.

# SAFE token usability

#### SAFE staking

- Feature access, security, and spam prevention
- Examples
    - Token curated registry (TCR)
        - About
            - Decentralized registry where token holders are mutually incentivized to maintain a high quality
            - Move towards automation
            - Requires additional data points other than tokens alone to determine a quality score to avoid gaming the system
        - Registries
            - Become a part of the Ecosystem Hub and update info
            - Add a module
    - Advanced features for teams, businesses, and individuals
        - E.g. The Google Play and Apple App store’s create self-serve recurring tools and services like analytics, reviews, customer support for developers.
        - Moving forward, instead of having centralized tools like with Google and Apple for fully integrated services (analytics, reviews, customer support, etc.), developers could choose from multiple services, not just ones Safe builds, with all accepting SAFE tokens.
- Resources
    - [Safe Token Value Alignment Program](https://forum.safe.global/t/safe-token-value-alignment-program/3766/2) *by Adam Hurwitz*
    - [Overview of Token Curated Registries](https://republic.com/blog/crypto/overview-of-token-curated-registries) *by Republic*

#### Mobile

- To be determined opportunities with decentralized mobile operating systems
- ethOS: [ethosmobile.org](https://www.ethosmobile.org)
- GrapheneOS: [grapheneos.org](https://grapheneos.org)
- Saga: [solanamobile.com](https://solanamobile.com)

#### Value Alignment Program (VAP)

- About: Agreement between SafeDAO and teams for a trade of SAFE tokens for a portion of the project/protocol/product's equity/revenue share/token
- *See [Safe Token Value Alignment Program](https://forum.safe.global/t/safe-token-value-alignment-program/3766) by LongHash Ventures*

# Decentralization

- [Decentralizing Safe](https://hackmd.io/@safe/oi/https%3A%2F%2Fhackmd.io%2F%40safe%2Fdecentralize)

# Multinetwork

- [Multinetwork Safe](https://hackmd.io/@safe/oi/https%3A%2F%2Fhackmd.io%2F%40safe%2Fmultinetwork)

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