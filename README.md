# take-over-bid
Implementation of mandatory/voluntary take-over bidding in ERC20 token as voting power

## Principles
- A take over-bid is the process of buying as many token as possible, for a set price, by a single address
- As in tradfi take-overs, the ultimate goal is to possess the whole supply
- Any address reaching a balance of min 30% of the total supply triggers an automatic take-over bid and has the obligation to lock an amount of bid * (totalSupply - bidder balance). As long as this amount is not locked, the address balance occurs the Generic Penalty (infra).
- Any address can trigger a voluntary take-over bid at anytime, by locking the amount as defined supra
- The bid amount is the uniswap 24h twap * 1 sigma
- The Generic Penalty is freezing of transfers and 
