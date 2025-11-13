Interim Status Report (Milestone 3)

Project Review: For our semester project, we studied how US interest rates relate to stock market performance, focusing on the S&P 500. We used historical information from Federal Reserve rates and S&P 500 price data to quantify how monthly indexes returns and volatility move with changes of interest rates. 

From exploring the data early on, we decided to narrow our time horizon from the original 70-year window to a more recent 10-year period. By focusing on this window, we can successfully clean data more easily, reduce issues with structural breaks, and keep our results more relevant to recent market behavior. We refined our research questions to mirror these changes below:

What has been the relationship between monthly S&P 500 returns and the federal interest rates over the last ten years?
How do changes in interest rates impact stock market/S&P 500 volatility?

During Weeks 7-12, we downloaded and stored our datasets, cleaned and aggregated the data to a common monthly frequency, created features, merged datasets for analysis, and produced summary tables and visualizations to better understand our research goal. 


Updated Timeline & Progress:

Week 7-8: Data Collection and Ethical Considerations

Week Plan: For Weeks 7-8, we planned to focus on data collections and getting the project organized. We planned to download both the S&P 500 and Federal Reserve datasets and set them up in a shared repository. We aimed to create clear folders for raw data, cleaned data, and scripts for future analysis. Additionally, we prepared to read through the documentation for each dataset and record ethical/licensing considerations.  

Changes: There were no changes made to this stage of the project plan. 

What We Completed: We set up our project structure in GitHub by creating a new repository called IS477_Course_Project. Inside the repository, we added two main folders called “data” and “project_code” to separate the datasets and the scripts we’ll write later. Inside the “data” folder, we created two subfolders called “raw” and “cleaned”, and uploaded our two datasets. We documented where each dataset came from (Kaggle & investing.com) to summarize our plan for cleaning and analysis. From this research, we noted that both datasets are public, contain no personal or sensitive information, and do not raise any major ethical or licensing issues. 

Artifacts: The artifacts within this portion of the project include GitHub repository initialization, raw data files added and version controlled, and ethical and licensing notes in our README.md section.

Status: Completed


Week 9: Organizing and Exploring Data

Week Plan: For Week 9, we planned to actually organize and explore our data. We wanted to clean and align our datasets to the same format, and check for Null values. We aimed to run some light exploration checks to make sure the data looked reasonable before building features in later weeks. 

Changes: There were no major changes made to this stage of the project plans beyond restricting the date window to have aligned datasets. 

What We Completed: We wrote code to read in both datasets using pd.read_csv() and verified structure. We converted the “Date” column in both stock_df and ffr_df to a proper datetime format with pd.to_datetime() to filter and join dates. After matching the date range and dropping the unused “Vol.” column, we cleaned each dataframe by removing missing values. After cleaning, we confirmed the same numbers of columns and rows before merging the two datasets. Finally, we used an inner join on the “Date” column to create merged_df, which combines stock prices/returns to macro variables. This created an organized dataset to build features from later.

Artifacts: Cleaning/merge notebook, cleaned CSVs, and merged daily-level dataset.

Status: Completed


Week 10: Creating Key Features

Week Plan: For Week 10, we moved from basic cleaning into creating key features that relate to our research question. We planned to create measures that show how the S&P 500 is performing and how volatile it is over time. On the interest-rate side, we aimed to summarize how policy rates move daily and how they compare to one another. With these, the features would give us a clever view of how interest rates and market conditions evolve. We planned to have a dataset ready to roll up to a monthly level.  

Changes: We started with a 30-day rolling volatility and daily rate-change features as a beginning step, instead of aggregating everything to monthly measures from the start. This still supports our goal of studying how rate movements relate to returns/volatility. 

What We Completed: We cleaned up the numeric columns by converting all relevant fields to numeric types so they could be used in calculations. We engineered multiple key features such as Log_Return, Volatility_30D, FedFunds_Change, SOFR_Change, Spread_S0FR_Fed, and Intraday_Range. After creating these features, we dropped rows with missing values created by rolling windows, to have a clean dataset with 1,764 rows and 18 columns. We finally formatted the rate-change variables as percentages to make them easier to interpret for visualization. 

Artifacts: Script/notebook for feature engineering. 

Status: Completed


Week 11: Merging Datasets and Checking Quality

Week Plan: For Week 11, we planned to take the merged dataset and focus on quality checking before doing analysis. We wanted to ensure time coverage and row counts looked right, verify the data type for each column, and make sure there were no missing values. We aimed to create summary statistics to spot patterns and unusual relationships between variables. We planned to identify outliers as well. 

Changes: We ran quality checks at the daily first level, with an idea to aggregate to monthly later. We wanted to be confident in the underlying data. 

What We Completed: We used merge_df.info(), .shape, and .describe() to confirm we had 1,764 rows and all feature columns had appropriate numeric types. We created a correlation matrix for the numeric columns to check relationships between features. We checked for unusual values and summarized in a separate table. This gave us more confidence that our merged dataset looked reasonable and was ready for aggregation and visualization steps. 

Artifacts: Week 11 quality-check notebook with summary statistics, correlations, and outlier table and the verified merged feature dataset. 

Status: Completed


Week 12: Cleaning and Automating the Process

Week Plan: For Week 12, we planned to take our integrated dataset and polish it for analysis. This would involve resolving any missing values or alignment issues, and making sure all features looked reasonable. Additionally, we planned to build an automated workflow so that, starting from raw CSVs, our cleaning, merging, and feature-creation steps could be reproduced easily. Lastly, we wanted to generate  visualizations to see how features move overtime with one another and re-check the data.
Changes: The main adjustment this week was shifting towards creating visualizations and confirming the data looked reasonable, while pushing most of the automation work to the next milestone. 

What We Completed: We used our cleaned, merged dataset to create line plots of the Federal Funds rate and S&P 500 daily prices over time, as well as a combined chart that overlays both series using separate y-axes. These plots help the both of us confirm that key events are captured correctly in our data. Furthermore, we used these visuals as a check that our date alignment and feature engineering steps from the previous weeks were working as intended. After that, we started outlining how these steps will eventually be wrapped into a reusable script or notebook. 

Artifacts: Notebook with time-series plots of the Federal Funds rate, S&P 500 price, and their combined comparison, plus notes outlining the planned automated workflow. 

Status: In-Progress


Planning Ahead Weeks 13-15:

In Week 13, we want to start running analysis by testing how different rate levels and rate changes relate to returns and volatility. In Week 14, we’ll shift toward reproducibility by writing a data dictionary, polishing our scripts, and tightening up our GitHub documentation. Finally, in Week 15, we plan to pull everything together by refining analysis, finalizing figures, double-check citation/organization in the repository, and complete the report. By the end, we want a project that fulfills our research question.


Team Member Contributions:
Yash Singh: I cleaned the Federal Funds Rate dataset. Additionally, I merged the cleaned datasets into a single table and computed summary statistics for the merged data.
Vishv Patel: I cleaned the S&P 500 dataset including cutting down rows to make sure the dates aligned wil the Federal Funds Rate. Additionally, I performed quality checks on the data and code throughout the weeks as well as built the visual models present in our code.

Dataset URLs and Licensing Notes:
Dataset 1: https://www.kaggle.com/datasets/eswaranmuthu/u-s-economic-vital-signs-25-years-of-macro-data 
Dataset 2: https://www.investing.com/indices/us-spx-500-historical-data 
Licensing Notes: 
The Federal Funds Rate dataset was licensed under CC BY 4.0 which allows us free use to use the material. The S&P 500 dataset falls under the T&C of investing.com. The data can be used for non-commercial use like schoolwork.
