# DengAI-Assignments
Code created in part to serve as assignments for the course ''Data Science Programming" course at USF and for the DengAI challenge.

## Assignment Questions
The questions below relate to the data files associated with the contest with the title 'DengAI: Predicting Disease Spread' published at the following website. 
https://www.drivendata.org/competitions/44/dengai-predicting-disease-spread/data/

Anyone can join the contest and showcase your skills. To know about contest submissions visit the following webpage
https://www.drivendata.org/competitions/44/dengai-predicting-disease-spread/submissions/

You can showcase your Machine Learning skills by ranking top in the contest. 

## Problem description:
Your goal is to predict the total_cases label for each (city, year, weekofyear) in the test set. There are two cities, San Juan and Iquitos, with test data for each city spanning 5 and 3 years respectively. You will make one submission that contains predictions for both cities. The data for each city have been concatenated along with a city column indicating the source: sj for San Juan and iq for Iquitos. The test set is a pure future hold-out, meaning the test data are sequential and non-overlapping with any of the training data. Throughout, missing values have been filled as NaNs.

## Assignment:
The goal is achieved through three subsequent Assignments 1, 2 and 3, all using the same dataset

## Dataset Description
The features in this dataset
You are provided the following set of information on a (year, weekofyear) timescale:

(Where appropriate, units are provided as a _unit suffix on the feature name.)

City and date indicators

    city – City abbreviations: sj for San Juan and iq for Iquitos
    week_start_date – Date given in yyyy-mm-dd format

NOAA's GHCN daily climate data weather station measurements

    station_max_temp_c – Maximum temperature
    station_min_temp_c – Minimum temperature
    station_avg_temp_c – Average temperature
    station_precip_mm – Total precipitation
    station_diur_temp_rng_c – Diurnal temperature range
    
PERSIANN satellite precipitation measurements (0.25x0.25 degree scale)

    precipitation_amt_mm – Total precipitation

NOAA's NCEP Climate Forecast System Reanalysis measurements (0.5x0.5 degree scale)

    reanalysis_sat_precip_amt_mm – Total precipitation
    reanalysis_dew_point_temp_k – Mean dew point temperature
    reanalysis_air_temp_k – Mean air temperature
    reanalysis_relative_humidity_percent – Mean relative humidity
    reanalysis_specific_humidity_g_per_kg – Mean specific humidity
    reanalysis_precip_amt_kg_per_m2 – Total precipitation
    reanalysis_max_air_temp_k – Maximum air temperature
    reanalysis_min_air_temp_k – Minimum air temperature
    reanalysis_avg_temp_k – Average air temperature
    reanalysis_tdtr_k – Diurnal temperature range

Satellite vegetation - Normalized difference vegetation index (NDVI) - NOAA's CDR Normalized Difference Vegetation Index (0.5x0.5 degree scale) measurements

    ndvi_se – Pixel southeast of city centroid
    ndvi_sw – Pixel southwest of city centroid
    ndvi_ne – Pixel northeast of city centroid
    ndvi_nw – Pixel northwest of city centroid

## Assignment Questions

1. Load the file 'dengue_features_train.csv', display the top 3 rows and observe the data. Then programmatically define the column names to make the following changes. 

a). rename columns which have 'station' such that 'station' is abbreviated to 'stn' and rest of column name remains intact. For example column name 'station_diur_temp_rng_c' is renamed to 'station_diur_tmp_rng_c'

b). similarly rename columns which have 'reanalysis' to abbreviate 're_an', retaining rest of column name same

c). rename columns which have 'humidity' to abbreviate to 'hd', retaining rest of column name same

d). abbreviate 'precipitation' part of column name to 'prec', retaining rest of column name same

e). view top 3 rows and recheck if column name changes have taken effect

f). check the type of columns in dataframe

g). Change the column 'year' as categorical variable and check if the column data type is changed and the levels of category are correct. As an example, 'city' is converted into categorical below with two categories (of cities).

2. The predictor column (y-value) is present in the file 'dengue_labels_train.csv'. Read this file in a new dataframe and merge it with the above dataframe using city, year and weekofyear as join conditions. 

Count NANs in merged dataframe and use forward fill method to fill NANs (df_merged.fillna(method='ffill'))

a). Do a random check by printing few values from both files and merged file

b). Do a scatter plot of weekofyear on x-axis and total_cases on y-axis and observe if there is a relationship.

c). Do a box plot to observe the density of data and if it complies to Central Limit Theorem (for large enough data, mean of sample is mean of population, or data is tightly packed close to the mean)

d). Find the mean, min, max and standard deviation of total_cases by city

e). Read the relationship between mean and standard deviation from the link given here and describe the data of total_cases by city, if there is too much variation or too little variation https://www-users.york.ac.uk/~mb55/msc/applbio/week3/sd_text.pdf

3. How many years in the city iq have greater than or equal to 50 total_cases of dengue and in which years?

4. Optional Question (no credit, or no extra credit): Find and remove the outliers to bring the mean and standard deviation closer to each other.

5. Create a temp data frame by grouping the total_cases by weekofyear and draw a histogram of total_cases and provide insights based on the distribution. 
