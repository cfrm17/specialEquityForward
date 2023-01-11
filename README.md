# Equity Forward with Settle Date Lag and Dividend Percentage

Two new features are added in the equity forward pricing model.  One feature is settle date lag, which is introduced to match market conventions as forward contracts are sometimes settled with a delay.  The other feature is dividend percentage, which allows the model user to use part of the real dividend for calculation.


Suppose the initial trade date is set to time zero, the maturity of the forward is T.  If there is a delay of   for the forward contract to be effective, and a delay of   for the contract to be settled, the forward price is calculated by

	                             (1)

where   is the initial stock price,   is the amount of the  dividend whose ex-date lies between the trade date and the maturity date,   is the payment time of the  dividend, and   is the forward interest rate (see https://finpricing.com/lib/IrBasisCurve.html) between time u and v.  At time t, if there is a delay of   for the contract to be unwound, the unwinding value of the forward is calculated by

	              (2)

where   is the stock price at time t.

For an equity forward contract matured at a time T with a settle date lag  , there is no cash/asset exchange until  .  For a long position, the net value of the contract at the time of   is

	 	(3)

where   is the forward price of the equity determined at time T, matured at  , i.e., the  -term forward price at T.  Hence, the mark-to-market value of the contract at T is given by

	 	(4)

where   is the zero-coupon bond price at T matured at  .

If we interpret   as  , i.e.,  -term forward price of an equity at the current time zero, we obtain equation (1) to calculate the forward price.  However, during the contract period where mark-to-market price needs calculated, the “spot” value of the forward should be given as

 
             				(5)

If a dividend percentage   is specified in a GED token file for equity forward, all the dividend amounts have to be adjusted as

	 	(6)

