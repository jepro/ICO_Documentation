#################
Solidity
#################


Basic Example 
=====================================

A contract in the sense of Solidity is a collection of code (its functions) and data (its state) that resides at a specific address on the Ethereum blockchain.

.. code-block:: javascript
   :linenos:

	pragma solidity ^0.4.0;

	contract SimpleStorage {
	    uint storedData;

	    function set(uint x) public {
	        storedData = x;
	    }

	    function get() public view returns (uint) {
	        return storedData;
	    }
	}

Just store and retrieve information (a variable) on the	blockchain.


.. code-block:: javascript
   :linenos:

	pragma solidity ^0.4.0;

Ensures that the contract does not suddenly behave differently with a new compiler version.




Subcurrency Example
=====================================


.. code-block:: javascript
   :linenos:

   pragma solidity >0.4.24;

	contract Coin {
	    // The keyword "public" makes those variables
	    // readable from outside.
	    address public minter;
	    mapping (address => uint) public balances;

	    // Events allow light clients to react to
	    // changes efficiently.
	    event Sent(address from, address to, uint amount);

	    // This is the constructor whose code is
	    // run only when the contract is created.
	    constructor() public {
	        minter = msg.sender;
	    }

	    function mint(address receiver, uint amount) public {
	        if (msg.sender != minter) return;
	        balances[receiver] += amount;
	    }

	    function send(address receiver, uint amount) public {
	        if (balances[msg.sender] < amount) return;
	        balances[msg.sender] -= amount;
	        balances[receiver] += amount;
	        emit Sent(msg.sender, receiver, amount);
	    }
	}

The line event ``Sent(address from, address to, uint amount);`` declares a so-called “event” which is emitted in the last line of the function ``send``. User interfaces (as well as server applications of course) can listen for those events being emitted on the blockchain without much cost. As soon as it is emitted, the listener will also receive the arguments ``from``, ``to`` and ``amount``, which makes it easy to track transactions

In order to listen for this event, you would use


.. code-block:: javascript
   :linenos:
   
	Coin.Sent().watch({}, '', function(error, result) {
	    if (!error) {
	        console.log("Coin transfer: " + result.args.amount +
	            " coins were sent from " + result.args.from +
	            " to " + result.args.to + ".");
	        console.log("Balances now:\n" +
	            "Sender: " + Coin.balances.call(result.args.from) +
	            "Receiver: " + Coin.balances.call(result.args.to));
	    }
	})






