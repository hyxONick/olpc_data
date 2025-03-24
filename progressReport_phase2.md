# Week 4: Recommendation System using Matrix Factorization (LightFM)

## Problem Statement

> "Using a hybrid matrix factorization model, can we recommend apps used by high-performing schools to lower-performing ones, potentially bridging digital learning gaps?"

## Goal

Create a recommendation model for the OLPC project.

## Project Steps

1. **Assumptions:**
   - NAPLAN scores for 2014-2016 are assumed to be the same as those recorded in 2012.

2. **Data Preprocessing:**
   - **2.1** Categorize schools by performance (High: top 75%, Low: bottom 25%, Average).
   - **2.2** Merge app usage data with categorized school performance data.

3. **Create Interaction Matrix for LightFM:**
   - **3.1** Normalize aggregated app usage duration per school-app pair.
   - **3.2** Weight interactions by NAPLAN performance, giving higher-performing schools more influence during LightFM training.

4. **Model Training:**
   - Train the model using 80% of the data from 2014-2015.

5. **Model Testing:**
   - Test the model using the remaining 20% of data from 2014-2015.

6. **Validation:**
   - Validate the trained model using data from 2016.
