# Social-Sentiment-Impact-on-Cryptocurrency-NFT-value

Cryptocurrencies and NFTs (Non-Fungible Tokens) have exploded in popularity over the past
few years. One notable characteristic of these assets, however, is that they’re extremely volatile.
The USD prices of cryptocurrencies such as Bitcoin and Ethereum, as well as the average prices
of popular NFT collections, can oscillate wildly week by week, and even day by day. In addition
to dealing with price volatility, crypto investors must also deal with a lack of data-driven
information when deciding where to invest their money. Because blockchain technology is still
so young, there is no bonafide tool to utilize to make informed investing decisions. Interestingly,
Twitter has emerged as the leading platform for all crypto-related discussion, and it is common
for individuals to invest in an emerging project based solely on the Twitter sentiment
surrounding that project. Our goal in this project is to utilize data to make more informed
crypto-related investing decisions. To do this, we will first create a comprehensive dataset that
couples Tweets related to different crypto assets with the corresponding price-action of those
crypto assets, over a set period of time. We will then analyze this dataset in order to deduce how
the Twitter sentiment of certain crypto assets affects the performances of those crypto assets.


Dataset:

We have used the NFT dataset available on Kaggle : https://www.kaggle.com/datasets/simiotic/ethereum-nfts
For getting the crypto prices for one year, we have 
scraped the coinmarketcap.com website. 


Code Structure:

Our code was modularized in order to make it more usable and more readable. There are a few
important classes to take note of. The first of these classes is TweetSentimentAnalyzer. This class
was responsible for calculating the average Twitter sentiment for a particular crypto asset, across
a number of defined intervals over a period of time. To use this class, we had to instantiate a new
instance by passing in a Twitter query, a start date, an end date, a time interval, the number of
tweets to aggregate per time interval, and a Twitter API object. With this instance, we could
generate a data frame with each row storing the average positive, negative, and neutral sentiment
percentages for a different time interval.

Another important class to note is NFTPriceAggregator. This class was responsible for
calculating the average price for a particular NFT collection, across a number of defined
intervals over a period of time. To use this class, we had to instantiate a new instance by passing
in an NFT collection name, a start date, an end date, a time interval, and data frames containing
information pertaining to NFT collections and NFT transfers (both loaded from Kaggle). With
this instance, we could generate a data frame with each row storing the average normalized price
for the collection for a different time interval.

A third class to note is CryptoPriceAggregator. This class was responsible for calculating the
average price for a particular cryptocurrency, across a number of defined intervals over a period
of time. This class worked in the same way as the NFTPriceAggregator; the only difference is
that it was instantiated with a data frame containing daily cryptocurrency prices.
A final class to note is CryptoTopicCombiner. This class was responsible for combining the data
frames generated using the classes described above into one analyzable data frame. To use this
class, we had to instantiate a new instance by passing in a dictionary of information related to
different crypto assets as well as a time interval. We also had to pass in unique parameters for
each class mentioned above, because this class was responsible for instantiating and utilizing
instances of those classes. With this instance, we could generate a data frame with each row
storing both the average twitter sentiment and average normalized price for a crypto asset during
a specific time interval. The crypto assets contained in the resulting data frame are the crypto
assets represented in the dictionary passed in when creating the combiner object.


References:

1) https://developer.twitter.com/en/docs/twitter-api/tweets/search/api-reference/get-tweets-se
arch-all
2) https://www.nltk.org/_modules/nltk/sentiment/vader.html
3) https://towardsdatascience.com/step-by-step-twitter-sentiment-analysis-in-python-d6f650
ade58d
4) https://www.kaggle.com/datasets/simiotic/ethereum-nfts
5) https://medium.com/crypto-code/how-to-web-scraping-one-full-years-of-any-pricing-hist
ory-from-coinmarketcap
6) https://coinmarketcap.com/
