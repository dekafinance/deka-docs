---
id: overview
title: Overview
sidebar_label: Overview
slug: /overview/
---

:::note

Welcome to the DEKA protocol documentation guide! This is the up to date source of truth for DEKA protocol functionality and production contracts. If there is anything unclear or out of date, please submit a pull request to the repository on Github or join our Discord server.

:::

Existing Defi projects aim to provide annualized earnings for specific currencies using smart contracts. Usually, once the user funds are successfully allocated in the smart contract, earnings are calculated every Binance Smart Chain block (every ~3 seconds).

So, if the annualized percentage yield (APY) is 10% and a user stakes $1,000, after one year, he will be able to withdraw $1,100.

DEKA is a permissionless protocol allowing everyone to stake $DKA and earn instant upfront yield.

DEKA protocol enables users to stake tokens and earn the yield immediately. Using the same example as above, if the user stakes $1,000 for one year, he will get $100 instantly and have his $1,000 locked for one year.

Because of its permissionless nature, it will exist for as long as Binance Smart Chain does.

The DEKA protocol is fueled by the $DKA token the same way Binance Smart Chain is fueled by $BNB.

## Features
The DEKA protocol is built with numerous useful features:
- Permissionless
- Open Source
- Stake $DKA and redirect the yield to an externally owned account (EOA) or a smart contract.
- Unstake $DKA after the expiration period is over.
- Unstake $DKA before the expiration period is over, but burn percentage of the staked amount based on the remaining time.
- Dynamic DPY (Deka Percentage Yield) calculated with the formula:
$$
(1 - \frac{total\char`_staked\char`_amount + new\char`_staked\char`_amount}{total\char`_supply}) / 2
$$
- Dynamic UPY (Instant Upfront Yield) calculated with the formula:
$$
\frac{new\char`_staked\char`_amount * expiration\char`_in\char`_seconds * DPY}{86400 * 365}
$$

## Glossary

### AMM
An automated market maker is a smart contract on Binance Smart Chain that hold on-chain liquidity reserves. Users can trade against these reserves at prices set by an automated market making formula.
### APY
Annual percentage yield is the effective rate of return on an investment for one year.

### DPY
Deka Percentage Yield - the percentage used to calculate the upfront yield reward.

### UPY
Instant Upfront Yield
### BEP20
BEP20 tokens are fungibile tokens on Binance Smart Chain.

###  LP
A liquidity provider is someone who deposits an equivalent value of BEP20 tokens into the liquidity pool within a pair. Liquidity providers take on price risk and are compensated with fees.

### EOA
Externally Owned Account