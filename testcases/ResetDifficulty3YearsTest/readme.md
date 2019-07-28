## Purpose of this test is to see a difficulty reset by 95% after 3 years

Since we cannot wait 3 years, we will change this line:
nFutureTime = now + 92275199;

to:

nFutureTime = now + 300;

Furthermore, we must increase a difficulty in the constructor
            n = 100; 
            _burned = 31896750* 10 ** uint(decimals);
            rewardEra = 100;
            _mintingEpoch = 100;
            ...
            nFutureTime = now + 1800; // about 3 years in the future
            
            
            
Also, added this into a pulse check

// ------------------------------------------------------------------------
// Checks if mining is alive
// ------------------------------------------------------------------------
    function pulseCheck() internal{
    uint treshold = (tokensMinted.mul(95)).div(100);
        if(nFutureTime<=now){
          name = "PASSED IF-THEN";
          n = (n.mul(150)).div(100); 
          miningTarget = (2 ** n);
          _startNewMiningEpoch();
        } 
        else{
            name = "DID-NOT-PASS";
        }
    }



We are repeating the send until 234 is reached and repeated.


            
Deployed here:
https://ropsten.etherscan.io/dapp/0x18eB41c65b4F2f25b24ff1311a415E5343E13FCa#readContract


STARTED WITH:
name:ButtCoin string
lastRewardEthBlockNumber:0 uint256
getMiningDifficulty:0 uint256
totalSupply:165771700000000 uint256
rewardEra:2 uint256
decimals:8 uint8
getMiningTarget:10141204801825835211973625643008 uint256
_totalSupply:3355446700000000 uint256
_burned:3189675000000000 uint256
getChallengeNumber:0x5b0bba81e8d0e5ef4d8f7b334024b68f8055afb59671f3986c6a9a0c02aa3907 bytes32
tokensMinted:3355446700000000 uint256
lastRewardTo:0x0000000000000000000000000000000000000000 address
balanceOf:
nFutureTime:1564327407 uint256
checkMintSolution:
_MAXIMUM_TARGET:1267650600228229401496703205376 uint256
challengeNumber:0x5b0bba81e8d0e5ef4d8f7b334024b68f8055afb59671f3986c6a9a0c02aa3907 bytes32
owner:0xda54fcb4728641112985a7444fe2c6f9a7f4ffca address
symbol:0xBUTT string
getMintDigest:
lastRewardAmount:0 uint256
mintingEpoch:0 uint256
getDifficultyExponent:103 uint256
newOwner:0x0000000000000000000000000000000000000000 address
previousSender:0x0000000000000000000000000000000000000000 address
allowance:
getNextAward:2248091 uint256

PASS!








