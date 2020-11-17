# Political-Polarization-

```{r}
# load twitter library - the rtweet library is recommended now over twitteR
library(rtweet)
# plotting and pipes - tidyverse!
library(ggplot2)
library(dplyr)
library(readr)
# text mining library
library(tidytext)

twitter_token <- create_token(
  app = "Miladn5",
  consumer_key = "SdREvqn8hS4b368N0Zob0NM6t" ,
  consumer_secret = "qvsF39e5Dc3f3Y2bySdqSa9Lxbsiw1HiSYjNTaBCjE5ifRhAOd" ,
access_token="1189228289568755712-kqRUC2oxVsOOhzo0dyXxUga9cNxdwj", 
access_secret="jCjZZzcw1r7JPYKFY2OLkNj2DW5v4QLdtwSinGBozw3qi",
  set_renv = TRUE)

## search for 500 tweets using the #rstats hashtag
Our_tweets <- search_tweets(q = "@SarahPalinUSA",
                               n = 500, include_rts = FALSE)


Our_tweets <- search_tweets(q = "#Presidentialdebate2020",
                               n = 500, include_rts = FALSE)

Our_tweets = as.matrix(Our_tweets) ## store tweets in a matrix

#glimpse(Our_tweets)
write.csv(Our_tweets, file = "SarahPalin.csv")
```
