SimpleStorage — zkSync Era Deployment & Security Review

***DISCLAIMER***
This repository documents my first end-to-end smart contract deployment and security assessment.
The goal of this project was to demonstrate mastery of the full workflow required for modern smart contract engineering:
    •    Environment setup
    •    L1 to L2 testnet bridging
    •    Contract compilation
    •    zkSync Era deployment
    •    Interaction testing
    •    Explorer verification
    •    Security audit writing
    •    Portfolio-grade documentation

This is not intended for production use. The purpose is learning, documentation, and establishing professional workflow patterns.



**1. Project Overview**

This project walks through the lifecycle of a simple storage contract deployed to zkSync Era Sepolia.

Technologies and tools used:
    •    Solidity 0.8.24
    •    Remix IDE + zkSync plugin
    •    MetaMask
    •    zkSync Era bridge
    •    zkSync Sepolia explorer
    •    Manual and static analysis tools (Remix analyzers)

Key goals:
    •    Understand L2 deployment flows
    •    Practice bridging and gas abstraction
    •    Document complete testing steps
    •    Produce a real-world audit report
    •    Build a portfolio-ready repository



**2. Contract Summary**

Contract: SimpleStorage.sol

The contract implements:
    •    uint256 myFavoriteNumber - a single stored value
    •    Person[] listOfPeople - an array of structs
    •    mapping(string => uint256) nameToFavoriteNumber - associative lookup

Public Functions
    •    store(uint256) - updates myFavoriteNumber
    •    retrieve() - returns the stored value
    •    addPerson(string,uint256) - appends to the array and updates the mapping

Purpose: demonstrate basic state modification patterns and mapping usage.



**3. Deployment Details**

Network

zkSync Era Sepolia

Contract Address

0x60bd074d765d57DF84C24AE1cC80B668dD72809f
Explorer:
https://sepolia.explorer.zksync.io/address/0x60bd074d765d57DF84C24AE1cC80B668dD72809f

Deployment Transaction

0x3fa582250727e2beab00d33ab6a92ffb17c5357dff5e984c6db7c8e66766022
Explorer:
https://sepolia.explorer.zksync.io/tx/0x3fa582250727e2beab00d33ab6a92ffb17c5357dff5e984c6db7c8e66766022

Compiler: Solidity 0.8.24
Environment: Remix zkSync Plugin (Remote Devnet → Wallet Mode)



**4. Bridging Workflow (zkSync Era)**

A full L2 workflow was completed to support deployment:
    1.    Bridged ETH from Ethereum Sepolia → zkSync Era Sepolia
    2.    Verified arrival of L2 funds on the zkSync explorer
    3.    Connected MetaMask to zkSync Era Sepolia
    4.    Used the Remix zkSync plugin to compile with zksolc
    5.    Successfully deployed using zkSync plug in on Remix IDE

Purpose: demonstrate understanding of L1 → L2 bridging and zkSync deployment flows.



**5. Interaction Tests**

Performed in Remix after deployment:
    •    store(7) → transaction successful
    •    retrieve() → returned 7
    •    addPerson("Michael", 33) → mapping + array updated correctly

Explorer traces confirm correct state writes.



**6. Screenshots**

All documentation screenshots (bridging, deployment, contract interaction, explorer confirmations) are stored in:

/screenshots/

Recommended filenames:
    •    bridge.png
    •    deploy.png
    •    interaction-store.png
    •    interaction-retrieve.png
    •    explorer-confirmation.png
    •    zkSync-plugin.png



**7. Security Audit**

The full audit report is located at:

/audit/SimpleStorage-Audit.md

Audit includes:
    •    Executive summary
    •    Threat model
    •    Findings 
    •    Recommendations
    •    Methodology
    •    Appendix with on-chain metadata



**8. Next Steps**

This repository is Phase 1 of my security portfolio.
Upcoming additions:

FundMe Contract
    •    More complex storage
    •    Custom errors
    •    Events
    •    Withdraw patterns

Foundry Testing (TDD)
    •    Invariant tests
    •    Fuzzing
    •    Gas snapshots

Security Patterns
    •    Reentrancy protection
    •    Access control
    •    Checks-Effects-Interactions pattern

DeFi Mini-Projects
    •    ERC20 implementation
    •    Dex simulation
    •    DVDeFi (Damn Vulnerable DeFi) challenges

zkSync Smart Contract Series
    •    Paymaster examples
    •    Account abstraction
    •    L1 <-> L2 messaging

This repo establishes the foundation and documentation style I will use across future Web3 security projects.



**9. License**

MIT License 

