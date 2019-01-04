# Balance Limit for Gekko

I modified the trader.js in Gekko so let's say you have $100 USD (or the fiat currency of your choice) 
and you only want Gekko to use $10, you just set that in the currentBalance variable. Now Gekko will only 
use $10 even though you have $100 available. The winning/losing trades will adjust the currentBalance so
winning trades will allow Gekko to use what it won as part of the next trade and if it loses, it won't
eat into your portfolio as the currentBalance variable will be adjusted based on how much it sold the
crypto for.

The reason for this is to allow you to test multiple strategies live using the same API key. You will
run into IP blacklist issues if you run too many Gekko bots from the same IP address if the exchange
has a low rate limit, but you should be able to test 3 - 5 strategies easily with this modification.

Note: This trader.js also writes trades to a CSV file. You will need to install fs (npm i fs) in your
Gekko folder. Instructions for that are in this video: https://www.youtube.com/watch?v=662t8cQ0DRk
