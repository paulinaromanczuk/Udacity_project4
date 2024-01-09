# Udacity_project4 - we rate dogs

This documents briefly describes data wrangling process I did as part of 4th project required for “Data Analyst” Udacity Nanodegree.  
The aim of the project was to gather data from 3 different sources, then assess it and clean it  

Let’s walk quickly through the abovementioned steps  
For gathering data:  
1)	First I loaded “Enhanced Twitter archive” which contained a base of over 2000 tweets from twitter account WE RATE DOGS  
2)	Second step was to load .tsv file from URL and load it to dataframe – this file was containing predictions regarding dog breeds for given tweets  
3)	Third steps was to load data from JSON file that would expand dataframe with at least count of retweets and likes  
As part of assessing data the task was to assess data both visually and programmatically and find at least 8 quality issues and 2 tidiness issues  
I have documented my findings as below:  
  Quality:  
        Archive df:  
           1. Remove retweets based on retweeted_status_id column => if isn't NaN, then retweet (column 'text' starts with 'RT @")  
           2.timestamp is an object type, not datetime  
           3.IDs columns with float/integer types to be changed to string  
           4.change lower-case dog names to "None"  
           5.source column to be dropped as it does not contain any valid information  
           6.rating columns should be changed to floats - this was corrected at source as part of iteration process   
           7. Add ratio column to get rid of very different denominators  
           
       predictions:    
           8. predictions are lower/upper case  
           3. IDs columns with float/integer types to be changed to string (not counting this as separate quality issue)   
          
       df_1:  
           3. IDs columns with float/integer types to be changed to string (not counting this as separate quality issue)  
        
        
    Tidiness  
      1. columns puppo/pupper/floofer/doggo => melt them into one  
      2. merge all 3 datasets into one, as they are all containing the same observations  

The next step was to actually clean data in a clear “Define-Code-Test” Framework. I have tackled each identified issue as first defining it, then coding the solution and testing it.  
