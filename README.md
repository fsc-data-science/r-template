# r-template
  An renv based template for easy setup of reproducible repos integrating Flipside data & R for data science.

We recommend R 4.2.3 available here: https://cran.r-project.org/ and RStudio as an IDE here: https://posit.co/download/rstudio-desktop/ 

# Use as a Template for a new Repo

~ 10min detailed walkthrough video available here: https://www.loom.com/share/Using-the-R-Template-for-Reproducible-Data-Science-cd06a544bcc54fd6a7f48e3267fbee3b

Here are the steps: 

1. Clone the repo locally.
2. Rename the folder to your desired name.
3. Rename the Rproj file to your desired name.
4. Delete the (possibly hidden) folder: `.git` which tracks your history. When using the template for a new repo, you want to have a fresh history.
5. Create a new repo using the renamed folder. You can choose to overwrite the README, gitignore, and License with defaults. If you do, re-add api_key.txt to the gitignore. We suggest you do not overwrite. You can change these later.
6. After you have created a git repo at this renamed folder, the gitignore, License, and README will match the template (change if you want). You will notice you now have an initial commit with the template files.
7. Create an api_key.txt with your API key. (you can create one via the API page when logged into Flipside: https://flipsidecrypto.xyz/account/api-keys)
8. Double check your key is gitignore'd before making a new commit.
9. Open RStudio and your renamed Rproj file.
10. `renv::restore()` & `hello-flipside.r` should now "just work". You can make changes and push your new repo, including using `renv::snapshot()` to add new packages.

The renv environment lock file includes installs for shroomDK, dplyr, and plotly. 

# Exact Reproduction 

For testing, when you are not going to rename or make a new repo, this proves the `r-template` is reproducible. 

1. Clone this repo. I use GitHub Desktop, you can grab the URL to clone in that app, or use `git clone https://github.com/fsc-data-science/r-template.git`
2. Create a txt file called `api_key.txt` and place your API key (you can create one via the API page when logged into Flipside: https://flipsidecrypto.xyz/account/api-keys )
3. Open RStudio and then navigate to the `r-template.Rproj` file and open it. This will abstract away any non-relative file paths.
4. In RStudio run the command `install.packages('renv'); renv::restore()`.
5. You can now run the analysis script `hello-flipside.R`. If you create an interactive HTML file (`candlestick_chart.html`) it worked! (Open in browser to see the eth volume weighted average price candle chart over the last 30 days).
6. Exact reproduction is different than using the template for a new repo. See above for Use as a Template for a new Repo.

7. As you work with your own repos and environments, use `renv::snapshot()` to manage new package installations and ensure reproducibility for those who clone your repos!

# Flipside API 

You can generate API keys to bring SQL queries from the data studio into R & RStudio: https://flipsidecrypto.xyz/account/api-keys

This repo includes it in the environment for you. Note: API Keys default to the Community Tier of the first 5,000 query seconds/month free.
We recommend you write your queries in the Flipside Studio first, and then bring the polished query into R once it runs as expected.

Relatedly, keep our docs handy as you work with data from Flipside. 
https://docs.flipsidecrypto.com/flipside-api/get-started/run-your-first-query

