---
published: true
subtitle:
topic:
date: 2023-08-19
tags: infrastructure
foam_template:
  filepath: '_articles/entrance-queue.md'
  name: Article
---

# Entrance Queue

The entrance queue is the primary source of $BONKLE issuance. Its contents are used to fuel  the <a class="wiki-link" href="/articles/bidder">Bonkle Bidder</a>. A depositor is said to have an 'account' with the queue whereby they may have:
- Ether locked in the queue
- Ether unlocked in the queue
- Ether remaining in the account, but not allocated for queue utilization
- $BONKLE tokens

This system is intended to offload gas costs to the user. All ether not expended by the <a class="wiki-link" href="/articles/treasury">Bonkle Treasury</a> as gas remains claimable value for tokenholders.

## Queue Sequencing
The queue will always prioritize utilization of ether (and subsequent payout of $BONKLE) with the best bid price. This enables price discovery at the point of *issuance*. Bidding above the floor price indicates an expectation of an even greater windfall received at a later date.

**Example:**

    A depositor enters the queue with a bid of 5Ξ at 1Ξ for 0.7 $BONKLE exchange rate (the minimum price). Soon after, a new depositer inputs a bid of 3Ξ at 1Ξ for 0.6 $BONKLE and therefore moves ahead of the first depositer in queue. 
    
Note that it is not relevant that the first depositor bid earlier nor that they bid more ether. Bids of equal exchange rates are sequenced by order of deposit time.
    
## Locking (*optional*) 
Rather than attract the large sums of capital required to win a Bonkler each day, depositors' ether is locked over a decaying period. Each day following a deposit, 20% of the principle is made available for withdrawal from the queue. If a depositor elects not to withdraw (or de-allocate) their ether, it remains in the queue until it is utilized in the successful acquisition of a Bonkler. 

*Optional:* Daily queue-locked decay rate can be made to vary according to the previous day's Bonkler's distance from the 7-day moving average price.

**Example 1:**

    Three bidders enter the queue with bids of - #1: 2Ξ, #2: 3Ξ, and #3: 6Ξ (all at a bid price of 0.7 $BONKLE per 1Ξ and in the order listed) for a total of 11Ξ in the entrance queue. The Bonkle Bidder wins the day's auction at a price of 10Ξ. The bidders receive the following: #1: 1.4 $BONKLE, #2: 2.1 $BONKLE, #3: 3.5 $BONKLE. Since not all of Bidder #3's ether was utilized in the day's purchase,Bidder #3 remains with 1Ξ locked in the queue. 

**Example 2:** 

    On day 0, a depositor adds 5Ξ at a bid of 0.6 $BONKLE per ETH to the entrance queue. The day's bid fails. On day 1, the account is locked into an 80% allocation (4Ξ) contributed to the day's bid. The depositor withdraws the unlocked 1Ξ. The day's bid fails. On day 2, there is now 3Ξ locked and 1Ξ available for withdrawal. The depositor does not interact with the queue. The day's bid is won, however the depositor was on the cusp of the necessary bids so only some of their ether was utilized. 1Ξ of their 4Ξ participating (3 locked + 1 unlocked) in the day's bid is contributed to the bid. The locked ether was prioritized. On day 3, the depositor now has 3Ξ and 0.6 $BONKLE in their account. The account has 1Ξ locked and 2Ξ available for withdrawal. The depositor opens their account this day, and alters their bid price to 0.65 $BONKLE per ETH and withdraws their 0.6 $BONKLE. The day's bid succeeds but, again, only 1Ξ of their deposit is utilized. On day 4, the account has 2Ξ and 0.65 $BONKLE. The depositor adds a 8Ξ  in a bid at 0.55 $BONKLE per ether. The day's bid succeeds, but only 3Ξ is utilized and the lower bid is prioritized. On day 5, the account now has 4Ξ locked at 0.55:1, 1Ξ unlocked at 0.55:1, 2Ξ unlocked at 0.65:1, and 2.3 $BONKLE (0.55x3+0.65). The depositor withdraws 1Ξ and all $BONKLE then re-allocates the remaining unlocked ether (2Ξ) to 0.6:1. Their account now has 4Ξ at 0.55:1 and 2Ξ at 0.60:1 for a total of 6Ξ. On days 6, 7, 8, and 9, they do not interact with the wallet and every bid either fails or does not utilize their ether. On day 10, all their ether has been unlocked and they withdraw. Their wallet has deposited 13Ξ in total and withdrawn 8Ξ and 2.9 $BONKLE (for an average price of 0.58 $BONKLE per 1Ξ). 


## Price Target Sentiment Sampling (*optional*)
To source entrant sentiment for the value of the day's Bonkler, bidders will input a price curve for their desired $BONKLE. While implementing continuous curves would be preferable to the discrete function in the example below, the essence remains consistent.

**Example:**

    A depositor enter the queue with bid at: 1Ξ for 0.6 $BONKLE if the final sale price is <= 15Ξ; 1Ξ for 0.65 $BONKLE for a total sale price <= 20Ξ; 1Ξ for 0.7 $BONKLE at final <= 25Ξ; and lastly no bid for any final sale > 25Ξ. 

This mechanic protects depositors from attacks which would deposit large amounts of ether to dilute the supply of $BONKLE (*see <a class="wiki-link" href="/articles/attacks">inflate attack</a>*). This would require dynamic bid sequencing according to current bid price.



