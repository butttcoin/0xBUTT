## The purpose of this test is to test the following

1. Correct amount gets transferred from A to B
2. Correct amount is displayed on A and B
3. Correct amount is burned (in this case, 2% is sent to address(0))
4. Correct amount is displayed as the overall supply
5. Correct increments are displayed on the online dapp overview
6. When next transaction is made, A gets 1% back, 1% is sent to address(0)
7. Correct increments are displayed on the online dapp overview

For this testcase a new contract will be deployed, with 33554467 pre-mined coins

1. If we send 1234 tokens, the A should have 33553233.  B should have 1209.32. address(0) should get 24.68
2. Overall supply should be 33554442.32
3. When B sends 123 tokens to C, B should have 1086.32, C should have 120.54, A should get 1.23, address(0) should get +1.23. A's total should be 33553234.23
4. Overall supply should be 33554441.09


Results:
Contract created:  https://ropsten.etherscan.io/tx/0x3b9e245bc6eac1294411be39e0a9cf732f8440f99193e928ffa86e5ff677fcf1
Contract address: 0x5a159F1433397AC1aeBA5a8dDaE439B85542DCC2

Total Supply: 33,554,467 0xBUTT -OK

1.
Sending 1234 from 0xda54Fcb4728641112985A7444FE2C6f9A7f4FFCA to 0x496Cd58eecC70992d86d5Dd7DE70d6a049305416
https://ropsten.etherscan.io/tx/0x9276eba71365c95dfbfd1a09afb5d90a7ff4e824163c435455a19d35138526d6

A has: 33553233 -OK
B has: 1209.32 -OK
address(0) has: 24.68 -OK
overall supply: 33554442.32 -OK


2. 
(Side-Note: sent some ETH to B)
Sending 123 from 0x496Cd58eecC70992d86d5Dd7DE70d6a049305416 to 0x0Da59F0647b607De89115f96caEb4f1c46005023
https://ropsten.etherscan.io/tx/0xcd825bd699f59ae2fb75658e4a81a27344b8ee834ef4c751a8b7305efa977ee5

B has: 1086.32 -OK
C has: 120.54 -OK
A has: 33553234.23 -OK
Overall supply: 33,554,441.09 -OK
address(0) has: 25.91 (that is, additional 1.23) -OK

PASSED!
