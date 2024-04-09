
## 1. Introduction
Kickstarter, as a crowdfunding website platform dedicated to funding companies with creative ideas, aims to support and inspire innovative, creative, and imaginative activities. It allows creative individuals to raise small amounts of money from the public through an online platform, enabling them to obtain the necessary funds to realize their dreams. The platform connects users who are innovative and eager to create with those willing to fund them.

This experiment focuses on scraping data, conducting regression analysis, and building a model for technology crowdfunding projects from Asia that ended before October 2021. The output of the predictive model is whether the project was successful, i.e., whether the fundraising amount reached its target.

## 2. Experiment Objectives
The objectives of this experiment are twofold:
1. To scrape crowdfunding project data from Kickstarter.
2. To establish a predictive model for the success of crowdfunding projects based on the scraped data.

## 3. Implementation Phases
### 3.1 Data Scraping
#### 3.1.1 Web Analysis
- Initial URL: [Kickstarter URL]
- Observations: 
  - Asynchronous loading of Kickstarter website.
  - Changes in URL structure upon loading more projects.
- Extraction Strategy:
  - Loop through 165 pages to extract project data.
  - Utilize Beautifulsoup for HTML text extraction.
  - Extract project information using regular expressions and JSON parsing.

#### 3.1.2 Scraping Approach
- For loop: Visit 165 pages to retrieve HTML text.
- Beautifulsoup: Extract HTML text containing 12 project details.
- Regular expressions: Retrieve project JSON data.
- JSON library: Convert JSON data to dictionary.
- Data processing: Convert data to pandas DataFrame and save as an Excel file.

### 3.2 Data Cleaning
#### 3.2.1 Variable Removal
- Removed irrelevant variables from the original dataset of 37 variables.

#### 3.2.2 Time
- Converted four timestamp variables to datetime format.
- Filtered data to include only projects ending before October 2021.

#### 3.2.3 Location and Category
- Extracted country information from the 'location' variable.
- Retained only the 'name' information from the 'category' variable.
- Filtered out categories with fewer than 10 projects.

#### 3.2.4 Variable Creation
- Created a 'success' variable based on the 'percent_funded' variable.

### 3.3 Visualization
- Visualized project counts and success rates by location and category.

### 3.4 Prediction
- Implemented an XGBoost model for predicting project success.
- Input variables included 'goal', 'period', 'staff_pick', location dummies, and category dummies.

For detailed information on the XGBoost model principles and analysis results, refer to the accompanying PPT presentation.
