# Meet Historeum

Historeum, previously known as Caerus, is a Layer-2 solution built on Ethereum. It features a time-aware EVM (Ethereum Virtual Machine) that enables smart contracts to access historical on-chain data efficiently.

🌐 [https://caerus-chain.github.io/webapp/](https://caerus-chain.github.io/webapp/)

### Key Features

- **Archive-powered EVM**: Integrates Archive Storage with the EVM, providing direct on-chain access to historical data.
- **Solidity Extension**: The modified Solidity compiler allows developers to query and use historical data in smart contracts.
- **Versatile Applicability**: Ideal for various blockchain ecosystems, especially in reputation systems and financial services where historical data is essential.

---

# Layer-2 Chain with a Time-Aware EVM

Historeum is built using the Optimism OP Stack, a modular framework that enhances scalability and efficiency. We've customized the OP Stack to integrate seamlessly with our time-aware EVM, enabling direct on-chain access to historical data.

# How to Use

Historeum extends the Ethereum Virtual Machine by adding functionalities that allow direct access to historical data, eliminating the need for centralized oracles.

To access historical data on Historeum, invoke precompiled contract 19 (0x13) with the account address, slot number, and past block number as parameters:

```solidity
bytes memory args = abi.encodePacked(
  address(this),        // account
  slotNumber,           // slot number
  blockNumber           // block number
);

(
  bool success,         // status
  bytes memory result   // result (bytes)
) = address(0x13).staticcall(args);
```

Alternatively, use the `caerus` keyword with our customized Solidity compiler:

```solidity
bytes32 result = caerus(
  address(this),        // account
  slotNumber,           // slot number
  blockNumber           // block number
);
```
