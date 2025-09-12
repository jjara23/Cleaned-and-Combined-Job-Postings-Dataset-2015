# Cleaned and Combined Job Postings Dataset (2015)

This repository contains a cleaned and combined dataset of job postings, originally collected in 2015. It is intended to be used as a baseline for research and development related to job posting analysis and fake job detection.

## Dataset Description

This dataset is an aggregation of job posting data from multiple sources, primarily focusing on real and fake job advertisements. The original data was collected around 2015 and may not reflect the current landscape of online job postings.

The combined dataset includes the following columns:

*   `job_id`: Unique identifier for each job posting.
*   `title`: The title of the job posting.
*   `location`: The location of the job.
*   `department`: The department within the company.
*   `salary_range`: The specified salary range for the position.
*   `company_profile`: A description of the company.
*   `description`: The main description of the job.
*   `requirements`: The required qualifications and skills.
*   `benefits`: Information about job benefits.
*   `telecommuting`: Indicates if the job allows telecommuting (binary).
*   `has_company_logo`: Indicates if the job posting has a company logo (binary).
*   `has_questions`: Indicates if the job posting includes screening questions (binary).
*   `employment_type`: The type of employment (e.g., full-time, part-time).
*   `required_experience`: The required level of experience.
*   `required_education`: The required level of education.
*   `industry`: The industry of the company.
*   `function`: The job function.
*   `label`: The target variable, indicating whether the job posting is real (0) or fake (1).

## Data Sources

This combined dataset was created by aggregating data from the following sources available on Kaggle:

*   **EMSCAD (Real/Fake Job Posting Prediction):** [https://www.kaggle.com/datasets/shivamb/real-or-fake-fake-jobposting-prediction](https://www.kaggle.com/datasets/shivamb/real-or-fake-fake-jobposting-prediction)
*   **Recruitment Scam variant:** [https://www.kaggle.com/datasets/amruthjithrajvr/recruitment-scam](https://www.kaggle.com/datasets/amruthjithrajvr/recruitment-scam)
*   **Fake-only 10k dataset:** [https://www.kaggle.com/datasets/srisaisuhassanisetty/fake-job-postings](https://www.kaggle.com/datasets/srisaisuhassanisetty/fake-job-postings)

## Data Cleaning and Preprocessing

The following cleaning steps were applied to the raw datasets:

*   **Combination:** Multiple datasets were combined into a single DataFrame.
*   **Renaming:** The target column was standardized to `label` across all datasets.
*   **Missing Value Handling:** Missing values in text fields were filled with empty strings for consistency.
*   **Deduplication:** Duplicate job postings were removed based on a hash of the title and description to ensure a unique set of entries. This resulted in a final dataset size reflecting only unique job postings.

## Dataset Size

After cleaning and combining, the dataset contains approximately 15,787 unique job postings. This number reflects the dataset size after deduplication across all sources.

## Limitations

It is important to be aware of the following limitations when using this dataset:

*   **Temporal Relevance:** The data is from 2015, which means it may not be representative of current job market trends, language used in job postings, or scam tactics. New fake job schemes may have emerged since then.
*   **Class Imbalance:** The dataset exhibits a significant class imbalance, with a much larger number of real job postings (label 0) compared to fake job postings (label 1). This imbalance needs to be addressed during model training (e.g., through oversampling, undersampling, or using appropriate evaluation metrics).
*   **Data Source Bias:** The original sources of the data may have their own biases, which could be reflected in the combined dataset.
*   **Limited Features:** While the dataset includes several features, additional information (e.g., source of the posting, user reports) could be beneficial for more robust fake job detection.

## Usage

This dataset can be used for various tasks, including:

*   Exploratory Data Analysis (EDA) of job posting characteristics.
*   Developing and evaluating models for fake job detection.
*   Text analysis of job descriptions and titles.

Please consider the limitations mentioned above when interpreting your results or building applications based on this dataset.
