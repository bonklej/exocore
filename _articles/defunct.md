---
published: true
subtitle:
topic:
date: 2023-08-21
tags: info
foam_template:
  filepath: '_articles/defunct.md'
  name: Article
---

# Defunct Components
Herein are pieces of the Bonkle infrastructure deemed unnecessary, impractical, or otherwise suboptimal. They primarily concern the Bonkler-backed quasi-ETH-stable design. This protocol utilized market dynamics to ensure price discovery always resolved, at worst, to the floor ratio of 1 $BONKLE: 1 ETH. 

## Exit Window
$BONKLE may swap utilize the Exit Window each day. The queue will empty daily and disperse <a class="wiki-link" href="/articles/treasury">Treasury</a> ether according to the average bids of the most recent successful auction (minus a small fee). Once emptied, this \$BONKLE is permanently burned. This ensures each Exit Window pop enriches tokenholders long on \$BONKLE. Those wishing to exit their $BONKLE positions are incentivized to avoid this fee by trading their tokens for ETH on the open market. This helps maintain the $BONKLE float and  <a class="wiki-link" href="/articles/treasury">Treasury</a> ether - which serves as a de facto shield against  <a class="wiki-link" href="/articles/defunct#burn">burning</a> treasury Bonklers. The Exit Window closes after the final Bonkler is minted.

## Burn Queue
When $BONKLE in the Burn Queue reaches the burn-value of the <a class="wiki-link" href="/articles/reserve">Bonkler Reserve</a> Bonkler with the lowest burn-value, the Bonkler is burned and its burn-value and treasury share are distributed proportionately to Burn Queue depositors. If the treasury were at 0Ξ, then depositors would receive the floor price of 1Ξ per \$BONKLE. Once the Burn Queue is popped, the $BONKLE is burned permanently. If there is sufficient ether in the treasury to cover the burn-value of the Bonkler on deck, the Bonkler is not burned and additional treasury funds are dispersed instead.

**Failsafe**: To prevent the final $BONKLE holders being griefed by the locked $BONKLE liquidity, no-show wallets, or other unforeseeable complications: once Bonklers mint out, the burn queue begins a timer of 14 days (2 <a class="wiki-link" href="/articles/re-auction">re-auctions</a> (but add further failsafe in event 2 <a class="wiki-link" href="/articles/re-auction">re-auctions</a> dont occur)). If the Burn Queue has not popped in this time, the lowest value Bonkler is burned and the proceeds are made immediately available for \$BONKLE redemption. The failsafe timer then resets. In the event there are no more Bonklers remaining in the <a class="wiki-link" href="/articles/reserve">Bonkler Reserve</a>, see <a class="wiki-link" href="/articles/re-auction">re-auction</a> clauses.

**burn attack:** adversarial party deposits large amounts of $BONKLE into the [burn-queue]
- reason: burning prevents a future [re-auction] whose profits may have been priced into current $BONKLE market value. undermines Bonkle project.

## Auction Queue
The intent of Bonkle is to in no way compete with Remilia's current daily Bonkler bidding. As such, this white paper expressly dissuades $BONKLE token holders from utilizing the Auction Queue and instead to wait for the automatic <a class="wiki-link" href="/articles/re-auction">re-auction</a>. However, it remains available all the same if they so choose. 

When $BONKLE deposited into the Auction Queue reaches 2x the current lowest burn-value Bonkler in the <a class="wiki-link" href="/articles/reserve">Bonkler Reserve</a>, the Bonkler is made available for <a class="wiki-link" href="/articles/re-auction">re-auction</a> with a starting price of the Bonkler's burn-value. Proceeds from the sale will be disbursed to the treasury. The auction will begin 23 hours after the auction-target is reached. All \$BONKLE locked in the Auction Queue will be available for the original holders to reclaim.

**Consideration:** There is a clash of incentives within this option - in the event a re-auction was financially savvy, individuals who mustered the capital to trigger the re-auction ought to be incentivized to do so. However, offering financial compensation (say, a larger share of the Bonkler's re-auction proceeds) would then simply incentivize depositing ether in the auction queue regardless as 'What if enough others do the same?' Then there is a rush to the lifeboats and the protocol eats itself.
This issue was eventually addressed by rethinking the protocol into the 'floating Bonkle' implementation. 

**early auction attack:** 2x the least valuable Bonkler $BONKLE is deposited to the [auction-queue] to force an early auction
- reason: an interested party expecting a higher future price for Bonklers after mint-out can force an early auction to acquire a Bonkler from the [bonkler-reserve] at a lower rate. This can be especially powerful in a bear market which it might otherwise be in the best interest of Bonkle to hold Bonklers through.


## Bonkle Social Layer
Bonkle bidders over a 0.1Ξ threshold may claim a customizable soulbound NFT representing their 'Bonkler Pilot'. The NFTs would track their bid history as well as which Bonkler's they contributed to acquiring. This layer could potentially replace/augment the automated <a class="wiki-link" href="/articles/bidder">Bonkle Bidder</a> system via token governance votes weighted by active users contributions.
