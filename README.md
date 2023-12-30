# Showcase
## Introduction
This project enables trade researchers to backtest complex option strategies with easy to configure parameters. While I did build out a ML model to produce signals, the ultimate goal is to empower traders with weeks out predictions/signals, the ability to test various option strategies- including spreads. Currently I am developing to improve CLI functionality with hopes of implementing visualization soon. Long term, I plan to make this a web app with the possibility of deploying paid for services to the public. 

About the financial side:
This project was inspired during a period of frequent trading where I developed an interest in the hedging capabilities of spreads. Spreads cut potential losses, by being open an opposing position further out. You can sell spreads, where you hope to capitalize on time decay of options in hopes of selling an option that will expire. You can sell spreads further from your predicted price, being further away from the money allows a certain amount margin of error. The genesis of this project was c

Technical overview:
The first iterations of this project were done in a fintech bootcamp.That being my first exposure to programming, meant time constraints clashed with inexperience. The biggest problem with the first iterations was managing the large amount of data I purchased- 120gb of csvs. The latest iteration, which I'm still developing, hosts data in a SQL database. 

Technical process:
1. A symbol and time frame starts a query, first we check if the query was already performed- if so then we reproduce the processed data. Otherwise we query the raw data and perform processing for signals

2. Various ML models are trained on the signals, predicting a week and two weeks out if the stock will go down or go up. These models produce signals: 1, 0, -1. 

3. The signals dictate bullish or bearish positions for all spread, call, and puts in a certain range of tolerance and time parameters.

4. Results with metrics are calculated and grouped. This will soon include visualization and tools to gain insights on risk factors regarding each strategy.



## Approach: strategies and tools  

*   Construct functions with changing variables
*   Use iteration to apply the functions to wide sets of data, apply different parameters to the options we dealt, and different approaches to the signals, in order to determine whether strategies could be formed across the range of indicators used.
*   Use and construct a number of different strategies
*   Construct a number of buying strategies by utilizing technical indicators such as Bollinger Bands,  Volume –both the underlying/options, and Put/Call ratios
*   Combine LSTM and Random Forest models –in essence, themselves, technical indicators

##  Libraries and Tools  
*   Tensorflow
*   Google Collab  
    <https://colab.research.google.com/notebooks/intro.ipynb>
*   Iter Tools and Functions - Functions creating iterators for efficient looping  
    <https://docs.python.org/3/library/itertools.html>
*   Streamlit - the fastest way to build and share data apps  
    <https://streamlit.io/>
*   Data Source: Yahoo Finance and Discount Option Data

## Code
* To navigate the code, start with get_data, which sets a directory path and goes through every file with a csv ending. 
* It will then append the row to a bin if it meets the symbol and date criteria. The bins are then added to the dictionary, and 
*the dictionary will be turned to a dataframe saved to a pickle.
* We then process the pickle for various features and ML models, to start creating signals and help with option selection
* With signals and option selection perimeters in place, we choose the calls or puts dataframe for a symbol, then append the profit
* or loss of the value where there is a signal.

## Statistics  

*   Option data available for 4500 different symbols organized by day!
*   We narrowed it to 25 symbols grouped by six sectors over four years
*   We ran five different strategies using nine different compositions of signals, with nine different parameters for options selection
*   Data is MASSIVE! 120GB, 900 million lines in the csv files  

## Process

*   Create .csv files for each sector with the data sets mentioned –price, technicals, etc.
*   Take the data for each sector/name, and apply the various strategies we built, and then log the returns
*   With the results, we intend to gain insight into risk factors regarding each strategy  

##  Example strategies

*   Selling Put Credit Spreads
*   LEAPS
*   LEAPS/Call Calendar Spreads
*   Underlying
*   Underlying/Covered (Short) Calls
*   Underlying/Selling (Short) Puts  

##  Results
There was an overwhelming amount of results when there are many perimeters tested using different strageties and different machine learning programs. The average and mean are slightly above average. More time and energy would need to be applied to refine strageties and targets after learning from our results. Here is a screenshot of the directory of results.

![image](https://user-images.githubusercontent.com/122204322/211847509-ca703cbb-1efb-4381-ba59-69dc49a308d2.png)

Here is an example of a results print out. I will attach a csv of these results, first_final, that will serve as an example.
![image](https://user-images.githubusercontent.com/60438049/211848075-a7719b02-86e3-4b2a-b90c-353b037bec6e.png)

## Insights and challenges

*   It Pays to Pay for Big Data!
    *   Don’t Use Google Drive
    *   AWS Sagemaker seems to be a better alternative

*   Computational Limitations
    *   Corrupted Data
    *   Long Run Times/Delays with respect to Trial and Error


*   Moving Forward
    *   Finish visualizing results
    *   Smaller Data Sets
    *   Perhaps Less Breadth and Scale  

##  Further improvement

*   With more time, the goal would be to do more to fine-tune to calibrate variables, as well as think through the scenarios that detect the best fit for each strategy

*   Due to the scale data used, along the way, we encountered a number of obstacles with regard to massaging the data

*   We faced a number of challenging issues involving the code –also do to the breadth















