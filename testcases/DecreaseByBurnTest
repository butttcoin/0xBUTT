The purpose of this test-case is to see a decrease in a difficulty assuming a 95% burn.  
Code had to be changed, these are the lines altered:

Constructor:
n = 100; 
_burned = 31876750* 10 ** uint(decimals);
rewardEra = 134;
_mintingEpoch = 100;

Since there was no other way to test the 95% burning other than by the mining, the pulse-check got added the same if-then and therefore became:

// ------------------------------------------------------------------------
// Checks if mining is alive
// ------------------------------------------------------------------------
    function pulseCheck() internal{
    uint treshold = (tokensMinted.mul(95)).div(100);
    if(_burned>=treshold){
         name = "PASSED IF-THEN";
        //lower difficulty to significant levels
        n = (n.mul(105)).div(100);
        if(n > 213){n = 213;}
        miningTarget = (2 ** n);
    }
        
    //if either the coin is dead or the mining is stuck  
        if(nFutureTime<=now){
          n = (n.mul(150)).div(100); 
          miningTarget = (2 ** n);
          _startNewMiningEpoch();
        }  
    }

https://ropsten.etherscan.io/dapp/0x3b2Ae277bba8af94700E5D1F3c6373CE5A696e62#readContract


1. FIRST RUN:

OLD:
name:ButtCoin string
totalSupply:165771700000000 uint256
getMiningTarget:10141204801825835211973625643008 uint256
_totalSupply:3355446700000000 uint256
_burned:3189675000000000 uint256
getDifficultyExponent:103 uint256
previousSender:0x0000000000000000000000000000000000000000 address
getNextAward:2248091 uint256

NEW:
name:PASSED IF-THEN string
totalSupply:165769700000000 uint256
getMiningTarget:324518553658426726783156020576256 uint256
_totalSupply:165769700000000 uint256
_burned:3189677000000000 uint256
getDifficultyExponent:108 uint256
previousSender:0xda54fcb4728641112985a7444fe2c6f9a7f4ffca address
getNextAward:2000376 uint256


2. SECOND RUN:

NEW:

name:PASSED IF-THEN string
totalSupply:165768700000000 uint256
getMiningTarget:10384593717069655257060992658440192 uint256
_totalSupply:165768700000000 uint256
getDifficultyExponent:113 uint256
previousSender:0xda54fcb4728641112985a7444fe2c6f9a7f4ffca address
getNextAward:1771561 uint256




What we wanted to see here is that difficulty decreases when 95% burning is achieved by 5%... it got from 103 to 108 to 113.  Furthermore, we can also see that the next reward decreases.

PASS !




