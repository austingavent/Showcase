# Showcase
##Introduction
Welcome to my repo. This project was the love child of a simple idea I had: by selling out of the money options, you could still make money even if your predictors weren't consistent.
By selling options far from the money, one can still collect premiums even if they are wrong about direction of the underlying. Using this logic, I employed several machine learning programs targeting the price on several different time perimeters.  
These programs used features and signals, such as bollinger crossovers, as training. The results are exported in various directories grouped by various different features. The program is designed with a pipeline function that intakes symbols as a list then reads data, generates features, signals, and results.

This was a group project for UC Berkeley's fintech bootcamp. However, my contribution included the entireity of the new processor python file which contains all of the code except for machine learning files used to generate signals.


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
*   ML Libraries: RF and LSTM
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


## Insights and challenges

*   It Pays to Pay for Big Data!
    *   Don’t Use Google Drive
    *   AWS Sagemaker seems to be a better alternative

*   Computational Limitations
    *   Corrupted Data
    *   Long Run Times/Delays with respect to Trial and Error


*   Lessons Learned
    *   Smaller Data Sets
    *   Perhaps Less Breadth and Scale  

##  Further improvement

*   With more time, the goal would be to do more to fine-tune to calibrate variables, as well as think through the scenarios that detect the best fit for each strategy

*   Due to the scale data used, along the way, we encountered a number of obstacles with regard to massaging the data

*   We faced a number of challenging issues involving the code –also do to the breadth














