---
title: Denota Whitepaper
description: The programmable escrow protocol
date: 2024-12-15 14:00:00 - 500
categories: [Portfolio, Project Overview]
tags: [solidity, blockchain, escrow, utxo, denota]
---

## Abstract

Denota is a programmable escrow protocol implemented for the Ethereum Virtual Machine that allows users to convert ERC20 tokens into ERC721-compliant, UTXO-like assets. Each escrow NFT (or "Nota" for short) supports arbitrary metadata attachment and hook code execution upon interaction. Hooks can execute both before and after actions that modify the Nota’s state, can be chained together, and support dynamic fees upon completion. Hooks can be deployed permissionlessly and function as both a storage location for arbitrary Nota data and for action validation. Denota, in effect, generalizes the concept of token wrappers into programmable UTXOs and provides a framework for developers to explore new design spaces using before and after action hooks.

## 1 Introduction

The creation of a Peer-to-Peer Electronic Cash System has been both the origin and elusive goal of cryptocurrency since Bitcoin's inception. While cryptocurrency enables trustless payments, it also presents challenges due to the absence of financial protections. Satoshi Nakamoto suggested a "routine escrow mechanism" to protect buyers, and with the recent uptick in crypto payments, the need for buyer protections will become increasingly apparent. Existing crypto escrow solutions have been developed and deployed but have seen insignificant adoption. This is partly due to poor form factors— antipatterns like illiquidity, rigidity, and lack of interoperability—creating additional hurdles for widespread adoption.

Although payments and escrows are often viewed as mutually exclusive systems, in reality, payments operate as a form of implicit escrow where banks serve as escrow agents releasing and settling funds. Each payment is in fact **non-fungible** and it is the payment system that abstracts this from end users. Essential data about the transfer of funds is unique and attached to the payment enabling enforcement of KYC/AML, consumer protections, financial management, and more. Much of this functionality isn’t built into cryptocurrency today or is impossible without attached metadata. ERC20 transfers are the most popular but lack a way of attaching additional data within the same transaction.

I present Denota, a programmable escrow protocol which fixes many of the issues current day escrow face and allows developers to deploy custom extensions in the form of hook contracts. Denota can be thought of as a generalization of a token wrapper- a way to take in one asset and issue a functionally altered asset. By allowing developers to wrap ERC20 tokens within an ERC721 they can attach metadata and program rules around changes in the NFT’s ownership or escrow balance. This enables users to create and accept ERC20’s with additional metadata and conditions attached in an opt-in manner. 

Denota Protocol addresses these challenges by offering a flexible, programmable escrow system that allows for the attachment of metadata and execution of custom logic through hooks, all within a non-custodial and permissionless framework. The core component of Denota is the `NotaRegistrar` contract, which manages the creation, ownership, and lifecycle of Notas. By wrapping ERC20 tokens within an ERC721 token, developers can define what metadata can be attached and program rules around changes in the NFT's ownership or escrow balance. 

Denota’s most notable features are as follows:

- **Hooks:** Cheap and easy-to-deploy custom logic that executes at specific points in a Nota's lifecycle. Hooks can execute both before and after actions that modify a Nota's state, can be chained together, and support dynamic fees upon completion. They enable developers to define dynamic behaviors, enforce validation rules, and integrate with other protocols.
- **Singleton Contract:** Denota uses a singleton design, meaning all Notas are managed within a single contract (`NotaRegistrar`). This simplifies interactions, reduces gas costs, and allows for a single ERC20 approval. It provides a standard interface, trusted execution, and a tooling ecosystem for improved development and integration.
- **ERC20 and ERC721 Compatibility:** Seamless integration with existing token standards, allowing any ERC20 token to be wrapped into ERC721 Notas. This enables integration for existing and future protocols that support these standards.
- **Dynamic Metadata:** Ability to attach and update arbitrary metadata on Notas. Through hooks, Notas can have dynamic metadata, allowing for customizable token representations and integrations with applications that utilize this metadata like wallets and marketplaces.
- **Permissionless and Non-Custodial:** Denota maintains a trust-minimized architecture—non-custodial, non-upgradable, with no governance—ensuring users have full control over their assets with additional opt-in trust assumptions through hooks.

[More coming soon]