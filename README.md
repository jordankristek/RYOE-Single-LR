# RYOE-Single-LR
This project uses a multi-phased approach to analyze the predictability of NFL rushing yards-per-carry data year-over-year.

The first step was to import NFL play-by-play data and perform exploratory data analysis. Using yards to go (ydstogo) on the x-axis and rushing yards on the y-axis, we were quickly able to see that there is a slight positive correlation between ydstogo and rushing yards.

![image](https://github.com/jordankristek/RYOE-Single-LR/assets/150874257/0ac7381a-548c-4b37-ba13-fe630fb3d260)

After averaging yards per carry (YPC) per ydstogo bin, we were able to see the positive line of regression much more clearly.

![image](https://github.com/jordankristek/RYOE-Single-LR/assets/150874257/292ed904-91e8-4e7c-af77-327d1f1511fa)

Next, we fit our data into a simple linear regression model, using the statsmodels package.

![image](https://github.com/jordankristek/RYOE-Single-LR/assets/150874257/de6b5f3a-2c2e-4e5b-9ef3-29d18c14cd9c)

![image](https://github.com/jordankristek/RYOE-Single-LR/assets/150874257/d783fbb3-a98f-4cb8-a59a-4210a7e68f0d)

With a low R-squared score of 0.007, we can conclude that there is not a strong correlation between ydstogo and rushing yards. Most likely, a multiple linear regression model will need to be used for predicting rushing yards. For the sake of this project, we will move forward.

The last part of the project revolves around creating a new metric called "Rushing Yards Over Expected (RYOE)", which is the difference of the predicted rushing yards from our simple linear regression model minus the actual rushing yards recorded for each play.

We created a new dataframe used to look at RYOE and rushing yards by season, player_id, and player name. We also filtered our data on players with more than 50 rushing attempts.

![image](https://github.com/jordankristek/RYOE-Single-LR/assets/150874257/3d8a506d-144e-45ae-a7b6-678a0c65afc0)

Finally, we created a current year dataframe, as well as a last year dataframe. We merged the two dataframes together and performed correlation testing to find out which rushing metric, YPC or RYOE, is more correlated year-over-year. The results show that RYOE is slightly more correlated year-over-year.

![image](https://github.com/jordankristek/RYOE-Single-LR/assets/150874257/fd364fcc-8161-4698-b333-b32295aa86b5)

![image](https://github.com/jordankristek/RYOE-Single-LR/assets/150874257/e74f6c48-bb89-4a5d-9f48-e79b3fd4fe5e)
