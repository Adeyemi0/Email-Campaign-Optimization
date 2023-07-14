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

### Keyword Analysis
To analyze the impact of keywords on engagement, the code creates a list called 'all_words' to store all the preprocessed words from the 'email_content' column of the campaign dataset. A Counter object, 'word_counts,' is used to count the occurrences of each word. The most_common_words variable stores the words and their corresponding frequencies in descending order. This information is crucial for identifying the top keywords that have the highest impact on engagement.
![](https://github.com/Adeyemi0/Email-Campaign-Optimization/blob/main/Images/key.png)

### Calculating Keyword Engagement
The code shown below iterates through the most_common_words list and calculates the average open rate and click rate for each keyword. It uses boolean indexing with the 'str.contains' method to filter the campaign dataset and extract only the rows that contain the current keyword.
The keyword_engagement dictionary is populated with each keyword as the key and a dictionary of its open rate and click rate as the value. This data structure allows for easy access to engagement metrics for each keyword.

![](https://github.com/Adeyemi0/Email-Campaign-Optimization/blob/main/Images/keyword%20engage.png)

###  SORTING AND SELECTING TOP KEYWORDS
The code shown below sorts the keyword_engagement dictionary based on the open rate in descending order. This sorting enables the identification of keywords with the highest open rates.
The associated open rates and click rates for these keywords are extracted from the keyword_engagement dictionary and stored in the lists 'open_rates' and 'click_rates,' respectively.
![](https://github.com/Adeyemi0/Email-Campaign-Optimization/blob/main/Images/sorted%20keyword.png)

The chart below shows the relationship between the open rates and the keywords

![](https://github.com/Adeyemi0/Email-Campaign-Optimization/blob/main/Images/relationship.png)

## BASED ON THE PROVIDED KEYWORDS, HERE'S AN ANALYSIS OF THE INSIGHTS
#### 1. Matches: 
This suggests that subscribers are interested in finding relevant content or solutions that match their specific needs. Tailor your subject lines and preview text to highlight how your training and content can help subscribers find the right solutions. Emphasize how your training and content can help users find matches, patterns, or insights within their data using Power BI.

#### 2. Hosting: 
Subscribers may be looking for information on hosting options for Power BI or related services. Create content or offer training modules specifically focused on hosting and deployment in Power BI. Highlight any hosting features or options that are available for Power BI, such as cloud-based hosting or on-premises hosting.

#### 3. News: 
Subscribers are likely interested in staying up to date with the latest news and updates in the Power BI industry. Recommendation: Include news-related updates in your email subject lines and preview text, such as product releases, feature updates, or industry trends.

#### 4. You'd: 
This keyword implies a personalized approach, suggesting that subscribers may be more responsive to messages that directly address them. Use personalized subject lines and preview text, addressing subscribers by name or using language that emphasizes a personal connection. Use "You'd" to create a sense of exclusivity: Craft subject lines that start with "You'd" to pique curiosity and make subscribers feel like they have access to valuable information or opportunities.

#### 5. Survey: 
Subscribers may be interested in providing feedback or participating in surveys related to Power BI or training content. Regularly engage subscribers by including surveys in your emails, asking for their input, and using their feedback to improve your offerings.

#### 6. Filled: 
This keyword may indicate that subscribers are interested in hands-on activities or practical exercises. Include information about hands-on exercises, practical examples, or interactive elements in your subject lines and preview text to attract engagement. Communicate about filled spots or limited availability: If you have limited seats for your training sessions or exclusive content, create urgency by mentioning that spots are filling up quickly.

#### 7. Notification: 
Subscribers may be looking for important updates or notifications related to Power BI or your training programs. Use subject lines and preview text to highlight time-sensitive updates or notifications that subscribers need to be aware of.

#### 8. Calculations: 
This keyword suggests that subscribers have an interest in learning about calculations and formulas within Power BI. Create content or training modules focused on advanced calculations and provide insights on how to leverage them effectively.

#### 9. Parent: 
This keyword may indicate an interest in understanding parent-child relationships within Power BI or hierarchical data structures. Develop content or training modules that explain and demonstrate how to work with parent-child relationships effectively.

#### 10. Bi/dax: 
This likely refers to the specific language used in Power BI called DAX (Data Analysis Expressions). Highlight DAX-related content, training resources, or advanced techniques in your subject lines and preview text to attract subscribers with an interest in this area.

#### 11. Subtotal: 
Subscribers may be interested in learning about subtotaling and aggregation features within Power BI. The business should offer tutorials, tips, or case studies that showcase how to effectively use subtotals and aggregations in Power BI. Discuss how Power BI enables users to generate subtotals and aggregate data, making it easier to analyze and present summarized information.

#### 12. Secure: 
This keyword implies a concern for data security. The business should emphasize the security measures implemented in your training programs or content, assuring subscribers that their data and information are protected.

#### 13. Measures (mean DAX measures): 
Subscribers are likely interested in learning about measures and calculations within Power BI, particularly in the context of DAX. The business should focus on creating content or training materials that explore advanced measures and calculations using DAX in Power BI.

#### 14. Row-level: 
This keyword suggests an interest in row-level security or filtering capabilities in Power BI. The business should create content or training modules specifically addressing row-level security and demonstrate how to implement it effectively in Power BI projects.

### IN ADDITION TO THESE KEYWORD-BASED RECOMMENDATIONS, CONSIDER THE FOLLOWING INSIGHTS:
1.	Focus on engaging new contacts: Since you have a significant number of recipients with a rating of 2 (1830), it indicates that these are either new contacts or previously engaged contacts who have become dormant. To re-engage these recipients, consider implementing targeted campaigns with compelling content to capture their attention and encourage them to interact with your emails.

2.	Nurture low-engagement recipients: The recipients with a rating of 3 (471) have shown some level of engagement by clicking on links in the campaigns but are not consistently engaged. Develop strategies to nurture these recipients and build stronger connections. Personalize your content, segment your audience based on their interests, and provide incentives to encourage regular interaction.

3.	Maintain engagement of moderate and high engagement recipients: It's encouraging to see that you have recipients with ratings of 4 (565) and 5 (574), indicating moderate and high engagement, respectively. The business needs to continue providing valuable content to these recipients to maintain their interest and encourage their consistent engagement. Also, consider segmenting this group further to deliver more targeted content that aligns with their preferences.

4.	Re-engage recipients with a rating of 1: Recipients with a rating of 1 (248) have either unsubscribed and resubscribed or experienced soft bounces in the past. Implement strategies to win back these recipients. Send personalized re-engagement campaigns, offer exclusive discounts or rewards, and remind them of the value they can receive by staying subscribed.



