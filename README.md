PROJECT
Error Handling
In this project, I'll just go over the three primary functions that Solidity uses to handle errors. They are as follows:

require(): Before the actual code is executed, the require() method is used to verify and check the condition.

assert(): This function is meant to ensure that conditions are met; if they aren't, the execution is stopped.

Revert(): The function used to handle mistakes and undo state modifications. Using it with or without an error message is possible

# eth-course
We can use the online Solidity IDE Remix to run this program. Visit the Remix website at https://remix.ethereum.org/ to get started.
we can Click the "+" symbol in the left-hand sidebar to start a new file once we are on the Remix website. Save the file as something like error handling.sol, ending in.sol. The code below should be copied and pasted into the file:

     // SPDX-License-Identifier: MIT
    solidity ^0.8.18;
    contract ErrorHandle {
    uint public CarPrice = 10000;
    uint public balance = 25000;

    function checkCost() public {
        require(CarPrice > 9999, "Car price must be greater than 9999");
        CarPrice -= 4000;
    }

    function buyCar() public {
        if (balance < 10000) {
            revert("Insufficient balance to buy Cars");
        } else {
            balance -= 10000;
        }
    }

    function refund() public {
        assert(balance >= 10000);
        balance += 10000;
    }
    }


# Author
Aakriti Singh singhaakriti203@gmail.com

# License
This project is licensed under the MIT License - see the LICENSE.md file for detail
