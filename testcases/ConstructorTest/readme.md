## Tests a constructor VS dapp display

    constructor() public {
        if (locked) revert();
        symbol = "TEST";
        name="TEST NAME";
        
        decimals = 8;
        
        _totalSupply = 8000;
        _burned = 10000;
        
        n=1234;
        nFutureTime=66666;
        _MAXIMUM_TARGET=1234567890;
        rewardEra=321;
        lastRewardAmount=54321;
        lastRewardEthBlockNumber=block.number;
        tokensMinted = 112233;
        
        lastRewardTo = 0x0Da59F0647b607De89115f96caEb4f1c46005023;
        previousSender = 0xc2F6c0c798014C2dF0aCC644e497F44748cF0387; //the previous user of a contract
        
        challengeNumber = blockhash(lastRewardEthBlockNumber - 1);
        
        miningTarget = 90909;
        _mintingEpoch=12333214;
        basePercent=1231232123;
        
        
        locked = true;
    }
    
    dAPP display:
    
name:TEST NAME string  - OK
lastRewardEthBlockNumber:6079736 uint256   - OK
getMiningDifficulty:13580 uint256
totalSupply:102233 uint256  - OK since there are no negatives
rewardEra:321 uint256  - OK
decimals:8 uint8  - OK
getMiningTarget:90909 uint256  - OK
_totalSupply:8000 uint256  - OK
_burned:10000 uint256  - OK
getChallengeNumber:0xb71d6324588640b493d3a23c47835c65e666bf54718102bb9e17fbb2f67e27f1 bytes32   - OK
tokensMinted:112233 uint256  - OK
lastRewardTo:0x0da59f0647b607de89115f96caeb4f1c46005023 address  - OK
balanceOf:
nFutureTime:66666 uint256  - OK
checkMintSolution:
_MAXIMUM_TARGET:1234567890 uint256  - OK
challengeNumber:0xb71d6324588640b493d3a23c47835c65e666bf54718102bb9e17fbb2f67e27f1 bytes32  - OK
owner:0xda54fcb4728641112985a7444fe2c6f9a7f4ffca address  - OK
symbol:TEST string  - OK
getMintDigest:
lastRewardAmount:54321 uint256  - OK
mintingEpoch:12333214 uint256  - OK
getDifficultyExponent:1234 uint256  - OK
newOwner:0x0000000000000000000000000000000000000000 address  - OK
previousSender:0xc2f6c0c798014c2df0acc644e497f44748cf0387 address  - OK
allowance:
getNextAward:115792089237316195423570985008687907853269984665640564039457584007912129639936 uint256  - OK


PASS

    
    
