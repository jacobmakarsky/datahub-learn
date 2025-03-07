# Introduction

I invite you to join me In this tutorial series and learn how to design, build, and monetize smart contracts on the NEAR platform. Learning is fun, applying what you learn to build is more fun, and making money from what you have built is rewarding. I believe in the philosophy of the "proof is in the pudding". In this tutorial series, we will be building a real-world smart contract called the [STAKE](https://github.com/oysterpack/oysterpack-near-stake-token) token. The goals for this tutorial series are:

1. Showcase the [STAKE](https://github.com/oysterpack/oysterpack-near-stake-token) token project on how to monetize NEAR smart contracts
2. Share with you my approach to architect, design, and code smart contracts in Rust
3. Take you step by step through designing, coding, and testing on the [STAKE](https://github.com/oysterpack/oysterpack-near-stake-token) 

   token project.

4. Share with you design patterns and best practices I have learned while working on the STAKE token project
5. Make this a collaborative experience with the community

Regarding the last point, I welcome community participation in the [STAKE](https://github.com/oysterpack/oysterpack-near-stake-token) open source project.

# NEAR Technology + Economics = Game Changer

When I first discovered NEAR, what caught my attention was NEAR's economic model. It is well thought out and designed to provide economic incentive and value. Coupling that with NEAR's sharded scalability, speed, and low predictable operational cost provides a platform that can deliver real-world business and economic value. NEAR has the potential and all the key ingredients to becoming the first true economical decentralized cloud platform - to compete with centralized cloud platforms owned by a few big tech companies ...

# You can have your STAKE and trade it too

The STAKE token contract enables you to delegate your NEAR to stake, and in return, you are issued STAKE tokens. This enables you to trade your STAKE tokens while your NEAR is locked for staking and earning staking rewards. In addition, to earning staking rewards, the staked NEAR earns contract rewards from transaction fees. The STAKE token transforms your staked NEAR into a tradeable asset that is backed by revenue streams.

The STAKE token business model leverages the following from NEAR:

1. [Staking pool delegation](https://docs.near.org/docs/validator/delegation#staking-pool-delegation)
   * Anyone holding NEAR tokens can earn staking rewards by [delegating](https://docs.near.org/docs/validator/staking-overview#for-delegators) their tokens to staking pools
2. [Staking pool](https://github.com/near/core-contracts/tree/master/staking-pool) core contract
   * STAKE token contract integrates with [staking pool](https://github.com/near/core-contracts/tree/master/staking-pool) contracts for staking NEAR
3. Contract rewards
   * NEAR provides out of the box the ability to collect a portion of transaction fees and distributes them to the contracts that were run as part of the transaction
   * STAKE token contract distributes a share of its contract rewards through staking
   * STAKE token contract is also able to collect earnings from external contracts and distribute the funds through the staking mechanism

# STAKE Token Contract High-Level Overview

![](../../../../.gitbook/assets/oysterpack-near-stake-token-overview-1-.png)

* Users must register with the contract in order to use it. When registering, users are required to pay an upfront account storage fee to cover storage staking costs. On NEAR long term storage is not free. The account storage fee is escrowed and will be refunded back to the user when the account unregisters.
* Contract is linked to a single staking pool contract, i.e., STAKE token contract is deployed per staking pool contract.
* Contract will implement the new fungible token standard defined by [NEP-141](https://github.com/near/NEPs/discussions/146)
* Contract has concept of contract ownership.
* Contract supports an operator role that is managed by the contract owner.
* Contract supports distributing contract rewards and earnings through the staking mechanism.
* Contract supports adding liquidity for unstaking and withdrawals

## What you will learn from the STAKE Token project from a technical perspective

The STAKE token project is fairly complex and showcases the following

1. Applying interface-driven design and domain modeling 
   * Leveraging Rust strong type system and compiler 
2. Cross-contract workflows
   * High level and low-level approaches
   * Making use of batch transactions
   * Gas considerations
3. State management
   * Storage staking considerations
4. Financial computation considerations
   * Protecting against overflows
5. New fungible token standard - [NEP-141](https://github.com/near/NEPs/discussions/146)
6. Unit testing
7. Simulation testing
8. Contract deployment
9. ... And the learning never ends

## The World Is Your Oyster

Decentralized network platforms, such as NEAR, provide tremendous economic opportunity. To put it into perspective, Amazon's market capitalization is currently valued at 1.56 trillion USD and 2021 revenue estimates are in the 411 - 488 billion USD range. That is just scratching the service. How much do you think the global economy is worth? Decentralized and scalable global cloud platforms such as NEAR provides an opportunity for all to participate in the global economy.

# Conclusion

NEAR is a super-fast smart contract platform with super low transaction fees that is user and developer-friendly for building real-world applications for the Open Web. I am excited about NEAR, and I hope I have inspired you to learn with me on this thrilling journey.

# Next Steps

If you are wondering what is NEP-41, then you are in luck. In the next tutorial, we'll do a deep dive into the new and improved Fungible Token Core Standard NEP-141.

