**What is a stablecoin?**

**Why won't central banks issue their own stablecoin?**

Answering this question requires some macro economics. If a central bank issues its own stablecoin, it will either represent a large economy (e.g. the US or the EU) or a small economy (e.g. Singapore). If a small economy's central bank issues its own stablecoin, the market capitalization for that currency (i.e. the value of tokens in circulation) cannot be too large relative to the size of the country's economy. Suppose Singapore issues a stablecoin pegged to the Singapore dollar (SGD) accessible on Ethereum or some other public blockchain. If the stablecoin attracts demand from outside the country, then the value of the SGD will increase. Perhaps a little bit of currency appreciation won't harm the Singaporean economy, but too much would be quite destabilizing. Indeed, if demand for crypto SGD were to dissipate, then the value of their currency would likewise decrease. Thus, a small economy like Singapore would be unable to issue a stablecoin of their own, or at least this stablecoin cannot be widely used outside of Singapore without taking large macro-economic risks.

But a large economy like the US does not face these limitations. The USD is already the global reserve currency so a large USD stablecoin market cap will not materially affect the domestic macro economics. So in principle there is no economic reason why the Federal Reserve could not directly issue USD stablecoins. However, issuing USD directly on a public blockchain would undermine the existing monetary system. Banks rely on customers holding deposits in their branches. If customers can bank directly with the Fed, then banks will no longer have a business model. This is why no one other than banks can have an account with the Federal Reserve. Because banks are arguably the most important stakeholders in the banking system of every large economy, it is highly unlikely that central banks will issue their own stablecoins. Much more likely is that private banks will issue their own USD-backed stablecoins, and continue the banking model that has existed since the advent of paper currency in Europe.

**What is Cowri?**

Cowri is a stablecoin interoperability protocol. What that means is that we...

**What kind of use cases can Cowri fulfill?**

Cowri can be used in the same way as any individual stablecoin.

**Does Cowri have a token?**

No, Cowri does have its own token. Rather than force users to deal with a token they don't want, we help them manage their stablecoins. In fact, not only does Cowri not issue a token, we also never hold users' money. Instead, at all times, users of the Cowri protocol are in control of their own tokens. Under the hood, at the blockchain layer, users' stablecoins remain unchanged.

**How does Cowri work?**

**What happens to Cowri if a stablecoin becomes insolvent?**

Although far less risky than cryptocurrencies such as Bitcoin, stablecoins nonetheless are not without risks of their own.  Although the stablecoin's price may temporarily go up or down, if properly designed the stablecoin will eventually return to its targeted peg, typically 1 stablecoin = 1 USD. Thus, the main risk associated with stablecoins is not price volatility per se (like it is with Bitcoin), but that the stablecoin may become insolvent. I.e., the stablecoin loses all value and is worthless. After all, why would anyone hold a stablecoin that is unable to maintain its peg?

What happens to Cowri if a widely used stablecoin becomes insolvent? Let's break this question into two parts: (1) what happens to individual users and (2) what happens to the protocol?

For (1), the effect on individual users will depend on whether a user has exposure to the insolvent stablecoin. If a user does not have that stablecoin in their shell, then they will be unaffected. If a user has the insolvent coin in their shell, then it will depend on how much of their total cowri balance is constituted by that stablecoin. It is possible for some users to have hardly any of their balance in the insolvent stablecoin. It is also possible for some users to have a large balance in that coin. It will depend on the user. This is why it is important for users to only use stablecoins they are comfortable with. In any case, whatever the risk posed to users, they are probably better off using cowri than any specific stablecoin since they balance will be more diversified.

In terms of (2), the underlying protocol will be unaffected. Essentially, the Cowri protocol is a messaging and coordination service between users' and stablecoin liquidity providers. This infrastructure is designed to work regardless of financial shocks.

**What is a Cowri "shell"?**

**How does Cowri compare to a meta-stablecoin?**

**How do I send cowri?**

Sending cowri is easy. All you need to know is: the Ethereum address of the intended recipient, and the amount you want to send. The act of sending cowri usually takes just one step, just like sending any other token on Ethereum. Occasionally, there may be a second step, if you are sending cowri to a recipient who only accepts stablecoins you do not currently have in your wallet. Even with the second step, the sending cowri should take less than 1 minute in most cases.

**How much does it cost to send cowri?**

In most cases, the transaction costs will be less than $0.15, the typical price of sending an ERC-20 token on Ethereum. Like any process that requires writing data to a blockchain, sending cowri requires a user to [pay gas fees.](https://education.district0x.io/general-topics/understanding-ethereum/what-is-gas/) The exact gas fees to send cowri depend on a couple of factors. First, it depends on whether the user must first swap some of their current stablecoins for stablecoins accepted by the recipient. Doing so will add gas fees. Second, the cost of sending cowri will depend on how many individual stablecoins a user sends in order to make the full transaction amount. For every different stablecoin sent, the cost increases. Our algorithm has been designed to reduce gas fees by making as few swaps and sending as few stablecoins as possible.

**I'm a user, how can I get access to Cowri?**

**I'm a developer, how can I integrate Cowri's protocol into my project?**

**How do I tell a friend about Cowri?**