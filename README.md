# SQL Insurance Claim Analysis

## Data Source

The dataset used for this project is sourced from Kaggle:  
[Insurance Claim Analysis: Demographic and Health](https://www.kaggle.com/datasets/thedevastator/insurance-claim-analysis-demographic-and-health)

## Project Description

This project involves analyzing insurance claim data to answer various questions related to patient demographics and health. The aim is to derive insights into insurance claims based on factors such as age, BMI, smoking status, number of children, and region.

## Analysis Questions

1. **Top 5 Patients with Highest Insurance Claims**
   - Identify the top 5 patients who have claimed the highest insurance amounts.

```sql


-- using order by


select * from insurance_data order by claim  desc limit 5


-- using window function


select *,rank() over(order by claim desc) from insurance_data limit 5;


```


2. **Average Insurance Claimed by Number of Children**
   - Determine the average insurance amount claimed by patients based on the number of children they have.

3. **Highest and Lowest Claimed Amount by Region**
   - Find the highest and lowest claimed amounts by patients in each region.

4. **Percentage of Smokers by Age Group**
   - Calculate the percentage of smokers in each age group.

5. **Difference Between Claimed Amounts for Each Patient**
   - Compute the difference between the claimed amount of each patient and the first claimed amount of that patient.

6. **Difference Between Claimed Amounts and Average Claimed Amount**
   - For each patient, calculate the difference between their claimed amount and the average claimed amount of patients with the same number of children.

7. **Patient with Highest BMI in Each Region**
   - Identify the patient with the highest BMI in each region and their respective rank.

8. **Difference Between Claimed Amount and Highest BMI Claimed Amount**
   - Calculate the difference between the claimed amount of each patient and the claimed amount of the patient with the highest BMI in their region.

9. **Difference in Claim Amount by BMI and Smoker Status**
   - For each patient, calculate the difference in claim amount between the patient and the patient with the highest claim amount among patients with the same BMI and smoker status, within the same region. Return the result in descending order of difference.

10. **Maximum BMI Value Among Next Three Records**
    - For each patient, find the maximum BMI value among their next three records (ordered by age).

11. **Rolling Average of Last 2 Claims**
    - For each patient, calculate the rolling average of their last 2 claims.

12. **First Claimed Insurance Value for Non-Diabetic Patients**
    - Find the first claimed insurance value for male and female patients within each region, ordered by patient age in ascending order. Only include patients who are non-diabetic and have a BMI value between 25 and 30.
