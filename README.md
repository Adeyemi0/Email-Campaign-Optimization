## PROJECT OVERVIEW
The business sells Power BI training services and content and utilizes MailChimp for email campaigns and is seeking to enhance its email engagement and overall campaign performance. They aim to optimize email content by analyzing keywords and phrases that correlate with higher engagement and using them strategically in their campaigns. the objective is to improve open rates and click-through rates, leading to increased customer interactions, conversions, and overall business growth. 
The business needs a systematic process to analyze its email campaign data, including subscriber information, campaign activity, open locations, opens, clicks, bounces, and other relevant metrics. They want to identify the keywords and phrases that positively impact engagement metrics, such as open rates and click rates. By understanding the relationship between specific keywords and higher engagement, they can optimize email content for better results.

## THE COMPANY'S GOAL
The desired solution involves leveraging Python and various datasets from MailChimp, including subscriber data, campaign activity, open locations, opens, clicks, bounces, and other relevant information. The solution should provide step-by-step instructions on loading the datasets, pre-processing the email content, calculating engagement metrics like open rates and click rates, analyzing keyword frequency and correlation with engagement metrics, and optimizing email content based on the identified keywords and phrases.
Through the implementation of this solution, the marketing team aims to gain insights into the most effective keywords and phrases that drive engagement. They can then apply these findings to improve their email campaigns, resulting in higher open rates, click-through rates, and ultimately, improved customer interaction and business success.

## FINDINGS
The business has 3,688 subscribers, most of whom are from the United States, Australia, Canada, and India. The subscriber’s rating distribution is shown in Figure 1. MailChimp rates subscribers’ engagement on a scale of 1 to 16 using this metric. They turn the numerical rating into a star rating so that you can quickly see how a contact stacks up against others. Everyone begins with a rating of zero, which is equal to two stars.
They examine subscribers’ click behavior in relation to your sending frequency to place them on the engagement scale. They update the contact ratings for each campaign you send. To think about this in terms of averages is beneficial. For instance, a contact's rating would be affected more negatively if they don't click a link in a monthly email than if they do so in a weekly email.

![](https://github.com/Adeyemi0/Email-Campaign-Optimization/blob/main/Images/rating.png)

As seen in the chart above the majority of the subscribers falls under rating 2 (1830), followed by 5 (574), 4 (565), 3 (471), and 1 (248) respectively.

One(1): This recipient has either unsubscribed and resubscribed, or soft bounced in the past.
Two (2): This recipient is most likely a new subscriber or a previously engaged contact who's gone dormant.
Three(3): This recipient clicks some links in your campaigns. They are either inconsistently engaged or they haven't been in your audience long enough to have earned a higher rating.
Four(4): This recipient often clicks links in your campaigns when you send.
Five(5): This recipient clicks links in your campaigns very consistently.

The most common reason why subscribers churn is that they’re no longer interested in the content.

![](https://github.com/Adeyemi0/Email-Campaign-Optimization/blob/main/Images/churn%20reason.png)

## METHODOLOGY
### Data Pre-processing
The stop_words variable initializes a set of stopwords and a list of punctuation marks. These will be used for text pre-processing to filter out common and insignificant words from the campaign’s email content. The preprocess_text function is defined to tokenize and preprocess the email content. The function converts the text to lowercase, tokenizes it into individual words, and removes stopwords and punctuation marks. This pre-processing step ensures that the subsequent analysis focuses on meaningful keywords that can influence engagement. The code (campaign_df["email_content"]) merges relevant columns from the campaign dataset to create a consolidated 'email_content' column. This column combines the subject line, and preview text of each email campaign. Creating this consolidated column simplifies the keyword analysis process.

![](https://github.com/Adeyemi0/Email-Campaign-Optimization/blob/main/Images/stopwords.png)

### Feature Engineering
Additionally, two new columns, 'open_rate' and 'click_rate,' are calculated. These metrics measure the percentage of unique opens and unique subscriber clicks, respectively, relative to the number of emails sent for each campaign. These rates provide insights into the engagement levels of different campaigns.

![](https://github.com/Adeyemi0/Email-Campaign-Optimization/blob/main/Images/kpi1.png)

### KEYWORD ANALYSIS
To analyze the impact of keywords on engagement, the code creates a list called 'all_words' to store all the preprocessed words from the 'email_content' column of the campaign dataset. A Counter object, 'word_counts,' is used to count the occurrences of each word. The most_common_words variable stores the words and their corresponding frequencies in descending order. This information is crucial for identifying the top keywords that have the highest impact on engagement.
![]()
