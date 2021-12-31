# take-over-bid
Implementation of mandatory/voluntary take-over bidding in an ERC20 token

## Principles
- A take over-bid is the process of buying as many token as possible, for a set price, by a single address
- As in tradfi take-overs, the ultimate goal is to possess the whole supply
- Any address reaching a balance of min 30% of the total supply triggers an automatic take-over bid and has the obligation to lock an amount of bid * (totalSupply - bidder balance). As long as this amount is not locked, the address balance occurs the Generic Penalty (infra). An automatic take-over bid last for one cycle.
- Any address can trigger a voluntary take-over bid at anytime, by locking a minimum of the required amount as defined supra. A voluntary take-over bid last for a custom duration, set by the bidder.
- The minimum bid amount is the uniswap 24h twap * 1.10. In case of an automatic take-over bid, the amount might then be at a discount or at a premium to the current Uniswap price. This is particularly true in more volatile assets.
- If at the end of the take-over bid, the bidder hold more than 90% of the total supply, an automatic bidding reopening is conducted (at the same price and duration as the initial one), in order for more participant to enter the process.
- The Generic Penalty is freezing of transfers and loss of the corresponding voting power.
- A cycle is defined as
-

## Implementation details
- Onchain voting and execution are conducted through a minimalist multisig - this is a POC
- 
