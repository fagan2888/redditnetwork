# redditnetwork

Code for managing Reddit dataset (assuming user has access to the Stanford Reddit Data).

## Installing / set-up

Run `pip install -r requirements.txt` to install the necessary dependencies and then you are good to go! 

## Using the code

There are two main use cases for this code:
1) Accessing the Reddit post and comment corpus.
2) Extracting heterogeneous/multilayer networks from the data.

### Accessing and iterating over comments and posts

The `corpus_reader.py` file contains a number of useful classes that allow you to access and iterate over the processed Reddit data.
If you have read access to the Stanford Reddit data (hosted by the InfoLab) then these should work out of the box.
The data is designed so that you can access comments or posts from a specific subreddit for a specific time-period (month).


When you iterate over comments for a particular subreddit/month, 
each comment will be represented by a dictionary with attributes corresponding to comments score, author, timestamp, etc.
The processed text data is accessible via the "doc" attribute, which is a spacy Doc object (https://spacy.io/docs/api/doc).
This Doc object contains the raw text, along with various processed/annotated versions (pos tags, lemmas, etc.).
See the spacy docs for more info.

### Extracting multilayer networks from the data

The `network_extractor.py` file contains code for extracting network data corresponding to one week of activity in a specific subreddit.
See the `network_examply.ipynb` notebook for an example an more information.