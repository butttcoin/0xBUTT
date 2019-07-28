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
3. When B sends 123 tokens to C, B should have 1086.32, A should get 1.23, address(0) should get 1.23. A's total should be 33553234.23
4. Overall supply should be 33554441.09


