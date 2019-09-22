# Untouchable-private-pension-plan
Untouchable private pension plan as an Autonomous Agent on Obyte.

*Address:* [YQRB6IXMAE32QCB3A6MKXVY3FJSL3C7Y](https://testnetexplorer.obyte.org/#YQRB6IXMAE32QCB3A6MKXVY3FJSL3C7Y)

*Definer unit (testnet)*: [FspkCY41TBrJ8oma9icVCj97GiFk+dvzDCCGnaAipcY=](https://testnetexplorer.obyte.org/#FspkCY41TBrJ8oma9icVCj97GiFk+dvzDCCGnaAipcY=)

Private pension plans are very important nowadays. The state pension is in the most countries not sufficient anymore to have enough to maintain a certain lifestyle once you stop working.

Interest rates are very low today and state pension plans are good, but also have a certain risk as of inflation and potential financial crisis.

So having part of your pension plans as a private untouchable crypto pension plan defineteley makes sense.

This AA covers exactly those points:
 * Create a private pension plan: Define owner address (only this address can withdraw later) and an "expiry date" that defines how long the funds are locked
 * Anyone can deposit to each private pension plan
 * The defined owner address can withdraw the deposited amount only after the defined expiry date completely or partly
 
 
 ## Create a private pension plan
 
 Triggered by someone who wants to create a new pension plan.
 
*Parameters*
 
  * `owner` - wallet address of the owner / creator of this pension plan
  * `period` - the length of the period that the pension plan does not allow withdrawals in seconds
  
*Response*

 *`reference`- the pension plan reference to be used in subsequent requests to deposit or withdraw to / from the pension plan. The pension plan creator is supposed to save this reference.


## Deposit to private pension plan

Triggered by anyone who wants to deposit money to a pension plan. Can be done by anyone.

*Parameters*
 
  * `reference` - pension plan reference
  * `deposit` - any input, just to let the AA know, that you want to deposit money
  
The amount of bytes you send has to be >10.000, that the balance of the pension plan increases, as the minimum fee is 10.000.
  

## Pension plan owner withdrawal

Can only be triggered by the wallet with the defined address from the first step "Create a private pension plan".

*Parameters*
 
  * `reference` - pension plan reference
  * `withdraw` - any input, just to let the AA know, that you want to deposit money
  * `amount` - optional field - amount that has to be withdrawn, if empty full balance will be withdrawn
  
*Response*

If the expiry date of the pension plan is reached, a payout is possible and it will send back the amount or full balance.
If the expiry date of the pension plan is not yet reached, a payout is not possible.
