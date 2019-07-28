## The purpose of this test-case is to see whether and how the public functions work.

### Read Contract functions:
https://ropsten.etherscan.io/dapp/0x388f50d323e79C4bBe8b3041637E84E30a5658a3#readContract

balanceOf method Response: 3355443200000000 uint256

-- Other functions concern the miners and will be tested by testing the mining.

### Read Contract functions:
https://ropsten.etherscan.io/dapp/0x388f50d323e79C4bBe8b3041637E84E30a5658a3#writeContract

approve:
https://ropsten.etherscan.io/tx/0x25d2621dbfcba6dc7726c39dfe6830be7c940f4ac341abcae7d7c54f52a064f6
allowance method Response: 1213123123123 uint256 -OK!

multi-transfer:
https://ropsten.etherscan.io/tx/0x9f26ae0e17f2f86a320f26c525cb2816e4cc6464e12f4773cfb4c25055b47e77

transfer-from:
https://ropsten.etherscan.io/tx/0x7d24ecbb7d3718fc7107b3ee1350e72a03129b9b47e545fb136eda2992bd8190

Accept ownership:  Should not work from the web-form. Result:
ALERT: Transaction Error. Exception thrown in contract code.
https://ropsten.etherscan.io/tx/0x4fd10688bb3446bf31da30a34bc4781e81b94bdf32afb0c169bce3ade9460ca0

Transfer:
https://ropsten.etherscan.io/tx/0xb5314ccea96b6c85e470cdabc29d68b3fd23ac1e695a588a1456626796bf0b8f

Approve and Call: should not work from the web-form:
ALERT: Transaction Error. Exception thrown in contract code.
https://ropsten.etherscan.io/tx/0x569e4693f825358dd1ac930b4e941ca0041483a7bb0e555b65c26a1c8c588205

Transfer and ERC20 token: should fail (a feature)
ALERT: Transaction Error. Exception thrown in contract code.
https://ropsten.etherscan.io/tx/0x569e4693f825358dd1ac930b4e941ca0041483a7bb0e555b65c26a1c8c588205

Transfer ownership:
https://ropsten.etherscan.io/tx/0x59b7f5d6829583aad32a707d74101777830767f05308a8891f44c64c296172af

Testing after transfering the ownership:
Accept ownership: 
https://ropsten.etherscan.io/tx/0xec996472c12c0060a054f08604823379a94d669b671a6cc7ecf0845117881d29

Transfer from 0x0000000000000000000000000000000000000000
Rejected

PASSED!





