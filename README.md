### Cowri Introduction

The goal of this project is to create Internet Money by building a stable and liquid medium of exchange accessible to anyone. This medium of exchange will be a decentralized protocol that unifies stablecoins (i.e. cryptocurrency pegged to a stable asset, usually USD) into a coherent monetary system. The Cowri Shell Protocol will not issue any tokens of its own and does not take custody of users' assets. 

The problem with stablecoins is that they are highly fragmented - there are five major stablecoins in circulation along with hundreds of minor currencies. This fragmentation creates problems in three areas:

   (1) Bad end-user experience
   (2) Prohibitively complicated for developers to integrate stablecoins payments into their projects
   (3) Exacerbates fragility of decentralized finance (DeFi) protocols

In a multi-stablecoin ecosystem, managing stablecoin wallets will be prohibitively complicated for end-users. For example, imagine buying coffee and having to first argue with the shop over which of the two hundred stablecoins to use? This problem is even worse for developers who want to integrate stablecoin payments into their projects. Every user will have their own preferences on which stablecoins to use. The more users on the platform, the worse the complexity gets for developers. 

DeFi protocols will also benefit from a unified stablecoin market. It will be much more difficult to trade cryptocurrencies and build sophisticated financial infrastructure if protocols must divide liquidity between many different stablecoins. Additionally, fragmentation causes protocols to rely on only a handful of stablecoins, which makes the system more fragile. If there are many stablecoins in the ecosystem, a broken stablecoin peg is less likely to be an existential threat.

Cowri solves these problems by:

   (1) Providing a seamless and intuitive user experience when sending multiple stablecoins
   (2) Giving dapp developers simple tools to integrate a stablecoin agnostic payment system
   (3) Creating stablecoin-optimized liquidity pool along with the ability to atomically swap and send stablecoins

Cowri is still in development. Currently, the protocol has built components (1) and (2). Component (3) is in progress. To see (1), you can check out our user-facing [demo](https://demo.cowri.io) and [tutorial](https://docs.cowri.io/cowri-user-guide/1-user-tutorial). For (2), we have created a developer [guide](insert url) and [tutorial](insert url). It walks you through how to build projects with Cowri and gives a more detailed description of how the Developer SDK works.

Half-way through development of (3), we learned that our original approach, which used the 0x Protocol to execute stablecoin swaps, had unanticipated draw backs. Namely:

   (1) Swaps and sends could not occur atomically in a single transaction
   (2) Automated price discovery for swaps required significant off-chain coordination between users and liquidity providers

The lack of atomicity allowed for errors to happen mid-way through a transaction, which had no easy remedy. Even without errors, some transactions would require many confirmations, which resulted in a poor user experience. Requiring off-chain coordination between user and liquidity provider makes DeFi integration prohibitive.

Thus, we are working on an updated version of the protocol to address these two problems. Among other changes, we redesigned the the stablecoin swaps to use an on-chain liquidity pool, similar in some ways to Uniswap, rather than an off-chain 0x model. If you would like to learn more about the differences between the old and new versions of the protocol, see the section on [Cowri architecture](https://docs.cowri.io/cowri-overview/architecture).
