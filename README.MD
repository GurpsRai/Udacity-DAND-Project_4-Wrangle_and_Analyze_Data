
## Wrangle and Analyze Data

This project was submitted for the Data Wrangling element of Udacity’s Data Analyst Nanodegree.

### The Project Requirements & Dataset Overview: 

**To gather, assess and clean data, and act on it data through analysis and visualisation.**

The dataset used for this project is the tweet archive of Twitter user @dog_rates, also known as WeRateDogs.  

WeRateDogs is a Twitter account that rates people's dogs with a humorous comment about the dog. The ratings almost always have a denominator of 10. The numerators however are almost always greater than 10. 11/10, 12/10, 13/10, etc. Why? Because "they're good dogs Brent." WeRateDogs has over 4 million followers and has received international media coverage.
WeRateDogs downloaded their Twitter archive and sent it to Udacity via email exclusively for use in this project. This archive contains basic tweet data (tweet ID, timestamp, text, etc.) for all 5000+ of their tweets as they stood on August 1, 2017.

### Context
**Goal:** To wrangle WeRateDogs Twitter data to create interesting and trustworthy analyses and visualisations. The Twitter archive only contains very basic tweet information. Additional gathering, then assessing and cleaning are also required for worthy analyses and visualisations.

### The Data
**Enhanced Twitter Archive**

The WeRateDogs Twitter archive contains basic tweet data for all 5000+ of their tweets, but not everything. One column the archive does contain though: each tweet's text, which were used to extract rating, dog name, and dog "stage" (i.e. doggo, floofer, pupper, and puppo) to make the Twitter archive "enhanced." Of the 5000+ tweets, the tweets were pre-filtered with ratings only (there are 2356).

**Additional Data via the Twitter API**

Of the Twitter archives, retweet count and favourite count were two of the notable column omissions, this data was gathered from Twitter's API.

**Image Predictions File**

Every image in the WeRateDogs Twitter archive was pre-run through a neural network that can classify breeds of dogs. The results: a table full of image predictions (the top three only) alongside each tweet ID, image URL, and the image number that corresponded to the most confident prediction (numbered 1 to 4 since tweets can have up to four images).

**Image Predictions Data Columns:**

- tweet_id: is the last part of the tweet URL after "status/" → https://twitter.com/dog_rates/status/889531135344209921
- p1: is the algorithm's #1 prediction for the image in the tweet → golden retriever
- p1_conf: is how confident the algorithm is in its #1 prediction → 95%
- p1_dog: is whether or not the #1 prediction is a breed of dog → TRUE
- p2: is the algorithm's second most likely prediction → Labrador retriever
- p2_conf: is how confident the algorithm is in its #2 prediction → 1%
- p2_dog: is whether or not the #2 prediction is a breed of dog → TRUE
- etc...

### Key Points

**Key points to keep in mind when data wrangling for this project:**

Only want original ratings (no retweets) that have images. Though there are 5000+ tweets in the dataset, not all are dog ratings and some are retweets.
Assessing and cleaning the entire dataset completely would require a lot of time. Therefore, the requirements of the project are only to assess and clean at least 8 quality issues and at least 2 tidiness issues in this dataset.
Cleaning includes merging individual pieces of data according to the rules of tidy data.
The fact that the rating numerators are greater than the denominators does not need to be cleaned. This unique rating system is a big part of the popularity of WeRateDogs.
No need to gather tweets beyond August 1st, 2017. 

## Project Details

**Project tasks:**

**Data wrangling:**

* Gather data
The WeRateDogs Twitter archive to be downloaded manually - twitter_archive_enhanced.csv

The tweet image predictions - image_predictions.tsv - hosted on Udacity's servers and to be downloaded programmatically using the Requests library and the following URL: https://d17h27t6h515a5.cloudfront.net/topher/2017/August/599fd2ad_image-predictions/image-predictions.tsv

Each tweet's retweet count and favorite ("like") count at minimum, and any additional data you find interesting. Using the tweet IDs in the WeRateDogs Twitter archive, query the Twitter API for each tweet's JSON data using Python's Tweepy library and store each tweet's entire set of JSON data in a file called tweet_json.txt file. Each tweet's JSON data should be written to its own line. Then read this .txt file line by line into a pandas DataFrame with (at minimum) tweet ID, retweet count, and favourite count. Note: not to include Twitter API keys, secrets, and tokens in your project submission.

* Assess data
After gathering each of the pieces of data, assess them visually and programmatically for quality and tidiness issues. Detect and document at least eight (8) quality issues and two (2) tidiness issues to wrangle_act.ipynb Jupyter Notebook. To meet specifications, the issues that satisfy the Project Motivation (see the Key Points header on the previous page) must be assessed.

* Clean data
Clean each of the issues you documented while assessing. Perform this cleaning in wrangle_act.ipynb as well. The result should be a high quality and tidy master pandas DataFrame. Again, the issues that satisfy the Project Motivation must be cleaned.

* Store, analyse, and visualise the wrangled data
Store the clean DataFrame(s) in a CSV file with the main one named twitter_archive_master.csv. If additional files exist because multiple tables are required for tidiness, name these files appropriately. Additionally, you may store the cleaned data in a SQLite database (which is to be submitted as well if you do).

Analyse and visualise wrangled data in your wrangle_act.ipynb Jupyter Notebook. At least three (3) insights and one (1) visualization must be produced.

* Reporting on 1) data wrangling efforts and 2) data analyses and visualizations

To create a 300-600 word written report called wrangle_report.pdf or wrangle_report.html that briefly describes your wrangling efforts. This is to be framed as an internal document.

To create a 250-word-minimum written report called act_report.pdf or act_report.html that communicates the insights and displays the visualization(s) produced from your wrangled data. This is to be framed as an external document, like a blog post or magazine article, for example.

Both of these documents can be created in separate Jupyter Notebooks using the Markdown functionality of Jupyter Notebooks, then downloading those notebooks as PDF files or HTML files (see image below).

### Datasets: 
twitter-archive-enhanced.csv
image_predictions.tsv
tweet_json.txt
