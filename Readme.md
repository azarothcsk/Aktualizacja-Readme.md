### Dock Plasma Cash Contracts  

#### NOTE:   
**Contracts are forked from [Loom Network](https://github.com/loomnetwork/plasma-cash). Please check each file in contracts for the applicable license. Rule of thumb: Loom-based code is GPL3, if in doubt, it's GPL3, the rest is MIT.**  

**Contracts are beta and have not undergone a third-party review yet. Tread with care.**  

##### To Do  
- [ ] Clean up lint errors in contracts, including snake case  
- [ ] Add deployment script  
- [ ] Add tests  
- [ ] List testnet addresses
 

#### Overview  
The Dock Plasma Cash contracts are a customized to support a single-validator, single-operator, master-slave deployment. This makes for a compact, reasonably cost-effective, solution suitable for a variety of paywall scenarios.  

The addresses for the test contracts deployed on Ropsten are:
Plasma: xxx  
ERC20:  xxx  
ERC721: xxx   


#### Compiling  

Follow [Populous](https://populus.readthedocs.io/en/latest/deploy.html),  [Truffle](https://truffleframework.com/docs/truffle/getting-started/compiling-contracts), or [py-solc](https://github.com/ethereum/py-solc) directions or follow the solidity [instructions](https://solidity.readthedocs.io/en/v0.4.24/installing-solidity.html). At this time, you want stay < 0.5.  
From the command line:   
```solc -o build --combined-json abi,bin --optimize  --optimize-runs=1 --evm-version byzantium contracts/*.sol```  
Note that the evm-version default is byzantium but with a fork afoot, you may want to keep this setting in mind.  







 







