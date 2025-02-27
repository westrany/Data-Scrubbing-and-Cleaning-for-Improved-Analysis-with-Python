# Data Scrubbing and Cleaning for Improved Analysis

![image](https://github.com/westrany/Data-Scrubbing-and-Cleaning-for-Improved-Analysis/assets/69496007/9734c233-c8f8-400a-96b1-327bb3215bf3)

*Run this command on CMD before running notebook to avoid data rate error:*  

```jupyter notebook --NotebookApp.iopub_data_rate_limit=1000000000```

*If using Notebook through Anaconda, run the previous command on Anaconda's CMD*


## Objective  

Demonstrate proficiency in data cleaning techniques.  

The project aims to prepare raw datasets for analysis by addressing inconsistencies, missing values, outliers, and other data quality issues.

## Dataset Selection  

The dataset chosen for this project is an unclean copy of my [GoodReads Small Dataset](https://www.kaggle.com/datasets/mariafitas/goodreads-small-dataset) (as for 2024/02/11) in csv format with 406 entries. Data types included are integers, floats, strings, data/time and booleans (both in TRUE/FALSE and 0/1 formats). The following table illustrates each section, its data type and entry example:  

| Column Title                  | Data Type      | Example                                                        |
|-------------------------------:|:----------------:|:----------------------------------------------------------------:|
| Book Id                       | Integer        | 50617439                                                       |
| Title                         | String         | Poetry Scraps                                                  |
| Author                        | String         | Rowan Skye                                                     |
| Author l-f                    | String         | Skye, Rowan                                                    |
| Additional Authors            | String         | Miguel Serras Pereira                                          |
| ISBN                          | String         | 9896419884                                                     |
| ISBN13                        | String         | 9789896419882                                                  |
| My Rating                     | Float          | 5                                                              |
| Average Rating                | Float          | 4.3                                                              |
| Publisher                     | String         | Relógio D'Água Editores                                        |
| Binding                       | String         | Paperback                                                      |
| Number of Pages               | Integer        | 152                                                            |
| Year Published                | Integer        | 2020                                                           |
| Original Publication Year     | Integer        | 2005                                                           |
| Date Read                     | Date (DD-MM-YYYY)         | 22/01/2024                                          |
| Date Added                    | Date (DD-MM-YYYY)          | 30/01/2024                                         |
| Bookshelves                   | String         | to-read                                                        |
| Bookshelves with positions    | String         | to-read (#179)                                                 |
| Exclusive Shelf               | String         | to-read                                                        |
| My Review                     | String         | Mind-blown in space                                            |
| Spoiler                       | Boolean (String)         | FALSE                                                |
| Private Notes                 | String         | gift from Hufflepuff                                           |
| Read Count                    | Integer        | 3                                                              |
| Owned Copies                  | Boolean (Integer)        | 1                                                    |  

This is a good dataset to clean and analyse as it contains missing values, inconsistent formats and outliers.  

*Disclaimer: Since GoodReads notifies you when there are duplicate entries, which meant I had no duplicate entries, I asked an AI to add 20 random duplicate entries to the data set for the purpose of this project.*

## Libraries Used  

• **category_encoders:** used to encode categorical data.

• **Display from IPython.display:** used to render the DataFrame in a nicer format.  

• **LabelEncoder from sklearn.preprocessing:** used to normalize labels. It can also be used to transform non-numerical labels (as long as they are hashable and comparable) to numerical labels.

• **Matplotlib:** A comprehensive library for creating static, animated, and interactive visualizations in Python. It provides a wide variety of plotting functions to visualize data in different formats, such as line plots, scatter plots, histograms, and bar plots. It's often used for customizing and fine-tuning visualizations created with Seaborn or other libraries.  

• **Numpy:** used for working with arrays.  

• **OS:** used when we needed to interact with the operating system to save data, check if there are files with the same name and delete them before saving the new data.

• **Pandas:** Used for data manipulation and analysis. It provides data structures and functions to work with structured data efficiently, such as loading datasets, handling missing values, and performing operations like filtering, grouping, and merging.

• **Seaborn:** Built on top of Matplotlib, Seaborn is a Python visualization library used for creating informative and attractive statistical graphics. It provides a high-level interface for drawing attractive and informative statistical graphics, including heatmaps, distribution plots, and regression plots.

## Key Steps  

1. **Data Collection:**  

      • Downloaded the chosen dataset from [Kaggle](https://www.kaggle.com/datasets/mariafitas/goodreads-small-dataset) and loaded it into a Jupyter Notebook using Pandas. (For conveniency, the dataset has been added to this repository as [unclean_goodreads_library_export.csv](https://github.com/westrany/Data-Scrubbing-and-Cleaning-for-Improved-Analysis/blob/main/unclean_goodreads_library_export.csv))   

      • This involved reading CSV files containing the datasets into pandas DataFrames, enabling further analysis and manipulation of the data.
   
2. **Initial Data Assessment:**
   
      • Displayed dataset structures including columns, data types and dataframe size.  

      • Converted date columns ('Date Read' and 'Date Added') to DD/MM/YYYY format. Also converted the 'Spoiler' column to boolean type for better analysis.  

      • Classified 'ISBN' and 'ISBN13' columns as categorical as they are unique identifiers with no inherent order.  

      •  Identified categorical and numerical columns in the dataset.   

      • Calculated and visualized missing values in the dataset using a heatmap.   

      • Identified and displayed duplicate entries in the dataset.  

      •  Checked for unique values in categorical and numerical columns, comparing the number of unique values per column to total values.   

      • Checked for outliers in relevant columns using boxplots and provided summary statistics.    

      • Reconfirmed the structure of the dataset to ensure all changes were applied correctly.
   
3. **Data Cleaning:**
   
      • Used DataCleaner's functionality to replace missing values with the mode or median on a column-wise basis.
   
      • Encoded categorical variables using appropriate methods provided by DataCleaner.  

      • Remove rows with missing values using DataCleaner's automated features.  

      • Apply automatic discovery and correction of common data issues such as outliers and format errors using DataCleaner's built-in algorithms.  

   
4. **Data Transformation:**
   
      • Perform data transformations as necessary (e.g., normalization, log transformation), leveraging DataCleaner's capabilities.
   
      • Create derived features or variables that might enhance analysis.
   
5. **Data Validation:**
   
      • Validate the cleaned datasets to ensure that data quality issues have been addressed effectively.
   
      • Use DataCleaner's data quality assessment metrics and methods to assess data completeness, accuracy, consistency, etc.
   
      • Check for any unintended consequences of data cleaning operations.
   
6. **Documentation and Reporting:**
    
      • Document the data cleaning process, including the steps taken and rationale behind decisions, utilizing DataCleaner's visual interface if applicable.
    
      • Present summary statistics and visualizations to illustrate the improvements in data quality.
    
      • Prepare a report highlighting the impact of data cleaning on the analysis potential of the datasets.
    

## Additional Considerations  
1. Ensure reproducibility by documenting all code and steps taken in the cleaning process.
   
2. Consider leveraging DataCleaner's visual interface for easier data management and exploration.
   
3. Utilize DataCleaner's extensibility to integrate with other data processing and analysis tools if necessary.

## Conclusion  

By completing this project using DataCleaner, you will showcase your ability to efficiently address data quality issues and prepare datasets for analysis, demonstrating key skills valued in the field of data science.  


This project structure adheres to the principles of clear objectives, high-quality data, robust algorithms, interpretability, continuous improvement, cross-functional collaboration, and ethical considerations outlined in the guidelines, while leveraging the unique features of DataCleaner for data cleaning and transformation.  

## Research   

[My Favorite Python Libraries for Data Cleaning in 2023](https://medium.com/@tubelwj/my-favorite-python-libraries-for-data-cleaning-in-2023-c475830dacbb)
