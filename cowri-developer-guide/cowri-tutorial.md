# Cowri Crab Corner Tutorial

[**Follow this Tutorial**](https://www.trufflesuite.com/tutorials/pet-shop)

[**Solutions can be found here**](https://github.com/trufflesuite/pet-shop-tutorial)

\*\*[Tutorial Markdown Documentation can be found here](https://github.com/trufflesuite/trufflesuite.com/blob/master/src/tutorials/pet-shop.md)

This tutorial will take you through the process of building your first dapp---a payment protocol integrated into Cowri Crab Corner!

This tutorial is meant for those with a basic knowledge of Ethereum and smart contracts, who have some knowledge of HTML and JavaScript, but who are new to dapps.

 **Note**: For Ethereum basics, please read the Truffle \[Ethereum Overview\]\(/tutorials/ethereum-overview\) tutorial before proceeding.

In this tutorial we will be covering:

1. Setting up the development environment
2. Creating a Truffle project using a Truffle Box
3. Adding Send Cowri to your Application
4. Interacting with the dapp in a browser

## Background

Triton of Cowri Crab Corner is interested in using Cowri as an efficient way to handle their hermit crab donations. As an initial proof of concept, **Triton wants to see a dapp, which associates a cowri shell with a hermit crab to receive donations.**

The website structure and styling will be supplied. **Our job is to integrate with the cowri protocol and front-end logic for its usage.**

## Setting up the development environment

There are a few technical requirements before we start. Please install the following:

* [Node.js v8+ LTS and npm](https://nodejs.org/en/) \(comes with Node\)
* [Git](https://git-scm.com/)

Once we have those installed, we only need one command to install Truffle:

```text
npm install -g truffle
```

To verify that Truffle is installed properly, type `truffle version` on a terminal. If you see an error, make sure that your npm modules are added to your path.

We also will be using [Ganache](https://github.com/cowri/cowri-docs/tree/04d9b6dec5ee45ed731242763b10787dc6964125/ganache/README.md), a personal blockchain for Ethereum development you can use to deploy contracts, develop applications, and run tests. You can download Ganache by navigating to [http://truffleframework.com/ganache](http://truffleframework.com/ganache) and clicking the "Download" button.

 **Note**: If you are developing in an environment without a graphical interface, you can also use Truffle Develop, Truffle's built-in personal blockchain, instead of Ganache. You will need to change some settings---such as the port the blockchain runs on---to adapt the tutorial for Truffle Develop.

## Creating a Truffle project using a Truffle Box

1. Truffle initializes in the current directory, so first create a directory in your development folder of choice and then moving inside it.

   ```text
   mkdir cowri-crab-corner-tutorial

   cd cowri-crab-corner-tutorial
   ```

2. We've created a special [Truffle Box](https://github.com/cowri/cowri-docs/tree/04d9b6dec5ee45ed731242763b10787dc6964125/boxes/README.md) just for this tutorial called `cowri-crab-corner`, which includes the basic project structure as well as code for the user interface. Use the `truffle unbox` command to unpack this Truffle Box.

   ```text
   truffle unbox cowri-crab-corner
   ```

 **Note**: Truffle can be initialized a few different ways. Another useful initialization command is \`truffle init\`, which creates an empty Truffle project with no example contracts included. For more information, please see the documentation on \[Creating a project\]\(/docs/getting\_started/project\).

### Directory structure

The default Truffle directory structure contains the following:

* `contracts/`: Contains the [Solidity](https://solidity.readthedocs.io/) source files for our smart contracts. There is an important contract in here called `Migrations.sol`, which we'll talk about later.
* `migrations/`: Truffle uses a migration system to handle smart contract deployments. A migration is an additional special smart contract that keeps track of changes.
* `truffle-config.js`: Truffle configuration file \(windows users\)
* `truffle.js`: Truffle configuration file 

The `cowri-crab-coner` Truffle Box has extra files and folders in it, but we won't worry about those just yet.

### Instantiating web3

1. Open `client/src/App.js` in a text editor.
2. Examine the file. Note that there is a global `App` object to manage our application, load in the pet data in `init()` and then call the function `initWeb3()`. The [web3 JavaScript library](https://github.com/ethereum/web3.js/) interacts with the Ethereum blockchain. It can retrieve user accounts, send transactions, interact with smart contracts, and more.
3. Remove the multi-line comment from within `initWeb3` and replace it with the following:

   ```javascript
   // Modern dapp browsers...
   if (window.ethereum) {
     App.web3Provider = window.ethereum;
     try {
       // Request account access
       await window.ethereum.enable();
     } catch (error) {
       // User denied account access...
       console.error("User denied account access")
     }
   }
   // Legacy dapp browsers...
   else if (window.web3) {
     App.web3Provider = window.web3.currentProvider;
   }
   // If no injected web3 instance is detected, fall back to Ganache
   else {
     App.web3Provider = new Web3.providers.HttpProvider('http://localhost:7545');
   }
   web3 = new Web3(App.web3Provider);
   ```

Things to notice:

* First, we check if we are using modern dapp browsers or the more recent versions of [MetaMask](https://github.com/MetaMask) where an `ethereum` provider is injected into the `window` object. If so, we use it to create our web3 object, but we also need to explicitly request access to the accounts with `ethereum.enable()`.
* If the `ethereum` object does not exist, we then check for an injected `web3` instance. If it exists, this indicates that we are using an older dapp browser \(like [Mist](https://github.com/ethereum/mist) or an older version of MetaMask\). If so, we get its provider and use it to create our web3 object.
* If no injected web3 instance is present, we create our web3 object based on our local provider. \(This fallback is fine for development environments, but insecure and not suitable for production.\)

### Integrating Send Cowri \(React\)

Now that we can interact with Ethereum via web3, we need to use our Send Cowri component. We can either pass in an instance of web3 or use the one built into Send Cowri.

Send Cowri react component takes the following _optional_ properties:

| Name | Type | Description |
| :--- | :--- | :--- |
| address | `string` | the receiver's public address |
| amount | `number` | the amount of cowri to send |
| web3 | `Web3` | instance of web3 |

1. Install and save `@cowri/send-react`:

   ```bash
   npm install @cowri/send-react --save
   ```

2. In _src/components/CardBody/CardBody.js_ add the following import at the top of the file:

   ```javascript
   import SendCowri from '@cowri/send-react';
   ```

3. Remove the following line:

   ```javascript
   <Button text={'Donate} />
   ```

4. Add SendCowri component and pass in `address` from props:

   ```javascript
   <SendCowri address={address} />
   ```

### Getting The Adopted Pets and Updating The UI

### Handling the adopt\(\) Function

## Interacting with the dapp in a browser

Now we're ready to use our dapp!

### Installing and configuring MetaMask

The easiest way to interact with our dapp in a browser is through [MetaMask](https://metamask.io/), a browser extension for both Chrome and Firefox.

1. Install MetaMask in your browser.
2. Once installed, a tab in your browser should open displaying the following:

   ![Welcome to MetaMask](../.gitbook/assets/metamask-welcome.png)

3. After clicking **Getting Started**, you should see the initial MetaMask screen. Click **Import Wallet**.

   ![MetaMask initial screen](../.gitbook/assets/metamask-initial.png)

4. Next, you should see a screen requesting anonymous analytics. Choose to decline or agree.

   ![Improve MetaMask](../.gitbook/assets/metamask-analytics.png)

5. In the box marked **Wallet Seed**, enter the mnemonic that is displayed in Ganache.

    \*\*Warning\*\*: Do not use this mnemonic on the main Ethereum network \(mainnet\). If you send ETH to any account generated from this mnemonic, you will lose it all!

   Enter a password below that and click **OK**.

   ![MetaMask seed phrase](../.gitbook/assets/metamask-seed.png)

6. If all goes well, MetaMask should display the following screen. Click **All Done**.

   ![Congratulations](../.gitbook/assets/metamask-congratulations.png)

7. Now we need to connect MetaMask to the blockchain created by Ganache. Click the menu that shows "Main Network" and select **Custom RPC**.

   ![MetaMask network menu](../.gitbook/assets/metamask-networkmenu.png)

8. In the box titled "New Network" enter `http://127.0.0.1:7545` and click **Save**.

   ![MetaMask Custom RPC](../.gitbook/assets/metamask-customrpc.png)

   The network name at the top will switch to say `http://127.0.0.1:7545`.

9. Click the top-right X to close out of Settings and return to the Accounts page.

   Each account created by Ganache is given 100 ether. You'll notice it's slightly less on the first account because some gas was used when the contract itself was deployed and when the tests were run.

   ![MetaMask account configured](../.gitbook/assets/metamask-account1.png)

   Configuration is now complete.

### Using the dapp

1. Start the local web server:

   ```text
   npm run dev
   ```

   The dev server will launch and automatically open a new browser tab containing your dapp.

   !\[Pete's Pet Shop\]\(../img/pet-shop/dapp.png "Pete's Pet Shop"\)

2. A MetaMask pop-up should appear requesting your approval to allow Pete's Pet Shop to connect to your MetaMask wallet. Without explicit approval, you will be unable to interact with the dapp. Click **Connect**.

   ![MetaMask approval request](../.gitbook/assets/metamask-transactionconfirm.png)

3. To use the dapp, click the **Adopt** button on the pet of your choice.
4. You'll be automatically prompted to approve the transaction by MetaMask. Click **Submit** to approve the transaction.

   ![Adoption transaction review](../.gitbook/assets/metamask-transactionconfirm%20%281%29.png)

5. You'll see the button next to the adopted pet change to say "Success" and become disabled, just as we specified, because the pet has now been adopted.

   ![Adoption success](../.gitbook/assets/dapp-success.png)

    **Note**: If the button doesn't automatically change to say "Success", refreshing the app in the browser should trigger it.

   And in MetaMask, you'll see the transaction listed:

   ![MetaMask transaction](../.gitbook/assets/metamask-transactionsuccess.png)

   You'll also see the same transaction listed in Ganache under the "Transactions" section.

Congratulations! You have taken a huge step to becoming a full-fledged dapp developer. For developing locally, you have all the tools you need to start making more advanced dapps. If you'd like to make your dapp live for others to use, stay tuned for our future tutorial on deploying to the Ropsten testnet.

