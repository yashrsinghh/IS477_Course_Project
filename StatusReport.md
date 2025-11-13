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


