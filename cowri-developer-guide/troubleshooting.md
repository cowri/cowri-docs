# Troubleshooting

## Known Issues

### Issues when running ganache locally

**The following issues are caused when restarting ganache locally**

**Issue** - Invalid Nonce

**Resolution** - In Metamask reset account

**Issue** - Cowri Demo App Spins without connecting

**Resolution** - In Metamask refresh the connection by switching to another network and then back to localhost:8545

**Issue** - Cannot connect to local ganache instance

**Resolution** - In Metamask set up a new RPC connection to localhost:8545

**The following Issues are known Metamask Issues**

**Issue** - Metamask confirmations are not appearing **Resolution** - Click on the Metamask Icon and the Confirmations will appear

## Developer Facing Errors

| Component | function | \# | Error Message | Root Cause | Action |  |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| CowriWeb3 | setPlatform | 0000 | Invalid Web3 Object Passed |  |  |  |
| CowriWeb3 | getUser | 0001 | Web3 instance must be initialized with the setPlatform function |  |  |  |
| CowriWeb3 | getUser | 0002 | Not connected to Ethereum | MetaMask Instance is not connected to a valid Ethereum Web3 Instance | Start MetaMask and connect to a valid Ethereum Instance \(Kovan\) |  |
| CowriWeb3 | getUser | 0003 | Invalid Ethereum Instance - No Shell Ledger |  |  |  |
| CowriWeb3 | getUser | 0004 | Invalid Ethereum Instance - No Ox Contract |  |  |  |
| CowriWeb3 | getUser | 0005 | Invalid Ethereum Instance - No current User |  |  |  |
| CowriWeb3 | getUser | 0006 | User has no shell Ledger |  |  |  |

