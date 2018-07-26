#################
Test Net (Ropsten Network)
#################


To start
=====================================

We need 3 components:

* Ethereum Address (Ropsten Network)
* Some Ether (Ropsten Network)
* Solidity contract


Ethereum address
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Go to `MyEtherWallet <https://www.myetherwallet.com>`_ (MEW) and create an account. 

To get setup, click the right hand side corner, change the network to Ropsten (MyEtherWallet) → click the New Wallet →Enter a password you can remember → Download / Save your Keystore file in a safe space → Save your Private Key in a safe space.


To view your wallet address, go to →View Wallet Info →Private Key → Enter the saved private key →Unlock your Wallet



Ether
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
As an example we will use the Ropsten Test network. But there are other testnet that can be used.
To get some Ropsten Ethereum Just access `this faucet <https://faucet.bitfwd.xyz/>`_  and put your ropsten address.




Solidity contract
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
As contract we can use the contract defined in ``scuffold`` page.




Deploy
=====================================
* Go to `Remix <http://remix.ethereum.org/>`_
* In the browser/ballot.sol, paste the code you just edited! If something red comes up, there is something wrong in the code.
* Now Under Compile →Details →Choose the Token you are creating
* Under ByteCode press the 📋 button to copy the ByteCode to your clipboard —( Into this section, what may appear are different things on the ByteCode. What you have to copy is the “object” ByteCode, adding a 0x in the beginning. So you will have 0xByteCode.)
* Go to MEW
* Navigate to the Contracts tab → Press Deploy Contract
* Paste your ByteCode into the ByteCode box. Your gas limit should automatically update
* Access your wallet by going into the Private Key → Enter your private key →Unlock your wallet
* Now press Sign Transaction →Deploy Transaction
* Click on the transaction tx or access `etherscan <https://ropsten.etherscan.io>`_  to check if the contract went through.



Register the contract
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
* In the Overview Tab → Click on the Contract Address
* Go to the Contract Code Tab → Click Verify and Publish


Get it right once or get it wrong forever.
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
#. Be sure that the contract address field corresponds to the contract address that you have just deployed. Remember contract address is different to the MEW address you created so make sure not to get them confused
#. The contract name has to match the one in the code
#. To check which version of the complier, go back to the remix page where you got the BYTECODE from and look at the URL, the complier version will be there. In most cases it should be: v0.4.19+commit.c4cbbb05.js
#. On Optimisation, choose No (We haven’t enable it before)
#. On ENTER THE SOLIDITY CONTRACT CODE BELOW, copy the whole code from Remix, and paste in that area. NOT THE BYTECODE, but the code itself.
#. Now, leave the other fields in blank and click on Verify and Publish.



