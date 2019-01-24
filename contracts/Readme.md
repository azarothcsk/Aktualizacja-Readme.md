### Dock Plasma Cash Contracts  

#### NOTE:   
**Contracts are forked from [Loom Network](https://github.com/loomnetwork/plasma-cash). Please check each file in contracts for the applicable license. Rule of thumb: Loom-based code is GPL3, if in doubt, it's GPL3, the rest is MIT.**  

**Contracts are beta and have not undergone a third-party review yet. Tread with care.**  

#### Compiling the contracts  
Follow [Populous](https://populus.readthedocs.io/en/latest/deploy.html),  [Truffle](https://truffleframework.com/docs/truffle/getting-started/compiling-contracts), [py-solc](https://github.com/ethereum/py-solc), the [solidity](https://solidity.readthedocs.io/en/v0.4.24/installing-solidity.html) instructions to install and rn solc. At this time, you want to stay < 0.5 and 0.4.24 is a good choice.  
From the command line:  

```bash
$ solc --version # should be 0.4.24
$ solc -o build --combined-json abi,bin --optimize  --optimize-runs=1 --evm-version byzantium contracts/*.sol
```  
Note that the evm-version default is _byzantium_ but with a fork afoot, you may want to keep this setting in mind.  

For a quick start, see the _compile_to_json.py_ script, which utilizes py-solc and assumes solc  0.4.24 is installed. If it is not, after ```$ pip install py-solc```, run ```$ python -m solc.install v0.4.25```. At least on OSX, the commandline installation, especially if another, newer version is already in place, seems to work reasonably flawless. If you have higher version installed with brew, you may need to unlink.  

Ok. now that we got a working solidity setup in place you can either compile from the command line or utilize the _compile_to_json.py_ script. If you want to use the deployment scripts in _deploy.py_, you may want to utilize the python script to keep changes to a minimum. 
```$ python compile_to_json.py``` creates a _json_ dir and decomposes solc's _complete.json_ into individual *.json files including the abi and bin output, if applicable.  

#### Deploying the contracts  
**Contracts are beta and have not undergone a third-party review yet. Tread with care.**  

The _deploy.py_ script includes a fairly generic **deploy** function as well as a few support functions and a parameterized **quick_deploy** function. Note that if you want to work with the contracts post deployment, you want to persist the personal and contract accounts as well as the transaction receipts for future reference. Moreover, there are a few initialization parameters you may want to adjust depending on your use case. See _deploy.py_ for more details and definitely before running it.  

Note that **quick_deploy** assumes you have access to a running (dockerized) parity dev node. You don't have to have docker by it sure helps. Assuming you do:  

```bash 
$ docker pull parity/parity:stable	
```  

For a minimal parity dev client:  

```bash
$ docker run -d -ti \
                 -v ~/.parity/:/home/parity/.local/share/io.parity.ethereum/ \
                 -p 8545-8546:8545-8546 \
                 --name <your container name> parity/parity:v2.2.5 \
                 --chain dev \
                 --jsonrpc-interface all \
                 --jsonrpc-apis all \
                 --jsonrpc-cors all \
                 --jsonrpc-hosts all
```  

should do. Make sure you replace <_your container name_> with the actual name and adjust the local dir as needed. If you end up having trouble writing to the local volume ```chmod a+rwx -R <your dir>``` out to do the trick.  

With more scaffolding out of the way, it's time to deploy the contracts:  

```python 
$ python deploy.py
```  

is the anti-climactic last step.  

Finally, ff you like to keep an eye on things, open a separate terminal __before__ you deploy the contracts and:  

```bash 
$ docker logs -f <your_container_name or id>
``` 

and you should see the block transactions zipping by.






