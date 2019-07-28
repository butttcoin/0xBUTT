## Deployment test

This test case ensures that
1. code compiles on Remix
2. code gets deployed
3. code gets verified
4. all public variables and functions are listed on dapp page.
5. all coins got pre-minted


1. and 2.
https://ropsten.etherscan.io/tx/0x05bd70f212e7b4e01d260a9b126be8d488e772d6262590611bb7bf5b13aeebc5

3.
https://ropsten.etherscan.io/address/0x388f50d323e79c4bbe8b3041637e84e30a5658a3#code

4. 
name:ButtCoin string 
lastRewardEthBlockNumber:0 uint256
getMiningDifficulty:2 uint256
totalSupply:3355443200000000 uint256
rewardEra:2 uint256
decimals:8 uint8
getMiningTarget:13803492693581127574869511724554050904902217944340773110325048447598592 uint256
_totalSupply:3355443200000000 uint256
_burned:0 uint256
tokensMinted:3355443200000000 uint256
lastRewardTo:0x0000000000000000000000000000000000000000 address
balanceOf:
nFutureTime:1656547913 uint256
checkMintSolution:
_MAXIMUM_TARGET:27606985387162255149739023449108101809804435888681546220650096895197184 uint256
challengeNumber:0x099c0b5f54515b9c11fdb29752bf473b4d99af983f50cb89ae3727e6d7ce2669 bytes32
owner:0xda54fcb4728641112985a7444fe2c6f9a7f4ffca address
symbol:0xBUTT string
getMintDigest:
lastRewardAmount:0 uint256
mintingEpoch:0 uint256
getDifficultyExponent:233 uint256
newOwner:0x0000000000000000000000000000000000000000 address
previousSender:0x0000000000000000000000000000000000000000 address
allowance:
getNextAward:1 uint256

For functions see:
https://ropsten.etherscan.io/dapp/0x388f50d323e79C4bBe8b3041637E84E30a5658a3#writeContract

5.

Total Supply:
33,554,432 0xBUTT


ALL PASSED
