# Week 6: Report, Revamp and Experimentation

### Experiment 2 (DONE)
School hours-based model - data input will be using activity logs (school hours vs outside school hours)

Where:
Users = Schools
Items = Apps

For Hybrid filtering, we used the following features:

Users - NAPLAN (bin scores)
Items - Category, App rating

### Revamp Homepage (In Progress)

### Report (In Progress)

# Week 5: Experimentation
## Experiment 1 (DONE)
Base model - Interaction matrix with equal importance (no weights)
Where:
Users = Schools
Items = Apps

For Hybrid filtering, we used the following features (best performing):

Users - NAPLAN (bin scores)
Items - Category, App rating

## Experiment 2 (TODO)
School hours-based model - data input will be using activity logs (school hours vs outside school hours)

Where:
Users = Schools
Items = Apps

For Hybrid filtering, we used the following features:

Users - NAPLAN (bin scores)
Items - Category, App rating

## Experiment 3 (TODO)
Feedback-based model - Interaction matrix with app rating as importance

Where:
Users = Schools
Items = Apps

For Hybrid filtering, we used the following features:

Users - NAPLAN (bin scores)
Items - Category

## Frontend Revamp
![image](https://github.com/user-attachments/assets/df7a8335-34cf-46bd-b2f9-53d5c31a5f11)

## App Recommender
1. The system first looks up School ID 20 in its database.
2. It checks which apps your school has already used.
3. Scoring Available Apps: For apps the school hasn't tried yet, the system calculates a score based on:
   3.1 Which apps school's similar to the ones schools have used
   3.2 Patterns it has learned from the overall data about which schools like which apps
4. It ranks all potential apps by their scores from highest to lowest.
5. It returns the top apps (usually 5 or 10) with their details like category and rating.


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
