# Closing the Loop
## Goals of the analysis
In this project, I will be working towards building a system that autogenerates a report and emails it to myself if the tweet meets some types of criterion (threshold). Since I do not have access to LMS data, I will be downloading data from Twitter. 

## Packages
```
install.packages("ROAuth")
install.packages("twitteR")
install.packages("sendmailR")
install.packages("cronR")
```

## Procedures
1. Twitter Setup
  * Step 1. Create a Twitter account at Twitter.com and register as a developer at the following link: https://developer.twitter.com/

  * Step 2. Register a new app (we need to create an app to access the API as that is what the primary us of the API is) at https://apps.twitter.com/

  * Step 3. Within R, install the packages ROAuth and twitteR
  * Step 4. Copy the following details from my Twitter App page
```
api_key <- ""
api_secret <- ""
access_token <- ""
access_token_secret <- ""
setup_twitter_oauth(api_key, api_secret, access_token, access_token_secret)
```
2. Download Tweets
```
TL <- searchTwitter("education data", n=50, since='2019-04-19', until='2019-04-25')
```
3. Visualize Tweets over time
4. Setup auto-email (need to install both the sendmailR and cronR packages)
```
address <- paste("<", address, ">", sep = "")

from <- "<xt2213@tc.columbia.edu>"
to <- address
subject <- "Twitter data visualization"
body <- c(
  "Latest Twitter notification.")

sendmail(from, to, subject, body)
```
5. Set the scheduler to send an email triggered by an activity threshold on Twitter.

## Background
Many scholars believe that learning analytics will not demonstrate real utility until it can "Close the Loop", use data to automate decision making. A common example of this system are email generators that send emails to students in response to an activity (or lack of activity). Several universities have had some success with this strategy such as George Washington University. There are an infinite number of these lopp closing activities that could be implemented and there is a lot of work to be done understanding when they are most useful.  

## Readings

* [RMarkdown Cheat Sheet](https://www.rstudio.com/wp-content/uploads/2016/03/rmarkdown-cheatsheet-2.0.pdf)

* [cronR Documentation](https://rdrr.io/cran/cronR/f/README.md)

* [sendmailR Documentation](https://cran.r-project.org/web/packages/sendmailR/index.html)

* [Whitehill, J., Williams, J. J., Lopez, G., Coleman, C. A., & Reich, J. (2015). Beyond prediction: First steps toward automatic intervention in MOOC student stopout.](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=2611750)

* [Liu, R., & Koedinger, K. R. (2017). Closing the Loop: Automated Data-Driven Cognitive Model Discoveries Lead to Improved Instruction and Learning Gains. Journal of Educational Data Mining, 9(1), 25-41.](https://eric.ed.gov/?id=EJ1155896)

* [Lawson, C., Beer, C., Rossi, D., Moore, T., & Fleming, J. (2016). Identification of “At Risk” Students Using Learning Analytics: The Ethical Dilemmas of Intervention Strategies in a Higher Education Institution. Educational Technology Research and Development, 64(5), 957–968.](https://doi.org/10.1007/s11423-016-9459-0)

## Videos

* [MuleSoft Videos. (2015). What is an API?](https://www.youtube.com/watch?v=s7wmiS2mSXY)

* [Peng, R. (2015). R Markdown with RStudio](https://www.youtube.com/watch?v=DNS7i2m4sB0)

* [Jalayer Academy. (2016).Twitter Mining with R](https://www.youtube.com/watch?v=lT4Kosc_ers)

## Author
[Katherine Tan](www.linkedin.com/in/katherine-tan-2019), M.S student in Learning Analytics at Teachers College, Columbia University
