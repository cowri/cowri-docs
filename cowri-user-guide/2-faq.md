# Frequently Asked Questions

### **What is Cowri?**

Cowri's goal is to create Internet Money by building a stable and liquid medium of exchange accessible to anyone. The building blocks for this medium of exchange are stablecoins. Individually, a stablecoin is limited. But if they work in unison, they become quite powerful. The Cowri Shell Protocol unifies an arbitrary number of stablecoins into a coherent monetary system.

Cowri lets users interact with multiple stablecoins as if they were using a single currency. The Cowri Shell Protocol is based on a set of logical procedures that ensure users always receive a stablecoin they are willing to accept. Users of the protocol need not agree on which stablecoins to hold. You could say that Cowri is a "stablecoin interoperability protocol."

### **What problem does Cowri solve?**

Cowri reduces stablecoin fragmentation. In order for Internet Money to become a reality, we need a stable and liquid medium of exchange existing natively on a permissionless ledger \(i.e. a public blockchain\). Stablecoins per se cannot fulfill that role because the market is just too fragmented. Imagine buying coffee and having to first argue with the shop over which of the two hundred stablecoins to use? Managing even a handful of different stablecoin balances will be prohibitive for users.

Additionally, a fragmented stablecoin market makes decentralized finance \(DeFi\) more fragile. Stablecoins are intrinsic to the working of many DeFi protocols and are at the heart of the ecosystem. Because these protocols rely on stablecoins, and these protocols rely on each other, the entire house of cards could collapse if only one of the stablecoins loses its peg. E.g., DeFi protocol 1 relies on DeFi protocol 2 which in turn relies on DeFi protocol 3 which relies on a Stablecoin A. If that one stablecoin loses its peg, all three protocols are at risk. This same logic can apply to any business who wants to rely on stablecoin payments.

### **What value does Cowri offer to the crypto ecosystem?**

Cowri mitigates the costs of stablecoin fragmentation for end-users, developers and other DeFi protocols. For end-users, Cowri provides a simple and intuitive way to send, receive and hold stablecoins. The complexity of managing individual balances is abstracted away.

For developers, Cowri allows them to build stablecoin agnostic projects. With Cowri, a developer does not have to make decisions as to which stablecoins to support, nor do they have to build the infrastructure to support multiple stablecoins.

DeFi protocols can directly tap into Cowri's on-chain infrastructure. The Cowri liquidity pool allows for efficient stablecoin-to-stablecoin swaps, without the need for an intermediate asset. Additionally, any number of stablecoin swaps or sends can be batched into a single, atomic transaction. With this infrastructure, DeFi protocols can compose stablecoin transactions of arbitrary complexity.

### **What kind of use cases can Cowri fulfill?**

Cowri can be used in the same way as any individual stablecoin. Three primary use cases come to mind: peer-to-peer payments, internet commerce and settlement in DeFi protocols. Our [demo](https://demo.cowri.io) and [tutorial](1-user-tutorial.md) shows how Cowri and stablecoins can work to facilitate P2P payments.

The most promising form of internet commerce for cryptocurrency is online gaming, namely buying and selling video game items, which is already worth $50 billion and is growing rapidly. It makes sense that digital items will be represented as non-fungible tokens \(NFTs\), and will be traded on decentralized market places. Stablecoins will be the medium of choice for payments in video games.

DeFi protocols already hold $500 million in assets on Ethereum. This technology, although barely two years old, is the future of finance. Just as fiat currency is at the heart of modern financial markets, stablecoins will be at the heart of DeFi. The ecosystem needs a unified stablecoin market to reduce settlement costs and increase financial resilience.

### **How does Cowri work?**

The best way to learn about how Cowri works is to read our **white paper**. Our [protocol overview](../cowri-overview/protocol-description.md) is also a good resource. In short, the Cowri Shell Protocol has three main components: shell ledger, shell manager and liquidity pool. The shell ledger tracks which stablecoins users will accept. The shell manager contains the logic necessary to ensure users always send and receive the correct stablecoins. And the liquidity pool facilitates swaps between stablecoins when necessary.

### **What is a Cowri "shell"?**

A Cowri "shell" is a list of stablecoins a user is willing to accept. This concept is at the heart of the protocol. When running the Cowri Shell Protocol, users do not need to micromanage their individual stablecoins when sending or receiving. The correct stablecoins will be sent to recipients, even if the sender and receiver do not have the same shell, i.e. they prefer to use different stablecoins. We built a front end [demo application](https://demo.cowri.io) to showcase how users can set up their shell and send cowri.

### **How do I send cowri?**

Sending cowri is easy. All you need to know is the Ethereum address of the intended recipient, and the amount you want to send. The act of sending cowri usually takes just one step, just like sending any other token on Ethereum. Occasionally, there may be a second step, if you are sending cowri to a recipient who only accepts stablecoins you do not currently have in your wallet. 

### **How much does it cost to send cowri?**

In most cases, the transaction costs will be less than $0.03, the typical price of sending an ERC-20 token on Ethereum. Like any process that requires writing data to a blockchain, sending cowri requires a user to [pay gas fees.](https://education.district0x.io/general-topics/understanding-ethereum/what-is-gas/) The exact gas fees to send cowri depend on a couple of factors. First, it depends on whether the user must first swap some of their current stablecoins for stablecoins accepted by the recipient. Doing so will add gas fees. Second, the cost of sending cowri will depend on how many individual stablecoins a user sends in order to make the full transaction amount. For every different stablecoin sent, the cost increases. Our algorithm has been designed to reduce gas fees by making as few swaps and sending as few stablecoins as possible.

### **Cowri vs. cowri**

The distinction is similar to Bitcoin vs. bitcoin, where Bitcoin is the protocol and bitcoin is the currency. In our case, Cowri with an uppercase "C" refers to the protocol and cowri with a lowercase "c" refers to the money transferred via the protocol. E.g., you can use Cowri to send $100 of cowri to your friend.

### Cowry vs. Cowri

Cowry shells were the earliest known form of money in human history. Archeological evidence can be found across the ancient world from Africa, to Mesopotamia, India and even China. Indeed, the modern Chinese character, 貝 \("bei"\), was [originally a pictogram of a cowry shell.](https://en.wiktionary.org/w/index.php?title=%E8%B2%9D&oldid=53661334) To this day, it has two meanings: "money" and "shell." We chose our name, Cowri, after the cowry shell because it reminds us that even though the form of money continually changes, the function of money is constant.

### **Does Cowri have a native token?**

No. Cowri does not have a native nor does it take custody of users' assets. The on-chain components of our open source protocol run on smart contracts. The off-chain component can run locally on users' devices.

### **What is a stablecoin?**

A stablecoin is a cryptocurrency whose value is pegged to a stable reference asset, typically USD. There are five main stablecoins in circulation, at the moment: Tether, USD Coin, TrueUSD, Paxos and Dai. USD Coin, TrueUSD and Paxos are backed by fiat deposits held in custodial bank accounts. Dai is backed by ether locked up in a smart contract. Cowri does not support Tether because the current version of the protocol only works for ERC-20 tokens. Beyond these five stablecoins, there are hundreds of additional stablecoin projects.

### **Why won't central banks issue their own stablecoin?**

A better question to ask is why do people have to hold deposits in retail banks instead of central banks, and will the rise of stablecoins change this calculus? The short answer to the latter question: no. Central banks are run by technocrats and are not disposed to deal directly with customers. Thus, they prefer to implement monetary policy by managing the underlying banking system. Private enterprise is expected to offer customer-facing services.

If a central bank issued their own stablecoin, they would expose themselves directly to customers. It would also require bureaucrats to become smart contract developers. It is unlikely central banks will be proactive in making such a transition. More likely, central banks will require stablecoin issuers to store their fiat deposits at the central bank, much like they do in the current banking system. That way, the central bank can retain control of the underlying monetary system and delegate customer-facing roles to the private sector.

### **What happens to Cowri if a stablecoin permanently loses its peg?**

Stablecoins are not without risk and it is possible a token could completely lose its peg and be worth $0. That is why a user must think very carefully about which stablecoins they want in their shell. Do not accept a stablecoin unless you are confident it will retain value over time. However, if a stablecoin in your shell does permanently lose its peg, your losses will be capped at the amount of that stablecoin held in your wallet.

In terms of the overall protocol, the main risk is to the stablecoin liquidity pool. In the event of a broken peg, third party traders may try to swap the broken stablecoin for the other coins available in the pool. This would drain the liquidity pool of its capital. To prevent this, there will be safety measures in place that can stop trading for certain stablecoins, or even temporarily halt trading altogether. We will provide more specific information regarding these precautions as we get closer to a main net release.

As the protocol grows, the need to mitigate the effects of a broken stablecoin will only increase. This problem is by no means unique to Cowri and has been a perennial shortcoming of any financial system. The apparent solution is for there to be a buyer of last resort, an institution with the means and mandate to provide liquidity when there is a systemic threat to the system. A big area of future work for Cowri is designing such a system that can provide some measure of insurance for users and liquidity providers in the event of a broken stablecoin.

### **How does Cowri compare to a meta-stablecoin?**

A "meta-stablecoin" is a crypto token that is backed by a reserve of other stablecoins held in a smart contract. The smart contract has a set of rules and procedures for how stablecoins can be redeemed and how new meta-stablecoins can be issued.

Unlike meta-stablecoins, Cowri does not issue a secondary token. Instead, Cowri is a protocol to help unify many different stablecoins into a common system. People need not even agree on what stablecoins to use.

In contrast, meta-stablecoins increase market fragmentation. Suppose there are three stablecoins in circulation: Stablecoin A, Stablecoin B and Stablecoin C. A developer builds a meta-stablecoin, Stablecoin D out of tokens A, B and C. Now there are four stablecoins, whereas previously there were only three. But with the Cowri Shell Protocol, all four stablecoins can seamlessly interoperate.

### **I'm a user, how can I get access to Cowri?**

For now, Cowri is just on Kovan, an Ethereum test net. You can see our user-facing demo [here.](https://demo.cowri.io) We also have a [Cowri faucet](../cowri-developer-guide/developerguide.md#cowri-utilities) available on Kovan.

### **I'm a developer, how can I integrate Cowri's protocol into my project?**

We want Cowri to be as easy as possible to integrate into your project. To that end, we have built [an SDK](../cowri-developer-guide/developerguide.md) for easy integration into React applications. We also have a [tutorial for developers.](../cowri-developer-guide/cowri-tutorial.md) Right now, we are deployed on Kovan, an Ethereum test net.

