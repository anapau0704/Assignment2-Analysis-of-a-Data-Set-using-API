# Analysis of a Data Set using Perspective API: Are comments using profanity doomed to a high toxicity score?

**Basic outline of what was investigated:**

Using Perspective API, I wanted to determine whether or not comments containing profanity are assigned an overall toxicity score that cannot be lower than a certain score, simply on the basis of word choice, irregardless of context and usage.

The idea came about because, while I was examining the Dataset on the CSV file, I noticed that the highest scored comments (receiving scores really close to 1) contained profanity. I then wondered if it was possible for comments containing certain words to receive scores bellow a threshold of 0.5., which I decided as I consider that the deviding line between toxic and non-toxic comments (in other words, it is a line right down the middle). For this test, I mainly looked at the columns (attributes) of "comment_text", which consisted of the comment being scored (qualitative), and "score", which describes the score given to each comment (quantitative continuous, range = 0-1), where lower reflects less toxicity.

The methodology is outlined in the Notebook attached.

**Results and Discussion**

As it turns out, word choice does not necessarily determine the toxicity score, as scores far lower than 0.5 can be reached. However, profanity does move the score higher in a majority of contexts. To further explain, I found that under very specific conditions such as when profanity is used within the title of a song (or other work of art), the API will detect it as neutral language so it does not contribute to its toxicity score. A score of around 0.15 was granted to a comment that referenced a song with a word, that on average achieved a score of around 0.92. When profanity was extended to include more words, the analysis of scores followed a similar pattern. The mean revealed a high score, and the minimum revealed an outlier. However, with the second test, the outlier revealed an error in either the data set or the API, as it detected a comment as having a word that was not in it. This is one of the potential weaknesses of the analysis. 

Lastly, I aimed to test whether comments that contained profanity but had positive intention would receive a similar or lower rating (than the mean of those in the data set), by getting the toxicity score of original comments. The result of this was that only one of the comments received a significantly lower rating (than the mean of comments with the same word). The other comments received scores just as high as those in the data set. The one comment with significant improvement (lower score) was interesting to me as it had the word most found in the highest scored comments. Just by speculating, I think it could be that the phrase is common enough for the API to detect it as positively intentioned and thus remove its bias for a higher score. This speculation would need more testing to confirm (or disprove). 

**Disclaimer for Viewers:** This data analysis examines profanity within a Data Frame and hence contains explicit language.
