Keri Mallari <br />
Fall 2018 Project

Data: Video Game Sales <br />
Source: https://www.kaggle.com/gregorut/videogamesales <br />

The data consists a list of videogames with sales greater than 100,000 copies. The kaggle contributor scraped this data using BeautifulSoup on Python at vgchartz.com. The data contain 11 features ranging from various sales numbers in North America, Europe, and Japan - since Japan as a country is a big publisher and consumer of videogames. There are also information on the platform and genre of the game. 

Questions: 
1. How much does Japan control the video game industry?
2. Does decrease in sale impact the number of games a publisher will release?
3. Is the publisher of the game indicative of the game genre and platform? 

***

Mean and Standard Deviation of Video Game Sales based on their region. <br />
![](df_mean_sd.jpg)

Distribution of sales in North America, Europe, and Japan.
These graphs are scaled by log 10 because it is right skewed. The scale allows us to better see and understand the distribution.

![](plot_na_dist.png) 

![](plot_eu_dist.png) 

![](plot_jp_dist.png)

To better understand the shape of these plots, the dataframe below lists the value of kurtosis and skewness, as well the the value of 2sqrt(6/n) and 4sqrt(6/n) to verify the skewness and kurtosis. <br />
![](df_shape.jpg)

The rule of thumb for skewness states that if the value of skewness is greater than 2sqrt(6/n) then that graph is significantly skewed towards the direction of the sign. Since the table above shows that all values of skewness are greater than the rule of thumb value, the three distributions are positively skewed, which is evident in the plots as well. Similarly, the rule of thumb for kurtosis states that if the absolute value of the kurtosis is greater than 4sqrt(6/n) then the it is significantly greater than 0. Since the table above shows that all values of kurtosis are greater than the rule of thumb value, the three distributions are leptokurtic - which means that there is a steep peak and heavy tails, both evident in all plots.

***
Looking at the distribution of the qualitative columns in our dataset: platforms, publishers, and genre

![](plot_platform_dist.png)

![](plot_genre_dist.png) 

![](plot_publisher_dist.png)

We see that PS4 is a very popular platform for purchasing videogames. This surprises me as I assume that there are more people playing on their PCs, until I realized that we are looking at video game sales and not player base in general, which makes sense because a lot of popular pc games are free such as League of Legends and Fortnite, as opposed to PS4 games. Action games are most popular video game genre. I flipped the graph for the video game publisher since it would be easier to read the x-
values (publishers). 

***

In calculating the confidence intervals for our three numerical column, I generated a sample of size 30 for each column. Then recalculated the sample mean, sample standard deviation, and sample standard error. With size 30, I will use the Central Limit Theorem. I selected 95% confidence level.

The table below shows the sample mean, sample standard deviation, sample error, and the left and right confidence intervals. 

![](df_confidence.jpg)

***

Hypotheses Testing

For the purpose of this project, I will be using the average global sales as the 'ground truth' and run 4 hypothesis tests where I am comparing the average sales of NA against Global, EU against Global, JP against Global, and Other against Global

Results of the t.test

| North America vs Global Sales | Europe vs Global Sales |
| ----------------------------- | ---------------------- |
| ![](ttest_na_gl.png)          | ![](ttest_eu_gl.png)   |

| Japan vs Global Sales | Other vs Global Sales |
| --------------------- | --------------------- |
| ![](ttest_jp_gl.png)  | ![](ttest_ot_gl.png)  |
***

ANOVA of average video game sales in North America grouped by top 3 video game platforms

Below is the plot of the sales of video games in North America grouped by their platforms: 3DS, PS4, and Xbox One. These three platforms are the most popular platforms in terms of sales. I conducted an analysis of variance of sales in north america grouped by the top 3 platforms. 

![](plot_anova1_platform.png) | ![](plot_anova1_tukey.png)


***

ANOVA of average video game sales in North America grouped by top 3 video game genres

Below is the plot of the sales of video games in North America grouped by their platforms: Action, Shooter, and Sports. These three platforms are the most popular platforms in terms of sales. I conducted an analysis of variance of sales in north america grouped by the top 3 platforms. 

![](plot_anova2_genre.png) | ![](plot_anova2_tukey.png)