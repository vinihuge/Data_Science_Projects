>DISCLAIMER 
This is a study of IBOVESPA futures index. You should note trade based on just this study, this is not a recomandation of investment.

=======================================================================================
> OBJECTIVE:

- High precision predicting if the day will go up in the next day.

=======================================================================================
> CONSIDERATIONS: 

- The project started creating the best scenario to use as a benchmark and understand how far away our algorithms return was from predicting all days correctly. 

- Feature Engineering was made based on classical Technical Analysis on diferent periods.

- Since predicting up or down day is to abstract, i wanted to restric more the target so that we could tell the machine learning models what we were looking for(a clear trend day) and not just a lateral day that randomly closed just a little above its open. Thinkng on this, i decided to cluster "up Days" when its High was 700 points above its open, defining that clearly that day was a up trend day.

- When the first machine learning model was fited and ploted the accumuleted profit, was clear that the capital curve was too volatile, so i decided to set a stop loss for the day, that was 500 point. Once we stabilished the daily stop loss, the profits started to grow. 

- Even in the notebook was printed in every ML model the accuracy, this is not relevant to this project since the goal is to have a high hit on our predictions, so the perfect metric is the precision predicting 1, that are the up trend days. The Lowest precision was 64% and the highest was 86%.

- The problem with the model that performed 86%(Logistic Regression) is that it traded few times, its so casual that may not represent the real world. On the other hand, the problem with the most profitable algorithm(SVM) is that his strategy was based on predicting all the days to up trend days, and its profit was based on the risk management and not his capability to predict future returns, and when the market cicle change it may not be able to capture this movements. 

- The best algorithm was Random Forest, with 66% of precision and 71% of recall. It was able to reasonably cluster the days and have a good capital curve lossing only to SVM.

=======================================================================================
> CONCLUSION:

- Even this project been in an inicial fase, it was able to have profit in all algorithms. The precision is median but the recall is still to low, maybe adding more features and understanding what precede up trend days would be easyer to perceive the project. Its important to say that slippage and fees were not taking on count and should be verify either if in the real world the algorithm would not had been stopped out before taking profit. Visualizing the relationship between high of the day and close of the day its obvius that close will be always lower or equal than the high of the day, but the mean difference between them is to high(500 points/38%), so a good strategy would be take profit on the mean high of the days and not let the trade come back in direction of the starting point. It is important to stress that the risk management has fundamental importance on the strategy, our risk/reward is 1x3, wich makes a 66% precision strategy much profitable. Also, in the test period the strategy never had a negative Month wich makes the strategy even better.

=======================================================================================
> IMPROVEMENTS FOR UPCOMING PROJECTS:

- Define a function that verifys wheter we got stopped out before the day closed up and computed our profit;
- More Feature Engineering based on statiscal thinking and math;
- Create a Neural Net;
- Increase the Recall without decrease the Precision;
- Create strategy to take profits before the day close;
- Add slippage and fees;
- Add Trailing Stop;




