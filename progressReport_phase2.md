Recommendation System using Matrix Factorization (LightFM)

Problem statement: 
"Using a hybrid matrix factorization model, can we recommend apps used by high-performing schools to lower-performing ones, 
potentially bridging digital learning gaps?"

Goal: Create a recommendation model for the OLPC project.

Steps team will take:
1. Assuming the NAPLAN scores for 2014-2016 is the same with 2012
2. Data Preprocessing:
   2.1 Categorize schools by performance (High 75%, Low 25%, Ave)
   2.2 Merge App usage with school performance
3. Create interaction matrix for lightFM using the normalized app usage.
   3.1 Normalise aggregated app usage duration per school-app pair.
   3.2 Weight interactions by NAPLAN performance so that high-performing schools have more influence in LightFM training.
4. Training using 80% 2014-2015 data.
5. Test using 20% 2014-2015 data
6. Validation using 2016 data.
 
