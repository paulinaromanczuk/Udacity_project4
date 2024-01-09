# Udacity_project4 - We Rate Dogs

This documents briefly describes data wrangling process I did as part of 4th project required for “Data Analyst” Udacity Nanodegree.  
The aim of the project was to gather data from 3 different sources, then assess it and clean it  

Let’s walk quickly through the abovementioned steps  
For gathering data:  
1)	First I loaded “Enhanced Twitter archive” which contained a base of over 2000 tweets from twitter account WE RATE DOGS  
2)	Second step was to load .tsv file from URL and load it to dataframe – this file was containing predictions regarding dog breeds for given tweets  
3)	Third steps was to load data from JSON file that would expand dataframe with at least count of retweets and likes
   
As part of assessing data the task was to assess data both visually and programmatically and find at least 8 quality issues and 2 tidiness issues  
I have documented my findings as below:  
**Quality:**
   - *Archive df:*  
      Remove retweets based on the retweeted_status_id column => if it isn't NaN, then it's a retweet (the 'text' starts with 'RT @").  
      Timestamp is an object type, not datetime.  
      IDs columns with float/integer types need to be changed to string.  
      Change lower-case dog names to "None."  
      Source column should be dropped as it does not contain any valid information.  
      Rating columns should be changed to floats - this was corrected at the source as part of the iteration process.  
      Add a ratio column to get rid of very different denominators.  

  - *Predictions df:*  
      Predictions are in lower/upper case.  
      IDs columns with float/integer types need to be changed to string (not counting this as a separate quality issue).  

   - *df_1:*  
      IDs columns with float/integer types need to be changed to string (not counting this as a separate quality issue).
        
**Tidiness:**        
    Columns puppo/pupper/floofer/doggo => melt them into one  
    Merge all 3 datasets into one, as they are all containing the same observations  

The next step was to actually clean data in a clear “Define-Code-Test” Framework. I have tackled each identified issue as first defining it, then coding the solution and testing it.  
