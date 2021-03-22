<h1><b>Indian-Economy-Study-using-news-articles</b></h1>

<h1><b>Abstract</b></h1>
This project focuses on the efficiency of Indian economy and forecasting the phases of economy
using news sentiments. We build embeddings using advance natural langauge processing
techiques for each news article to capture the novelty and potential impact of the news.
Moreover, this project designs a framework to capture the dynamic of news and the market.

<h1><b>Importance of news articles</b></h1>
➣ Newspaper articles convey how the journalist and those interviewed feel about the
economy.<br>
➣ By providing quantified view of financial market news more time is available to focus on
what matters most.<br>
➣ Markets thrive on new information and this data is constantly streaming.<br>
➣ Some people are directly affected by financial news, while others are indirectly affected.<br>

<h1><b>Data Sources</b></h1>
➣ I have used articles of “economictimes.com”, one of topmost and reliable news providers
in India.<br>
➣ Web Scraper was developed to handle the format of the article links that needed to be
scrapped.<br>
➣ The entire text of articles along with summary, key-words, headline and year was fetched
from the specific URL &nbsp;&nbsp;&nbsp;&nbsp;&nbsp; using “newspaper” library in Python. <b><i>"Data_scrap.ipynb"</i></b> notebook is used for this application.<br>
➣ The text was then preprocessed to handle special characters, irrelevant text and white
spaces by simply removing &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;from the text.<br>

<h1><b>Data Labelling</b></h1>

>![](https://i.imgur.com/tp7RRxI.png)
Fig 1. Graph flow of Data Labelling

➣ Some pre-processing on the data extracted is applied which can be seen in Data_scrap.ipynb file and <b><i>"dictionary_based_labelling.ipynb"</b></i>.<br>
➣ I have applied four techniques to find the sentiment of the articles:<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;i) Afinn<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ii) Vader<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;iii) Vader + LoughranMcDonald (LM)<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;iv) Vader + LM + HuLiu (HL)<br>
➣ All the scores are compared and the Vader + LM + HL dictionary is selected. These steps can be seen in <b><i>"dictionary_based_labelling.ipynb"</i></b>.<br>
➣ Finally index of the score is calculated based on the research paper <b><i>"Measuring News Sentiment"</i></b> by Shapiro, Kanjoya and Wilson.<br>
➣ Then these indexes are compared with the indicators taken from government websites and the result is present in &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<b><i>"comparing_results_with_indicators 2002-2010.ipynb"</i></b> file. <br>


<h1><b>Training on labelled data</b></h1>

>![](https://i.imgur.com/76c6eEe.png)
Fig 2. Training on data

➣ First I am converting the articles into triples using the stanford library. <br>

>![](https://i.imgur.com/3CQYzei.png)
.<br>
Fig 3. Sentence is divided into triplets.

Above step can be see in <b><i>"Triple_generation.ipynb"</i></b> file.<br>
➣ After converting the sentence to triplets it is then feed into transE algorithm to get the embeddings of triplets. This step can be seen in <b><i>"transE.ipynb"</i></b> file.<br>
➣ Entity with close meanings would have close embedding vectors. <br>
➣ Feed the embedding vector of the news articles to the sequential model. <br>
➣ Optimize the architecture of the model by using Bi-LSTM and attention or advance
technique like BERT.


