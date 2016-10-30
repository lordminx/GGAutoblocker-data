# GGAutoblocker-data

## Background

Early 2015, I started working on collecting and extracting information via the Twitter API, playing around with it without a clear goal in mind. While the main object of study was Gamergate, the massive hategroup/hashtag/"consumer protest"/etc., as it was very much present in my "internet bubble" at the time, I wan't really looking for anything in particular. I liked the topic of network analysis and figured GG might be an interesting subject. 

(I also had the idea of using the dataset to train a classifier for gamergaters. Might still try that some day.)

Alas, personal life prevented me from really analysing the data, so the project lay fallow, wasting a lot of space on my hard disk. (The raw collected data is nearly 20 gigabytes of pickled tweet objects.)

But because I did spend quite a bit of time on the project and felt annoyed by the idea of it being all for waste, I'm trying to exctract and present as much useful data as possible from the dataset, publish it here and then finally make my peace with it.

After all, publishing stuff counts as a ghost of done.

## Methodology

The data represents tweets collected from 11188 accounts and was collected over a couple of days in early february of 2015. With a newly created twitter account, I subscribed to the ["Good Game Autoblocker"](https://blog.randi.io/good-game-auto-blocker/) Blocktogether list curated by Randi Harper and let it add blocks to the account. Once that was done, I used the Twiter API to collect the accounts blocked ids.

For those ~11200 accounts, I now used Twitters API to collect as many tweets as possible. As the API only allows retrieval of the last 3000 or so tweets, that was the number the script aimed for, with some users obviously having less tweets than that.

All in all, this resulted in a collection of roughly 18 million tweets, which where, first saved as pickles and then, for better analysis, as a hdf5 datastore.

Sadly, Twitters Developer Agreement does not allow me to publish the full dataset. (I actually agree that data like this should not be published, but still, it would be so much more convenient.)

Because of this, I have tried to extract as much interesting information from the dataset without running afoul of Twitters TOS or making this too much of a privavy invasion. (Only accounts that were public at time of data collection were scraped, but still...)

I hope that somebody out there might find some interest in this information.

## File Descriptions

### sym_rt_graph.csv

In this file, the symmetric RT relationships in the dataset where extracted and modelled as a social graph. Every line in the csv file represents an edge between two users in the dataset who have retweeted each other.

### user_ids.txt

Contains all the 11188 user ids extracted from the blocklist at data collection. For one method to hydrate the ids into full twitter user objects, see [this Jupyter Notebook](hydrate_twitter_ids.ipynb).

### tweet_ids.txt.xz

The ids of the ~18*10^6 tweets collected, one line per ID. The text file was compressed using xz to be small enough for upload to Github.








mention_graph.csv.xz
sym_rt_graph.csv
user-ids.txt
mentionscount.csv
tweet-ids.txt.xz
wordcount.csv


Account_metadata.csv: created_at/followers/friends/statuses/language/protected/utc_offset\n
