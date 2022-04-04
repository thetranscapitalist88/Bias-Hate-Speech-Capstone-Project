**Technical Report**

**Problem Statement**:
As we create code, little do we notice that we put a piece of ourselves within that code. With that being said, this is how we introduce our humanity to machine learning. Computers do not have biases unless they're coded to do so, which makes me think, how can we reduce the biases within algorithms—mainly aimed at social media where everyone is allowed to express their opinion. 

One group, Figure Eight Inc., has taken this task upon them as they created a hate speech algorithm to help eliminate hate speech in social media. So I ask the question: Does the Figure Eight Inc hate speech algorithm misclassify hate speech or offensive language tweets, and in doing so, is this harmful to marginalized communities? 

I dissect Figure Hate Inc.'s hate speech algorithm through natural language processing (NLP) multi-classifier. Multiple models will be used, such as CountVectorizers with Logistic Regression. The metrics that I  heavily focus on are accuracy, precision, and recall. 

**Background**
Speech is the essence of social media. Everyone has an opinion and is creating posts or tweets to express themselves. But what happens when someone has a negative view of a person or targeted group? How can one company monitor millions of people's thoughts? This is where algorithms can come in and save the day to make monitoring of speech so much easier. Although, what happens if the person, people, or company is biased towards one group over the other while they create their algorithm? This is why I take a deeper look into Figure Eight hate speech algorithm within the capstone.

**Data**
The data I used throughout the capstone is from huggingface.com. I was able to find the original source of this data set that initially had over one hundred thousand rows worth of data. Through huggingface, they condensed the data set to over twenty-four thousand rows. From the huggingface data set, I only extracted ten thousand rows of data. 
Source: https://huggingface.co/datasets/hate_offensive.

**Summary Statistics**
From my analysis within Figure Eight Inc., the hate speech algorithm used on Twitter's tweets, I have learned that neither tweet-length nor tweet word length affects a user(s) creating hate speech tweets. All it takes is one word for the algorithm to identify whether it's in the hate speech, offensive language, or neither category. Then this led me to analyze the value counts on the 'class' column, which is my target predictor to classify, or the 'count' column. 

Looking into these two columns and if they correlate, I found no significant correlation. For example, remember that the 'count' column is how many coders within Figure Eight's company voted for the tweet in either of the three categories. Three coders voted over nine thousand tweets, and nine coders voted only 59 rows of tweets. Understanding this made me ask if there is any significance about it, and I could not answer this question. Although, I did realize within the 'class' column that my data is critically imbalanced. Over seven thousand and four hundred tweets out of the ten thousand tweets categorized as offensive language but not hate speech. 

The scatterText interactive word scatter plot showed me the most frequent words within the hate speech vs. offensive language categories. It seemed that it was categorizing racial hate speech and slurs correctly, but the algorithm miscategorized them regarding LGBTQ slurs. It is difficult to identify the LGBTQ slurs because unless you are a part of the community, one would not easily see that it is a slur. Therefore this is where the context of the tweet plays a significant role. Since the algorithm works from votes from a coder, there is bias in society, meaning, for example, if they do not support LGBTQ people, then slurs are acceptable. This is harmful and dangerous. Then are, some tweets within the data set were hate speech, and some coders voted it as neither. That is dangerous too. If you know that a specific word is hate speech, but you vote neither, it clearly shows your bias. Having these biases examples helps me to answer the problem statement stated above. 

Lastly, when it came down to my models using a multi-classifier, the imbalanced data would skew my results. For example, within my top performing model, the CountVectorizer with Logistic Regression, the accuracy was 87%, with a null model of 74%. One would think this is great, but I used the critical metric of "balanced accuracy" because the data is imbalanced—this metric accounts for imbalanced data. After applying the balanced accuracy, the accuracy score dropped significantly to 66%, and the null new model's new baseline is 33%. Although, you can infer from the precision and recall metrics that the balanced was also imbalanced. For example, the precision of the offensive language category was 90%, and the recall was 95%. Still, the hate speech category with fewer rows than the two other categories was alarmingly low. To account for the imbalanced data, I would use the SMOTE method to help create balanced data. Using SMOTE would help me have better accuracy scores for my models.

**Recommendations**
After my analysis, I recommend that companies such as Figure Eight Inc. train their models on marginalized communities to learn their vernacular and vocabulary. Doing this will help their coders be less biased toward specific groups in their lives. Or these companies can increase diversity hires to be on there to speak up if they see a colleague miscategorizing a word that they do not see as a hate speech word. 

Also, let social media companies that use hate speech algorithms have stricter rules on people's tweets, especially if it is hate speech to an already targeted marginalized community. For example, researching Twitter, I read that they only give a warning to people that write offensive language, and for the hate speech, Twitter will only suspend them for a day or two, and then they are invited back. This is alarming because the people who write hate speech still have an incentive to continue their hate speech. After all, the consequence is not severe. 

**Conclusions**
In conclusion, to answer my problem statement, the hate speech algorithm misclassifies hate speech and offensive language tweets. In doing so, it is harmful to targeted communities. Social media nowadays can incite digital assaults on other users without severe consequences. From my data, I have used the LGBTQ community as an example. Unfortunately, the algorithm multiple times misclassified queer hate speech and offensive slurs. Therefore, I want to state that everyone who is a coder using a hate speech algorithm should have the self-awareness to see if they have any biases towards any marginalized communities within society. 

My next steps with my capstone would be to review my data and remove any HTML from the tweets so the model can predict better accurate classification. Then I would test the data on a convolutional neural network (CNN) model and inspect the data to see if there is any racial or gender bias. 

**Sources**
https://www.theverge.com/2021/5/5/22420586/twitter-offensive-tweet-warning-prompt-updated-success-rate
https://medium.com/analytics-vidhya/visualizing-phrase-prominence-and-category-association-with-scattertext-and-pytextrank-f7a5f036d4d2
