# r-template
  An renv based template for easy setup of reproducible repos integrating Flipside data & R for data science.

We recommend R 4.2.3 available here: https://cran.r-project.org/ and RStudio as an IDE here: https://posit.co/download/rstudio-desktop/ 

# Reproduce 

1. Clone this repo. I use GitHub Desktop, you can grab the URL to clone in that app, or use `git clone https://github.com/fsc-data-science/r-template.git`
2. Create a txt file called `api_key.txt` and place your API key (you can create one via the API page when logged into Flipside: https://flipsidecrypto.xyz/account/api-keys )
3. Open RStudio and then navigate to the `r-template.Rproj` file and open it. This will 
abstract away any non-relative file paths.
4. In RStudio run the command `install.packages('renv'); renv::restore()`.

The environment lock file includes installs for shroomDK, dplyr, and plotly.

5. You can now run the analysis script `hello-flipside.R`. If you create an interactive HTML file (`candlestick_chart.html`) it worked! (Open in browser to see the eth volume weighted average price candle chart over the last 30 days).
6. You can restart your git history, rename the directory & project, etc. and push a new repo to your own github.

7. As you work with your own repos and environments, use `renv::snapshot()` to manage new package installations and ensure reproducibility for those who clone your repos!

# Flipside API 

You can generate API keys to bring SQL queries from the data studio into R & RStudio 
via the flipside package. This repo includes it in the environment for you. Note: API Keys are capped at a free 5,000 query seconds/month.
 So it is recommended you write your queries in the (free) Studio first, and then bring the polished query into R once it runs as expected.

Relatedly, keep our docs handy as you work with data from Flipside. 

https://docs.flipsidecrypto.com/flipside-api/get-started/run-your-first-query

