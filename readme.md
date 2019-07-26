## ButtCoin White-Paper 
#### (0xBUTT)
-------------------------------

### Introduction
The purpose of making this ERC20 token/coin is to create a cryptocurrency that is based on people’s beliefs regarding the Bitcoin. ButtCoin is by no means better or worse than a Bitcoin. It is simply different. ButtCoin was carefully brainstormed from various resources and stories about Bitcoin, and put together into a functioning contract. The resources are scattered, while referencing them would be a long-term project. Ethereum has provided us with an ability to make almost any functioning model of a cryptocurrency that we want, without worrying about the low-level priorities that concern coin’s survival. This coin is made as a proof that we can take almost any idea regarding the cryptocurrencies, even misconceptions, and create a product that might under-perform or even out-perform the Bitcoin. Furthermore, a different name could have been chosen. ButtCoin is a distortion of a BitCoin, and therefore a work of satire. Since the ButtCoin community was already formed prior to this coin, and since it is a community which enjoys a good satire, ButtCoin has been chosen as a name of this coin. 


### About the format
If code were the law, than a proper white-paper would represent a code-documentation. The code can be found deployed under Ethereum’s contract: 
[0x54CCf0c46D45b85A37f960cBe1ECAfAe5844252b](https://etherscan.io/address/0x54CCf0c46D45b85A37f960cBe1ECAfAe5844252b)



This white-paper will skip all the non-technical details, necessary repetitions and the common knowledge regarding the ERC20 tokens running on Ethereum. Furthermore, the main purpose of this white-paper is to translate the source-code to a plain and understandable English. The main parts of the source-code are ApproveAndFallCallback, Erc20Interface, ExtendedMath, Owned, SafeMath, and ZERO_X_BUTTv3. Everything else other than ZERO_X_BUTTv3 are the standards for coding an Ethereum token, and therefore, those will not be covered with the white-paper.

Most of the source-code originates from 0xBitCoin’s contract.
The 0xBitcoin contract is located at Ethereum address [0xb6ed7644c69416d67b522e20bc294a9a9b405b31](https://etherscan.io/address/0xb6ed7644c69416d67b522e20bc294a9a9b405b31) and has validated transparent code which can be audited on the Etherscan service.


### Functions, a general overview
ZERO_X_BUTTv3 consists of the public, private and internal functions:

Internal functions are: _mint, _startNewMiningEpoch,  checkMintedNumber, _reAdjustDifficulty, pulseCheck.

Private function: findTwoPercent.

Public functions are: constructor, mint, getChallengeNumber,  getMiningDifficulty,  getMiningTarget,  getMiningReward, getMintDigest,  checkMintSolution, totalSupply, burned, minted, mintingEpoch, balanceOf, transfer, multiTransfer, approve,  transferFrom, allowance, approveAndCall, transferAnyERC20Token.

The functions that exactly match the 0xBitCoin’s original code (regardless the Solidity version) are the one-line getter functions while the main algorithm has been entirely crafted into a new coin. Therefore, only the important changes will be discussed.

### Main Constructor
``` js
constructor() public {...
```
Constructor function is a function that is called by default. It is used to set the variables and call any additional setter functions before the program begins executing. This is where we set the coin symbol, name, decimals, base percent, rewardEra, miningTarget, tokensMinted, mintingEpoch, _totalSupply, and locked.  Here is what each variable means:

```symbol``` : This is coin’s market symbol, such as BTC for Bitcoin. In our case, 0xBUTT.

```name``` : This is coin’s name, such as Bitcoin. In our case, ButtCoin.

```decimals``` : Since Solidity (Ethereum’s language) currently does not support decimals, we have to use very large numbers and say how many spaces, from the large number, are decimals. In our case, we put 8 decimals.

basePercent : This helps us calculate the percentage for burning or sending to a previous address.

```toMint``` : If you are used to a BTC model, you may find ButtCoin very confusing. This is because ButtCoin is not replicating a BTC model. For example, BTC has started with zero coins, while ButtCoin has not started from a zero, thus leaving the mining-difficulty unaffected. If we want to kick-start and create initial coins without the costly mining, we can specify how many to generate. ButtCoin has generated 33554432 coins, while we can mine about 755975025 additional coins. This means, only 4% are generated. Now, please stop right here and forget what has been written. The 4% is an assumption, and we can mint as many coins as we want being restricted by technology VS mining difficulty. Futhermore, 4% is below the usual standard of 15%-20%. The 4% is then divided and given to exchanges, community, burning, and covering developer fees. However, since the mining difficulty increases faster than BTC, 4% can easily be seen as the 15%-20%. Furthermore, since we can infinitely mine and burn the coins, the generated 4% will become meaningless over time. Some strict BTC followers may not agree with this pre-mining idea, while taking a BTC model for granted. On contrary, getting deeper into ButtCoin’s model would show why BTC’s approach would be an absurd.

```tokensMinted``` : We are tracking how many tokens got minted overall. However, if the number gets too high (1.725436587×10⁶¹, which will probably never happen), we are resetting this number as well as the number of the burned tokens by 2^50 to continue tracking. This is called a minting epoch, and after the first epoch, we have to start calculating how many were minted/burned, since the actual numbers will not match. 2^50 has been chosen as a safe number, while it could be any other number that would make the mechanism work. Unfortunately, no programming language allows infinitely-large numbers, and therefore, such a mechanism must be developed.

```_totalSupply``` : Total supply, in case of a ButtCoin, is not the supply that can be minted, since there is no finite number. Unlike BTC, total supply is the same as the available amount, and is always a dynamic number depending on how many tokens were minted or burned. This may also be confusing to BTC followers who were used to seeing a finite number: 21,000,000.

```rewardEra``` : Every mining award starts a new reward era. With the reward era, difficulty is always increasing, until enough coins are burned to consider lowering a difficulty. Unlike BTC that has the new reward era increased after 1024 rewards, we are starting a new era after each reward. Therefore reward era also represents the step of a difficulty. Reward, however, is calculated with a simple formula (234-n)^3 where n comes form the mining difficulty if expressed as a 2^n. 

```miningTarget``` : This is the mining difficulty which starts at 2^234. Greater the number, easier the mining. Each reward, the number decreases as 2^233, 2^232, 2^231,...2^(n-1). BTC and Ethereum don’t follow this pattern.  Since miners keep BTC alive, BTC is constantly adjusting a difficulty to be accessible to miners. ButtCoin does not need to do that, and therefore, it encourages the smart mining instead.

```_mintingEpoch``` : As mentioned under “tokensMinted”, for now, we can safely assume that this will never happen. 

```locked``` : This is used to confirm whether we have initiated a constructor, if yes, we cannot initiate it ever again.

### Other Global Variables
Most were already covered under “Main Constructor”. However the “_burned”, “previousSender”, and “nFutureTime” have not been mentioned.

```_burned``` : Same as “tokensMinted”, however, we are counting how many tokens got burned. While tracking the minted as well as burned, we can get the _totalSupply. 

```previousSender``` : We are keeping a track of the last sender on a chain. Since 2% of a transfer fee is allocated to burning, half of that goes to a previous sender. A sender is a person/entity that sends a certain amount of coins to someone. This always costs them money (Ethereum gas) and 2% of the ButCoins. However, by any luck, they can cover the transfer fees and even earn some ButtCoins since the next sender on a chain will give them 1% of their transfer. This also means that no matter how many times we send the ButtCoins, we are never going to get bankrupt. The initial previous sender is address(0) allocated to burning, and this can be overridden by the contract holder.

```nFutureTime``` : This is used for a pulse check. If there is no difficulty increase in 1097 days (about 3 years), then the mining is either stuck with a difficulty or the coin is not mined for some other reason. This is used to decrease a difficulty should anything like that happen. The idea is vaguely similar to BTC’s difficulty decrease.

### premine Function
``` js 
function premine(address account, uint256 amount) internal {...
```
This will get executed only once, and never again. This function has been created as a kick-start to generate initial tokens.

### mint Function
``` js 
function mint(uint256 nonce, bytes32 challenge_digest) public returns(bool success) {...
```
Unlike “_mint” this is a function that mints tokens as a reward and gives them to a miner. There is no 2% burning fee, since the miners have already wasted electricity and Ethereum gas to mine the coin. It would not be fair to ask for any extra charges. What miners do afterwards, is not ButtCoin’s concern. This, however, may not apply to some mining pools where mined coins are shared and distributed to miners from a single account. Such scenarios are beyond the scope of this white-paper.

### Start New Mining Epoch
``` js
function _startNewMiningEpoch() internal {...
```
With this function, we are increasing the rewardEra by 1. Then, we check whether the overall minted number of coins is more or equal to 1.725436587×10⁶¹ and whether we need a new minting epoch or not (most-likely, we never will). In the next step, we adjust the mining difficulty and change the challenge number. This function is mainly used as an increment to a mining difficulty as well as to calculate a new reward. Reward therefore increases with an increased mining difficulty. It is not necessary to re-apply the same logic to a number of burned coins, since we cannot burn more coins than those we have already minted.

### Re-Adjust Difficulty
``` js
function _reAdjustDifficulty() internal {...
```
Difficulty is increased by decreasing the number 2^n to 2^(n-1) and so on... Initial difficulty is set as 2^234. However, it may happen that we have burned too many tokens and generated fewer. In other words, if we burned 95% of the minted amount, the mining difficulty could be the cause. This is a moment when we have to decrease the mining difficulty. At that point, the mining might be impossible or limited by technology. 95% has been chosen as a number denoting a high statistical relevance. However, it can happen that there are lost tokens and that 95% of burning cannot be reached. To avoid a dead-end, every 1097 days after the last difficulty increase, the coin can decrease difficulty while increasing the n by 50%. This way, a coin cannot be intentionally destroyed or converted to a store of a value. If the 95% is reached, the n from the 2^n is increased by 5% allowing for a decreased difficulty to settle-in.  Each reward would ask for another 5% increase on n, until we have mined enough coins to get out of this 5% increase loop. The n cannot go higher than 213 while in a 5% loop, meaning, we are not wasting Ethereum gas to get out of a loop. Once out of a loop, we will reach the mentioned 95% again. 

### Pulse Check
``` js
function pulseCheck() internal{...
```
Since it is possible to intentionally spread the ButtCoins to multiple accounts so that 95% of the burning does not get accomplished, we can track a difficulty increase. If difficulty does not increase for 1097 days, we intentionally reduce it, so more ButtCoins can be mined, in hope that 95% burning will be reached one day. If the mining is stuck for 1097 days, the n number is increased by 50% so that difficulty decreases to acceptable levels.

Transfer and Transfer-from
function transfer(address to, uint tokens) public returns(bool success) {...
function transferFrom(address from, address to, uint tokens) public returns(bool success) {...

Both of these functions are meant to transfer the ButtCoins from one account to another. However, the ButtCoin has given it a good twist. Each transaction will cost 2% where 1% is burned and 1% is given to a previous account that made a transaction. Burning deflates the coin and increases the market price, while sending the 1% to a previous account may cover the fees and hopefully awards the senders with more than they have spent. The receiver does not get anything from these 2% because they are not getting charged for getting the ButtCoins. We are also performing a pulse-check to see whether the minting got stuck for 1097 days.

#### Other methods are either the getters or the standard methods that do not need an elaboration.

With this white-paper, we have covered a distribution model, differences between a ButtCoin and a Bitcoin as well as the ButtCoin’s model and logic. This information can be beautified with nice graphs and tables, however, it was not a necessary step while writing the white-paper. Therefore, this white-paper was meant for technically-inclined audiences and those who may have some developer skills.

## Addresses
DEV ADDRESS: 
0xca88280E6eEECB75Bf371D2a97AD813c13b99478

EXCHANGES ADDRESS: 
0x06773FDBB50D7bF3d58834D257111419B7455df7

COMMUNITY ADDRESS: 
0x60AF68D5FE8a50310ADC90d5510597229cB1167b

## Previous version of a contract, BUGFIXES
[0x3324f4af7eE967bFA35A5AcCba7Df13e7C932397](https://etherscan.io/address/0x3324f4af7eE967bFA35A5AcCba7Df13e7C932397)

[0xbF633d148a67B551bD643783d2dC3cEAEae31a62](https://etherscan.io/address/0xbf633d148a67b551bd643783d2dc3ceaeae31a62)

Please ignore any 0xBUTT tokens coming from any of those contracts !!!
