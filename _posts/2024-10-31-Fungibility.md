---
title: Fungibility As a Spectrum
description: Why fungibility is not so black and white
date: 2024-10-31 10:00:00 - 500
categories: [Technical Writing]
tags: [denota, tokens, blockchain, utxo]
---

Since the launch of Ethereum, the vast majority of blockchains have elected to use the **account**-**based model** of tracking ownership of funds. It is **simpler** to understand and easier to program financial applications when one deals with a single state variable instead of an arbitrary number of cash-like notes. Global accounts along with native smart contracts enabled a slew of financial applications, and along with the standardization of fungible assets, led to a renaissance of protocols for borrowing/lending, swapping, tokenization, and more. Standardizing the interface for fungible tokens in ERC20 allowed protocols to instantly support all tokens, past and future, that implement that interface and to tap into their network effects by doing so. For developers this greatly reduced complexity, redundancy, and shortened their time to market significantly. 

However, the ERC20 standard often hides the fact that in practice most fungible tokens are **not truly fungible**; USDC in a blacklisted address is worth less than USDC in a non-sanctioned one. Even across dollar-pegged stablecoins, some have more trust assumptions than others. Fungibility gives the illusion that you are interacting with another permissionless, atomic unit of value, when this is often not the case. Rather, fungibility is a spectrum and how we encode this is up to developers and the ecosystem who adopts those standards. Arguably though, most financial transactions are non-fungible. Real estate, bonds, and even payments are unique so by abstracting them into fungible forms it hides this fact and the associated risk. Fungibility makes sense when all interactions with the asset are uniform but something like commerce has different semantics; I send you this value under this conditions and now fungibility runs into issues. How does one reverse a transfer when something goes wrong? How does one do so without subjecting all token holders under the same conditions? How does … 

When ERC721 came along it defined how a single contract could distinguish assets using an identifier instead of a balance and attach token specific metadata. While this made it an ideal form factor to tokenize art, it also meant that other data like liquidity positions, loan amounts, and more could be represented as well. And although existing ERC20 supporting protocols could not accept these non-fungible ones, a **new design space** opened up for more sophisticated financial instruments.

[More Coming Soon]