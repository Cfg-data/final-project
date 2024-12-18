# Educational Data Analysis Project

## Navigation

- [Project Overview](#project-overview)
- [EDA Results Summary](#EDA-results-summary)
- [Collected Datasets](#collected-datasets)
- [Project Progress](#project-progress)
- [License](#license)
- [Folder Structure](#folder-structure)
- [Streamlit App](#streamlit-app)

---

## Project Overview

This project involves analyzing educational data collected from the United Nations Data (UNDATA). The data covers various aspects of education, including gender ratios, public expenditure, access to computers, and teaching staff in different regions and countries. The datasets provided are from the *Statistical Yearbook* and are crucial for understanding trends and disparities in global education systems.

# EDA Results Summary

For a detailed view of the complete EDA results, please visit [Full EDA Results](https://raw.githubusercontent.com/Cfg-data/final-project/refs/heads/master/EDA_results.md).

---

## Education Trends (2005-2022)

- **Primary Education**: Enrollment ratios for both males and females were nearly universal in 2005 but have slightly declined by 2022. Both female and male enrollment ratios were close to 98%, signaling stable access to primary education.
- **Secondary Education**: Enrollment at the lower and upper secondary levels has decreased significantly over the years. The gender disparity is notable in upper secondary education, where females initially had higher enrollment but saw a sharp drop by 2022, with males having slightly higher rates by the end.
- **Regional Disparities**: Developed countries, especially in Europe and North America, generally maintained strong enrollment, while lower-income or politically unstable regions faced challenges, particularly at the secondary education level.

## Public Expenditure Insights

- **Staff Compensation**: Mexico (85.5%) and Belgium (83.6%) dedicate a significant share of their public expenditure to staff compensation, emphasizing a focus on salaries and benefits in the public sector.
- **Capital Expenditure**: Countries like Japan (13%) and Norway (12.3%) invest heavily in capital expenditures, suggesting a focus on long-term infrastructure development and public assets. Some countries like San Marino report 0% in this category, which may reflect unique expenditure patterns.
- **Current Expenditure**: Finland (32.85%) and Sweden (29.77%) allocate substantial portions of their budgets to other current expenditures, pointing to a robust funding model for public services beyond salaries.

## Regional Variations in Expenditure

- **High Expenditure on Staff Compensation**: Mexico and Belgium stand out with high percentages of public expenditure dedicated to staff compensation, indicating a larger portion of the public budget directed towards public sector employees.
- **Infrastructure Investment**: Japan and Norway prioritize capital expenditure, which indicates significant investments in public infrastructure and future development.
- **Operational Costs**: Finland, Sweden, and Romania show a larger share of spending on operational expenses beyond staff compensation, reflecting broad public service investments.

## Overall Conclusions

- **Education**: Global education trends show near-universal primary education enrollment, but secondary education faces challenges, with gender disparities increasing at the upper secondary level.
- **Public Expenditure**: The focus of public expenditure varies across regions. Countries like Mexico and Belgium emphasize staff compensation, while Japan and Norway prioritize infrastructure investment. Finland and Sweden lead in operational expenditure, ensuring robust public services.

This comprehensive comparison of education trends and public expenditure highlights diverse priorities and challenges faced by different regions, offering insights into both educational access and government spending patterns.

## Collected Datasets

The following datasets have been collected from UNDATA:

1. **[Ratio of Girls to Boys in Education](https://data.un.org/_Docs/SYB/CSV/SYB67_319_202411_Ratio%20of%20girls%20to%20boys%20in%20education.csv)**
   - Dataset ID: SYB67_319_202411
   - Description: This dataset provides the ratio of girls to boys in education across different countries and regions.

2. **[Public Expenditure on Education and Access to Computers](https://data.un.org/_Docs/SYB/CSV/SYB67_245_202411_Public%20expenditure%20on%20education%20and%20access%20to%20computers.csv)**
   - Dataset ID: SYB67_245_202411
   - Description: This dataset presents the public expenditure on education, along with data on the availability of computers in educational institutions.

3. **[Teaching Staff in Education](https://data.un.org/_Docs/SYB/CSV/SYB67_323_202411_Teaching%20Staff%20in%20education.csv)**
   - Dataset ID: SYB67_323_202411
   - Description: This dataset outlines the number of teaching staff in the education sector across various countries and regions.

4. **[Education Statistics](https://data.un.org/_Docs/SYB/CSV/SYB67_309_202411_Education.csv)**
   - Dataset ID: SYB67_309_202411
   - Description: This dataset provides a comprehensive overview of various education-related statistics, such as enrollment rates, graduation rates, and literacy rates.

## Additional Datasets

### Literacy Rates:
- **[Youth Literacy Rate, Population 15-24 Years (%)](https://data.un.org/Data.aspx?d=UNESCO&f=series%3aLR_AG15T24)**  
  Identified as UNdata_Export_20241213_140703208 in the files.
- **[Youth Literacy Rate, Population 15-24 Years, Gender Parity Index (GPI)](https://data.un.org/Data.aspx?d=UNESCO&f=series%3aLR_AG15T24_GPI)**  
  Identified as UNdata_Export_20241213_140708283 in the files.

## Project Progress

### Handling Data:
1. Changing column names
2. Dropping rows with index 0 (which contained all the column names)
3. Looking for null values
4. Describing data by Region Code and Value
5. Getting all unique values
6. Filling null values with mode in the "Footnotes" column
7. Gathering further data
8. Changing and normalizing format
9. Filtering dataset for the regions needed
10. Grouping only for the years with the largest amount of data for the biggest number of countries kept
11. Repeating step 10 for the regions
12. Renaming the files
13. Loading files into a jupyter notebook, Running a correlation matrix for each variable, making sure all Nan values are filled with 0
14. Running several figures for the various variables by year, bar plots and violin plots mostly (disregarding 0 values using seaborn and plotly)

### MySQL Progress:
- Database creation in Python connector attempted but unsuccessful
- Proceeded to create database in mysql workbench directly
- Proceeding with each .csv file
- Creating a table for countries and for years separately, to relate all tables to each other
- Aggregate data from existing tables into a full table with only the chosen list of countries

## License

This project is based on publicly available data from UNDATA. Please refer to the [UN Data Usage Policy](https://data.un.org/Usage.aspx) for licensing and attribution information.

## Folder Structure

The project is organized into the following folders:

- **`working_notebooks`**: Notebooks that contain work in progress and are not organized.
  - **`unused_notebooks`**
- **`usable_notebooks`**: Organized notebooks that present findings in an organized manner.
- **`data`**: Collects the data used for the project separate folders:
  - **`raw`**:
    - `literacy_rates`
    - `unused_data`
      - `enrollment_data`
      - `government_expenditure`
  - **`cleaned`**
  - **`filtered`**
  - **`merged`**
    - `variables`
    - `years_vars`
    - `final`
- **`mysql_scripts`**: Collects MySQL scripts and tables created for the project directly in MySQL Workbench.
- **`app_files`**: Contains all the files that pertain to the Streamlit app written for the project.
- **`tableau`**: Tableau visualizations created for the project in PDF form for ease of reading.
- **`slides`**: Presentation PDF for ease of view.

## Streamlit App

The Streamlit app is structured as follows:

- **`app_files/`**: Main folder containing app-related files.
  - **`app.py`**: Main script to run the Streamlit app.
  - **`data_loader.py`**: Handles data loading and processing.
  - **`pages/`**: Contains individual pages of the app.
    - **`opener.py`**: Page that confirms data has been loaded and presents project details.
    - **`introduction.py`**: Provides project introduction and overview.
    - **`ml_results.py`**: Displays machine learning results and findings.
  - **`utils_/`**: Folder for utility functions.
    - **`display.py`**: Helper functions for displaying data.

This app allows users to explore different aspects of the education data, verify the results of the machine learning models run for the project, and analyze trends in education. Navigation buttons within the app enable users to seamlessly switch between sections.