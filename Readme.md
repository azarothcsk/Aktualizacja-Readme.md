### Dock Plasma Cash Contracts  

#### NOTE:   
**Contracts are forked from [Loom Network](https://github.com/loomnetwork/plasma-cash). Please check each file in contracts for the applicable license. Rule of thumb: Loom-based code is GPL3, if in doubt, it's GPL3, the rest is MIT.**  

**Contracts are beta and have not undergone a third-party review yet. Tread with care.**  

##### To Do  
- [ ] Clean up lint errors in contracts, including snake case
- [x] Add compile script    
- [x] Add deployment script  
- [ ] Add tests  
- [ ] List testnet addresses
- [ ] Add SDK


#### Overview  
The Dock Plasma Cash contracts are customized to support a single-validator, single-operator deployment. This makes for a compact, reasonably cost-effective, solution suitable for a variety of paywall and exchange scenarios including one-to-many and many-to-many. Hence, this solution can be quite appealing to 'owner-operators' ranging from IoT to more traditional data exchanges.  

In the future, we plan to release the Dock SDK supporting the configuration, deployment, and management of the Dock single validator, single operator solution in a highly scalable master/slave configuration.  

If you are in the IoT or digital goods data exchange space and interested in working with the Dock SDK, please leave a note in the Issues section.  


#### Compiling & Deploying Contracts  

See the [Readme.md](https://github.com/getdock/plasma-cash-contracts/tree/master/contracts) in _contracts/_ for further information.  


#### Testnet Accounts  
The addresses for the test contracts deployed on Ropsten and Kovan, respectively, are:
Plasma:   NA, NA  
ERC20:    NA, NA  
ERC721:   NA, NA  
DoCheck:  NA, NA  
