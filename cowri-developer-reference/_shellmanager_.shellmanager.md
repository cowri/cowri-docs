# Cowri DApp SDK

## Hierarchy

**ShellManager**

## Constructors

### constructor <a id="constructor"></a>

⊕ **new ShellManager**\(platform: _`any`_\): [ShellManager](_shellmanager_.shellmanager.md)

_Defined in_ [_ShellManager.ts:9_](https://github.com/cowri/cowri-sdk/blob/a1e664e/cowri-dapp-sdk/src/ShellManager.ts#L9)

**High Level Logic Overview** Instantiation of the Shell Manager object is done by passing a platform object into the constructor. For example, if using a Web3 platform, pass the Web3 object into this constructor.

**Function Signature:**

```typescript
  constructor(platform: any)
```

**Basic usage example:**

```typescript
 let shellManager = new ShellManager(this.window.web3);
```

**Parameters:**

| Name | Type |
| :--- | :--- |
| platform | `any` |

**Returns:** [ShellManager](_shellmanager_.shellmanager.md)

## Methods

### getCurrentUser <a id="getcurrentuser"></a>

▸ **getCurrentUser**\(\): `Promise`&lt;`User`&gt;

_Defined in_ [_ShellManager.ts:57_](https://github.com/cowri/cowri-sdk/blob/a1e664e/cowri-dapp-sdk/src/ShellManager.ts#L57)

**High Level Logic Overview** `getCurrentUser` returns a User object of the currently logged in user. This object includes the user's address, the tokens currently in the user's shell, and all balances and other metadata of each token.

**getCurrentUser** is called with the following options

**Returns:** `Promise`&lt;`User`&gt; a User object

**Function Signature:**

```typescript
  public getCurrentUser(): Promise<User>
```

**Basic usage example:**

```typescript
 user = await shellManager.getCurrentUser();
```

### getMaxShellSize <a id="getmaxshellsize"></a>

▸ **getMaxShellSize**\(\): `Promise`&lt;`number`&gt;

_Defined in_ [_ShellManager.ts:133_](https://github.com/cowri/cowri-sdk/blob/a1e664e/cowri-dapp-sdk/src/ShellManager.ts#L133)

**High Level Logic Overview** getMaxShellSize get's the sytem wide maximum number of stable coins a user can have in their shell.

**getMaxShellSize** takes no input parameters

**Returns:** `Promise`&lt;`number`&gt; the maximum number of stable coins a user can have in their shell

**Function Signature:**

```typescript
 public getMaxShellSize(): Promise<number>
```

**Basic usage example:**

```typescript
 maxShellSize = await shellManager.getMaxShellSize();
```

### getUser <a id="getuser"></a>

▸ **getUser**\(userAddress: _`string`_\): `Promise`&lt;`User`&gt;

_Defined in_ [_ShellManager.ts:84_](https://github.com/cowri/cowri-sdk/blob/a1e664e/cowri-dapp-sdk/src/ShellManager.ts#L84)

**High Level Logic Overview** `getUser` returns a User object of the user with the provided address. This object includes the user's address, the tokens currently in the user's shell, and all balances and other metadata of each token.

**getUser** is called with the following options

**Parameters:**

| Name | Type | Description |
| :--- | :--- | :--- |
| userAddress | `string` | address/public key of the user retrieved e.g. \`0xE870B399Bf4D0ED2c74D97C3Fb9c25224CA2cEA0\` |

**Returns:** `Promise`&lt;`User`&gt; a user object

**Function Signature:**

```typescript
  public getUser(userAddress: string): Promise<User>
```

**Basic usage example:**

```typescript
 const userAddress = '0xE870B399Bf4D0ED2c74D97C3Fb9c25224CA2cEA0';
 user = await shellManager.getUser(userAddress)
```

### mintUser <a id="mintuser"></a>

▸ **mintUser**\(user: _`User`_\): `Promise`&lt;`User`&gt;

_Defined in_ [_ShellManager.ts:167_](https://github.com/cowri/cowri-sdk/blob/a1e664e/cowri-dapp-sdk/src/ShellManager.ts#L167)

**High Level Logic Overview** `mintUser` mints test stablecoins for the user. It does this by calling the cowri-faucet which has the capability to mint 100 or each stable coin supported. It then calls updateUser to retreive the updated user, including the new balances

_Note : for the initial developer release we support the following mocked stable coins in both Ganache and Kovan_

* Dai: 0x4C561F234520Bb75184E5337041285F990AA4107
* USDCoin: 0x49D9cebaDcD42F8a556e0a5a982a95dc191BF8c6
* TrueUSD: 0x936Bae0783D0e3c6B3799091E8803ffb563302e0
* Paxos Standard: 0xF63BF08CA72b7b4d0219777769f7B2E85C172BCB
* Gemini dollar: 0x6459d0c05A62dC1b4cC3b8f0CF652B6A2A0c3537

**mintUser** is called with the following options

**Parameters:**

| Name | Type | Description |
| :--- | :--- | :--- |
| user | `User` | a User object which contains the user's updated list of stable coins |

**Returns:** `Promise`&lt;`User`&gt; a user object reflecting the latest stable coins and their balances

**Function Signature:**

```typescript
 public async mintUser(user: User): Promise<User>
```

**Basic usage example:**

```typescript
 mintedUser = await shellManager.mintUser(thisUser);
```

### sendCowri <a id="sendcowri"></a>

▸ **sendCowri**\(receiverAddress: _`string`_, amount: _`BigNumber`_\): `Promise`&lt;`User`&gt;

_Defined in_ [_ShellManager.ts:198_](https://github.com/cowri/cowri-sdk/blob/a1e664e/cowri-dapp-sdk/src/ShellManager.ts#L198)

**High Level Logic Overview** `sendCowri` sends a combination of one or more stable coins based on the sender and receiver's shell. If there is no overlapping stablecoins it will call the cowri liquidity provider to swap stable coins and ensure the receiver only receives stablecoins that are in their cowri shell

**sendCowri** is called with the following options

**Parameters:**

| Name | Type | Description |
| :--- | :--- | :--- |
| receiverAddress | `string` | the receiver's address \(public key\) |
| amount | `BigNumber` | the amount of Cowri \(stble coins\) to send |

**Returns:** `Promise`&lt;`User`&gt; a user object reflecting the latest stable coins and their balances

**Function Signature:**

```typescript
 public async sendCowri(receiverAddress: string, amount: BigNumber): Promise<User>
```

**Basic usage example:**

```typescript
 const amount = new BigNumber(100);
 const receiever = '0x4a38736b7b8C78ab48e0C3020D10c4ff0134E1e1';
 updatedUser = await shellManager.sendCowri(receiver, amount);
```

### updateUser <a id="updateuser"></a>

▸ **updateUser**\(user: _`User`_\): `Promise`&lt;`User`&gt;

_Defined in_ [_ShellManager.ts:109_](https://github.com/cowri/cowri-sdk/blob/a1e664e/cowri-dapp-sdk/src/ShellManager.ts#L109)

**High Level Logic Overview** `updateUser` updates the shell ledger contract to the shell of the passed User object. It then returns the User object as is reflected on the updated shell ledger contract for that user, including all tokens and their balances.

**updateUser** is called with the following options

**Parameters:**

| Name | Type | Description |
| :--- | :--- | :--- |
| user | `User` | a User object which contains the user's updated list of stable coins |

**Returns:** `Promise`&lt;`User`&gt; a user object reflecting the latest stable coins and their balances

**Function Signature:**

```typescript
  public updateUser(user: User): Promise<User>
```

**Basic usage example:**

```typescript
 updatedUser = await shellManager.updateUser(thisUser);
```

### validateToken <a id="validatetoken"></a>

▸ **validateToken**\(tokenAddress: _`string`_\): `Promise`&lt;`Token`&gt;

_Defined in_ [_ShellManager.ts:226_](https://github.com/cowri/cowri-sdk/blob/a1e664e/cowri-dapp-sdk/src/ShellManager.ts#L226)

**High Level Logic Overview** validateToken takes a token address and validates that it an ERC-20 compliant token. If so, it also retrieves the user's balance for that token. It does this by calling functions on the token contract such as getBalance and getDecimals

**validateToken** is called with the following options

**Parameters:**

| Name | Type | Description |
| :--- | :--- | :--- |
| tokenAddress | `string` | the tokens address |

**Returns:** `Promise`&lt;`Token`&gt; a token object reflecting the tokens metadata and the user's balance

**Function Signature:**

```typescript
 public validateToken(tokenAddress: string): Promise<Token>
```

**Basic usage example:**

```typescript
 const thisToken = '0x4C561F234520Bb75184E5337041285F990AA4107';
 validatedToken = await shellManager.validateToken(thisToken);
```

