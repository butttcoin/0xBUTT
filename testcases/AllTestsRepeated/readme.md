###  This is a collection of all tests performed before the main launch of a code.

Tests are performed in this order:

1. DeploymentTest
2. ConstructorTest
3. DecreaseByBurnTest_
4. FunctionCallPublicTest
6. ResetDifficulty3YearsTest
7. MiningTest
8. TestBurnAndTransfer

New deployment is done for each test


### DeploymentTest
https://ropsten.etherscan.io/dapp/0x8c98470B37A1EDF0567AcA002bf558B6Beb3e497
PASS!  (with a beautiful getNextAward timestamp!)

### ConstructorTest
https://ropsten.etherscan.io/dapp/0xB59B31Ef4B6150109167e831cD48B6527981Ce21#readContract
PASS!  (this time _mintingEpoch was removed)

### DecreaseByBurnTest_
https://ropsten.etherscan.io/dapp/0x75B79639810C240bDaAE4A7AF949fb1909f120c4#readContract
PASS!

### FunctionCallPublicTest 
(reused deployment)
https://ropsten.etherscan.io/dapp/0x75B79639810C240bDaAE4A7AF949fb1909f120c4#readContract
PASS!

### ResetDifficulty3YearsTest 
https://ropsten.etherscan.io/dapp/0x1D43eb66e8656f9a50D1eD49F2041a85608c8C98
PASS! (_mintingEpoch was removed)

### MiningTest 
https://ropsten.etherscan.io/dapp/0xD0714D09B4aE63e021Bc62Ac61369bCD0a0e53F6#readContract
PASS! (this time _mintingEpoch was removed)


### TestBurnAndTransfer 
https://ropsten.etherscan.io/token/0x1235f2ac377db02417269a52a73573fea005ccdf
PASS!
