# Functions and Errors  / PROJECT

 write a smart contract that implements the require(), assert() and revert() statements.

## Description

`pragma solidity ^0.8.26;`
 This line specifies the version of Solidity to use. The caret ^ indicates that any version of Solidity greater than or equal to 0.8.26 is allowed but less than 0.9.0.

`contract errors { ... }: `This line declares a new Solidity contract named errors.

`uint public balance = 0;:` This line declares a public state variable named balance of type uint and initializes it with the value 0. 
The public modifier allows external contracts to read the value of balance.

`function withdraw(uint amount) public { ... }:` This function allows withdrawing a specified amount from the balance.
It takes a uint parameter amount and is publicly accessible (public).

`require(balance > amount, "Not sufficient balance ");`: This line uses the require statement to ensure that the balance is greater than the amount being withdrawn. 
If not, the transaction will revert with the error message "Not sufficient balance ".

`balance = balance - amount`: If the require condition is met, this line subtracts the amount from the balance.

`function deposit(uint amount) public { ... }`: This function allows depositing a specified amount into the balance. It takes a uint parameter amount and is publicly accessible (public).

`balance = balance + amount;`: This line adds the amount to the balance.

`if (balance > 400) { revert("Balance is exceeding the limit"); }`: This if statement checks if the balance exceeds 400. 
If it does, the transaction will revert with the error message "Balance is exceeding the limit".

`function zero() public view returns (string memory) { ... }:` This function checks if the balance is zero. It is public, view (does not modify the state), and returns a string.

`assert(balance == 0);`: This assert statement ensures that the balance is equal to 0.
If not, it indicates a critical error, and the transaction will revert.




## Getting Started

### Executing program

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., HelloWorld.sol). Copy and paste the following code into the file:

```javascript
 //SPDX-License-Identifier: MIT

pragma solidity ^ 0.8.26;

contract errors{

    //we have initial balance =0
    uint public balance = 0;
    function withdraw(uint amount) public {
        require(balance > amount, "Not sufficient balance ");
      balance = balance-amount;
    }
    function deposite(uint amount) public {
        balance =balance+ amount;
        if(balance > 400){
            revert("Balance is exceeding the limit");
        }
    }

function zero() public view returns (string memory){
    assert(balance ==0);
    return "No money for the transaction";
}
}
```

To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.26" (or another compatible version), and then click on the "Compile errors.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "errors" contract from the dropdown menu, and then click on the "Deploy" button.

Fill all the required fields ,i.e amount, balance etc.

## Authors
Vinod Kumar Saini


## License

This project is licensed under the MIT License - see the LICENSE.md file for details
