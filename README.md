# get-metrics
Simple Python script for getting Tweet metrics from Twitter Developer Labs endpoint...


## Getting started

* Join Twitter Developer Labs at https://developer.twitter.com/en/labs.
* Create a Twitter App. Go to https://developer.twitter.com and log in, then look for the "Apps" option in the dropdown menu.
* For your App, generate consumer key and secret, and also generate user access and secret tokens. You'll need all four keys to make requests to the metrics endpoint. 
* Connect the App to your activated Labs metrics endpoint. 

## Running the script.
This script supports a single command-line argument, ```-t``` (or ```--tweets```), that specifies the Tweets you want metrics for. 

+ Clone the repository. 
+ Run `pip install requirements.txt` to install the third-party library dependenices.
+ Create a .env file and fill in your private credentials. .env.example is provided as a template.
+ Execute the script: c>python3 get-metrics.py -t 1162377768081879040,1164305485266165760,1164214825804693509
+ Go admire the wonderful engagement numbers:

```json
{
  "data": [
    {
      "tweet": {
        "impression_count": 564,
        "like_count": 6,
        "quote_count": 2,
        "reply_count": 0,
        "retweet_count": 0
      },
      "tweet_id": "1162377768081879040"
    },
    {
      "tweet": {
        "impression_count": 1888,
        "like_count": 7,
        "quote_count": 0,
        "reply_count": 0,
        "retweet_count": 1
      },
      "tweet_id": "1164305485266165760"
    },
    {
      "tweet": {
        "impression_count": 3174,
        "like_count": 73,
        "quote_count": 0,
        "reply_count": 10,
        "retweet_count": 1
      },
      "tweet_id": "1164214825804693509"
    }
  ]
}
```


## Dependencies
- Python 3 (recommended >= 3.6 for f-string support)
- Requests package. 
- .env configuration functionality based on `python-dotenv` package.
    

```python
import argparse
import json
import os
import requests
from requests_oauthlib import OAuth1
from dotenv import load_dotenv
```
  
  
## Configuration
Create a file named ".env" at the root of the repository directory with the relevant credentials (see '.env.example'). Here's the example '.env' for reference:

```
# Twitter app creds for app uploading and posting Tweets. 
TWITTER_CONSUMER_KEY=""
TWITTER_CONSUMER_SECRET=""
TWITTER_ACCESS_TOKEN=""
TWITTER_ACCESS_TOKEN_SECRET=""

```
