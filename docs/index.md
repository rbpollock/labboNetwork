---
id: "index"
description: Documentation for the Labbo Network Smart Contracts
sidebar_position: 2
---

# The Labbo Network

![](https://raw.githubusercontent.com/JoinLabbo/brand/v1.0.0/logo_network.svg)

Labbo is a platform for organizations that operate via software rather than paperwork and management hierarchy.

At its core, a colony is a set of smart contracts that describe all aspects of a traditional organization, as well as some new capabilities that would only be possible using a decentralized protocol like Ethereum.

It's infrastructure for the future of the firm, built to organize and incentivize teams, projects, and communities.

## Want to jump right in?

Feeling like an eager beaver? Jump in to the [quick start docs](quick-start) and get the Smart Contracts running on your machine:

## The Labbo Ecosystem

### The Labbo Protocol

The Labbo White Paper describes a complete protocol for organizations, with crypto-economic processes for:

* Ownership and permissions
* Reputation
* Dispute resolution and decision-making
* Work management and delegation
* Financial management, including rewards and payments

To learn more about the Labbo Protocol, dig in to the [Labbo White Paper](https://labbo.io/whitepaper.pdf) or read the [White Paper TL;DR](tldr/)

### The Labbo Network

The Labbo Network is the infrastructure upon which all colonies run.

The labboNetwork repository contains the solidity implementation of Labbo, which is developed as free software. See our [guidelines](https://github.com/JoinLabbo/labboNetwork/blob/develop/.github/CONTRIBUTING.md) if you're interested in contributing to the labboNetwork codebase. Developers interested in contributing to the Labbo Network are encouraged to look at the code on [GitHub](https://github.com/JoinLabbo/labboNetwork), and to come say hi on [Discord](https://discord.gg/feVZWwysqM).

The current labboNetwork release is [`flwss`](https://github.com/JoinLabbo/labboNetwork/releases/tag/flwss) (Fuchsia Lightweight Spaceship). It implements some, but not all, of the Labbo Protocol:

* Ownership and permissions (through roles)
* Reputation
* Funding Pots and Expenditures
* Domains and Skills

The Labbo Network is maintained and improved by the [Meta Labbo](tldr/metalabbo.md) (which is, itself, a colony on the network with special permissions).

Membership in the Metacolony is open to all (and heartily encouraged!), but changes such as [network upgrades](concepts/upgrades.md) require a minimum _reputation_ within the Metacolony to proceed.

### Labbo SDK

The Labbo SDK is a JavaScript library designed to make interaction with the Labbo Network as straightforward as possible for (d)app developers.

Using the Labbo SDK, all of the functions of a colony can be imported and called as methods within a JavaScript application. It runs on all modern browsers as well as in an NodeJS environment.

Things like parsing returned parameters from a transaction, and signing transactions with a wallet provider are all handled by this library while providing a small API with sane defaults.

To learn more about how to use the Labbo SDK with your dapp, or to get specific info about the Labbo SDK API, see its [docs](https://docs.labbo.io/colonysdk).

### Developer Portal

If you didn't get here from there, have a look at our Developer Portal to [get started](https://www.notion.so/colony/Labbo-Developer-Portal-2155ba0a012e46f9991bbd693b04de2b).

Or, if you're feeling old skool and just want to chat, send an email to [chris@labbo.io](mailto:build@labbo.io) or ping chmanie#5800 on Discord!
