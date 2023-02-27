# Stock prediction for TechInvest
### TechInvest Holdings wants to predict the future price of the NASDAQ to better position themselves in the tech stock field. They have tasked me with creating a time series model to predict future prices of the NASDAQ to make informed investing decisions. TechInvest would like to forecast the next seven days.  
# Data Understanding
###  Below is the raw data brought in from the NASDAQ.
![data](https://user-images.githubusercontent.com/96254640/221614977-b451d064-1965-4b4b-9f09-d99cebc42c96.PNG)
#### The data set includes :
#### Date:  This is the date of the trading.
#### Open:  This is the price of each stock at the open of the trading day.
#### High:  This is the highest price each stock achieved during the trading of the day.
#### Low:  This is the lowest price each stock achieved during the trading of the day.
#### Close:  This is the price of each stock when official trading hours are done for the day.
#### Volume:  This is the amount of each stock that was traded during trading hours for the day.
#### Dividends:  This is the amount paid to shareholders when a company pays profits to its shareholders.
#### Stock Splits:  This is an action that occurs when a company increases its numbers of shares through liquidity.
### Since TechInvest is interested in forecasting the next seven days, the study will focus primarily on the Close and Volume of the stocks.

## Volume
![volume](https://user-images.githubusercontent.com/96254640/221618261-426c8629-c0fd-45b7-b1fe-baab1c35fc74.png)
#### Here we see the historical volume of the NASDAQ from 2002 to 2021.
## Closing
![closing](https://user-images.githubusercontent.com/96254640/221618678-29a0aa6c-2e95-45f3-a652-a7a77429d132.png)
#### Here we see the historical closing price for the NASDAQ from 2002 to 2021.
## Data Preparation
####  The code creates sliding window data for the training and testing sets using a window size of 30. It then creates an LSTM model using Keras and trains it on the training data. After training the model, it creates sliding window data for the testing set and uses the trained model to predict the closing prices.  This will then be used to create our LSTM model.
## Modeling
#### The code creates an LSTM model with one LSTM layer and one Dense layer. It uses the mean squared error (MSE) as the loss function and the Adam optimizer. It trains the model for 50 epochs with a batch size of 32.
## Evaluation
![predictionvactual](https://user-images.githubusercontent.com/96254640/221621556-fd9a3e21-02cd-414c-afcb-09d8b9acf40c.png)
#### The code evaluates the performance of the model using the RMSE of the predicted closing prices and the actual closing prices for the testing set. It also plots the predicted and actual closing prices for the testing set.
## Deployment
![eval](https://user-images.githubusercontent.com/96254640/221621965-413ef5bd-ecb5-4acd-b052-e5a9dc773854.png)
## Conclusion
#### The model has shown a good RMSE based on the models performance. The models predictions follow the actual trends quite well, without overfitting. However, stock market model predictions based on only a few variables can only tell so much. Given the influences of public sentiment, governmental policies, and unforeseen events, this model takes into account only the factors that have been given it; the closing price and traded volume within the historical data.
## Further Actions
#### Further actions that would make this model more accurate would be to incorporate mechanisms that allow the data to be scraped and incorporated such as public sentiment (e.g., twitter analysis, proposed legislation, and other current economic factors).
