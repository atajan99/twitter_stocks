# twitter_stocks
# Purpose of this project is to practice accessing data using api connection to well established companies.
# My focus on this data is to pull tweets and analyze specific Twitter users I follow myself. 
# Topics users I follow cower is stock market. 
# My goal is to go through their tweets to:
# 1) make a list of stocks they talk about, 2)  how other followers react to it, 3) general sentiment on stocks and tweets, 4) create chart and find other insights.
# Perhaps analyzing these tweets will help find promising stocks early.
# Bonus part of the project is analyzing crypto currency sentiments.
# Project uploaded here is incomplete to answer all the questions, it is work in progress stored locally on my machine.

# API Instructions that may help I found on internet (ref: https://towardsdatascience.com/tweepy-for-beginners-24baf21f2c25):
# See my notebook file if you want to do a quick run

Step 1: Get your credentials
Get yourself an account: A Twitter user account is a requirement to have a “developer” account, so either register a new account or log-in to an existing one.
Apply for a developer account: Head over to https://developer.twitter.com and apply for a developer account. If prompted, choose a personal or individual account rather than a business one. When submitting an intended use, ensure you answer is sufficiently descriptive, not just some junk or off the shelve copy paste statement.
Create an app: Register an app at https://developer.twitter.com/en/apps. For the required website field you can put a placeholder. After you set up, go to ‘Token and Keys’ to generate an access token and secret. Along with the consumer API keys (already generated), these are the credentials we use to communicate with the Twitter API.

Step 2: Install Tweepy
There are a few libraries available for interacting with Twitter’s API, I prefer Tweepy, it makes reliable calls and is well suited to dealing with tweets that exceed 140 characters.
Just write pip install tweepy into your terminal.
A few other libraries you may need (depending on what you want to do) are json, pandas, time and datetime. We’ll see more about these later.

Step 3: A quick test run
API credentials, check. Tweepy installed, check. Time to see if it works, paste the code below in a notebook, sub in your own keys (watch for typos!) and run. 

import tweepy

#Add your credentials here
twitter_keys = {
        'consumer_key':        '---YOUR-KEY---',
        'consumer_secret':     '---YOUR-KEY---',
        'access_token_key':    '---YOUR-KEY---',
        'access_token_secret': '---YOUR-KEY---'
    }

#Setup access to API
auth = tweepy.OAuthHandler(twitter_keys['consumer_key'], twitter_keys['consumer_secret'])
auth.set_access_token(twitter_keys['access_token_key'], twitter_keys['access_token_secret'])

api = tweepy.API(auth)

#Make call on home timeline, print each tweets text
public_tweets = api.home_timeline()
for tweet in public_tweets:
    print(tweet.text)
    
    
 
# Good luck :) 
