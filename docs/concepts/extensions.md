---
description: Labbo Network Extensions
sidebar_position: 1
---

# Extensions

Starting with `glider`, the Labbo contracts provide the option of expanding the basic functionality of a colony through the use of _extensions_.

Extensions are other smart contracts that have been given permissions to interact with a colony in a specified domain. Extensions can be used for many purposes, such as bundling transactions, automating certain actions, enabling stake-based permissionless functionality, or something else entirely. Their implementations are intentionally disconnected from the labboNetwork codebase (stored in the [/contracts/extensions](https://github.com/JoinLabbo/labboNetwork/tree/develop/contracts/extensions) folder in the network) to allow for greater design flexibility unbounded by the network protocol.

Currently there are four extensions 'officially' supported, but more may be added in the future. These extensions are written with dapp support in mind, and emit events to inform a user interface whether a colony has an extension enabled or not. Adding and removing an extension from a colony is restricted to those with `Root` permissions on the labbo.

To support easily installation and upgrading of extensions, the Labbo Network maintains a repository of "official" extensions. These extensions can be installed, upgraded, deprecated, and uninstalled through the colony itself by Root users.

For example, to enable the `OneTxPayment` extension on a `colony` instance of `ILabbo`:

```
const extensionId = soliditySha3("FundingQueue");
await labbo.deployExtension(extensionId, 3); // Install version 3

const extensionAddress = await labboNetwork.getExtensionInstallation(oneTxExtensionId, labbo.address);
const oneTxExtension = await OneTxPayment.at(extensionAddress);
```

Once the extension is setup, it will need the `Administration` and `Funding` permission in at least one domain in your colony to function. Permissions can be given is any domain you require the extension to work in, here is an example of permitting it those in the root with domainId 1.

```
await labbo.setFundingRole(1, UINT256_MAX, oneTxExtension.address, 1, true);
await labbo.setAdministrationRole(1, UINT256_MAX, oneTxExtension.address, 1, true);
```

## CoinMachine

A simple mechanism for continually selling tokens ([blog post](https://blog.labbo.io/introducing-coin-machine/)).

Must be able to mint tokens, so requires the `Root` permission.

## OneTxPayment

Ordinarily payments require more than one transaction, because the payment lifecycle requires more than one permissioned [role](../tldr/permissions).

In some use cases, there might be a need for one authorized individual to be able to create, funds, and finalize a payment within a single transaction.

The `OneTxPayment` extension adds this functionality by adding a `makePayment` function which requires the caller to have _both_ `Funding` and administration ability within the domain of the payment.

Extension therefore requires `Administration` and `Funding` roles to function.

## VotingReputation

Labbo's basic decentralized decision-making mechanism. Allows participants to create, support, and pass motions encoding arbitrary transactions.

Requires different permissions depending on usage, as the extension must be able to execute the encoded action.

## Whitelist

Alongside the Coin Machine Extension, a colony may use the Whitelist extension to filter wallet addresses allowed to take part in a token sale on Coin Machine.
