# Midterm Lab Task 2 - Data Cleaning and Preparation using Power Query
This portfolio contains the steps I followed for cleaning, transforming, and reshaping job posting data using Power Query Editor in Excel.

# Part 1: Data Cleaning and Transformation Steps

## 1. Data Import and Initial Cleaning
- Loading the Data: The raw data is loaded from a CSV file.
- Cleaning Salary Estimate: We remove unwanted characters from the Salary Estimate column (text after the opening parenthesis) to clean the data.
- Creating Min and Max Salary Columns: Using the extracted salary values, two new columns Min Sal and Max Sal are created to represent the salary range for each job.

## 2. Role Classification
- Grouping Job Titles: A new column called "Role Type" is created to classify the job titles into five categories:
- Data Scientist
- Data Analyst
- Data Engineer
- Machine Learning Engineer
- Other (for non-classifiable roles)

## 3. Location Data Cleanup
- Standardizing Locations: Custom formulas are used to standardize location names and abbreviations. For example, "New Jersey" is replaced with ", NJ", "California" with ", CA", and so on.
- Splitting Location: The location column is split into two parts: one for the location and another for the state abbreviation.

## 4. Handling Negative Values
- Cleaning Negative Values: We remove or filter out invalid negative values from columns like Competitors, Revenue, and Industry.

## 5. Handling Company Size
- Splitting Company Size: The Size column is split into two parts: MinCompanySize and MaxCompanySize.

## 6. Final Cleanup
- Cleaning Company Names: We remove the word "Rates" from company names.
- Removing Unnecessary Columns: Any non-useful columns (like description columns) are removed.

## Screenshots

- Before Cleaning

![image alt](https://github.com/CarlosA012/EDM-Portfolio/blob/5528199dcd6c8022b6bd97167e4a797b7e081f6f/Midterm%20Lab%20Task%202/images/raw%20data.png)

- After Cleaning

![image alt](https://github.com/CarlosA012/EDM-Portfolio/blob/50d70db1f0974bb826213bbf4b78e7f66858d6c0/Midterm%20Lab%20Task%202/images/Unclean%20DS%20Jobs.png)

![image alt](https://github.com/CarlosA012/EDM-Portfolio/blob/5a4647d1557285a89768a75115f450f32e3dadd1/Midterm%20Lab%20Task%202/images/Unclean%20DS%20Jobs%202.png)

![image alt](https://github.com/CarlosA012/EDM-Portfolio/blob/bed38cb17fb84615615af6fc29d7e535dc1dbfdb/Midterm%20Lab%20Task%202/images/Unclean%20DS%20Jobs%203.png)


## Part 2: Reshape and Group the Tables

## 1. Duplicate the Raw Data for "Sal By Role Type"
- Duplicate the Unclean DS Jobs query.
- Rename the query to Sal By Role Type dup.

## 2. Select Columns and Transform Data for "Sal By Role Type"
- Select columns: Role Type, Min Sal, Max Sal.
- Convert Min Sal and Max Sal to Currency.
- Multiply Min Sal and Max Sal by 1000.
- Group by Role Type and calculate average Min Sal and Max Sal.

## 3. Create a Reference for "Sal By Role Size"
- Reference the raw data query.
- Rename it to Sal By Role Size ref.
- Select columns: Size, Min Sal, Max Sal.
- Convert Min Sal and Max Sal to Currency and multiply by 1000.
- Group by Size and calculate average salary.

## 4. Merge Queries with State Mapping
- Merge raw data with state mapping query.
- Rename merged column to State Full Name.
- Remove null and blank values from State Abbreviations.

## 5. Create a Reference for "Sal By State"
- Reference the raw data query.
- Rename it to Sal By State ref.
- Select columns: State Full Name, Min Sal, Max Sal.
- Convert Min Sal and Max Sal to Currency and multiply by 1000.
- Group by State Full Name and calculate average salary.

## 6. View Dependencies and References
- View dependencies to check query relationships.
- Duplicates are independent; references are dependent on the original data.


# Final Queries
- Sal By Role Type dup: Grouped salary data by role type.
- Sal By Role Size ref: Grouped salary data by company size.
- Sal By State ref: Grouped salary data by state.
- Sal By Size Role Type dup: Grouped salary data by size and role type.
- Uncleaned DS Jobs: Raw dataset used for transformations.

## Screenshots of Queries
- Screenshots:

![image alt](https://github.com/CarlosA012/EDM-Portfolio/blob/698ee43bae1a9b9620eaea30577239605f91ea89/Midterm%20Lab%20Task%202/images/Sal%20By%20Role%20Type%20dup.png)

![image alt](https://github.com/CarlosA012/EDM-Portfolio/blob/2416f1bb2c6aeea780a1e11207010896a5c47a3b/Midterm%20Lab%20Task%202/images/Sal%20By%20Role%20Size%20ref.png)

![image alt](https://github.com/CarlosA012/EDM-Portfolio/blob/f6f45e254037e154bd73dc3682335a071f53bf07/Midterm%20Lab%20Task%202/images/Sal%20By%20State%20ref.png)

![image alt](https://github.com/CarlosA012/EDM-Portfolio/blob/1c6d099d8cff7b7159b05998928765ea6513a356/Midterm%20Lab%20Task%202/images/Sal%20By%20Size%20Role%20Type%20dup.png)

![image alt](https://github.com/CarlosA012/EDM-Portfolio/blob/84fdb949a7038628c4f36222420aa3039f0cc3da/Midterm%20Lab%20Task%202/images/Unclean%20DS%20Jobs.png)

![image alt](https://github.com/CarlosA012/EDM-Portfolio/blob/aba145300fbe9cf8053712bf1f8e57b9be5b535f/Midterm%20Lab%20Task%202/images/Unclean%20DS%20Jobs%202.png)

![image alt](https://github.com/CarlosA012/EDM-Portfolio/blob/adf03414c03a553c07cd1831fbd5113ef341920c/Midterm%20Lab%20Task%202/images/Unclean%20DS%20Jobs%203.png)

![image alt](https://github.com/CarlosA012/EDM-Portfolio/blob/3fdbc5a87a3dd0304b429c43cfd8c578d66ac8c6/Midterm%20Lab%20Task%202/images/Query%20Dependenciess.png)
