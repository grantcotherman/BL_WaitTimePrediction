# To the Wait Line... and Beyond!
Using machine learning techniques in KNIME to predict the wait times of Buzz Lightyear's Space Ranger Spin at Walt Disney World

Goals: To deepen knowledge of pandas, machine learning techniques, and KNIME.

### Overview
In this project, I retrieved feature wait time data and feature data from touringplans.com, cleaned and binned the data in Python using the pandas library, and used KNIME to build Artificial Neural Network (ANN) Models, Random Forest models and Logistic Regression models to predict whether the wait time would be "short" (0-15 minutes), "moderate" (20-40 minutes), or "long" (45 minutes +). In the end, I acheived the greatest prediction accuracy with a Random Forest model at 76.4%, with ANN following at 71.7%. Below is a screenshot of my condensed workflow in KNIME, along with a visualization generated from decision tree output depicting the relative importance of different features in generating the prediction model. 

![KNIME Workflow](https://github.com/grantcotherman/BL_WaitTimePrediction/assets/94634170/f359ae1e-dedf-4091-8b1a-e3235b093440)

![BL_FeatureImportance](https://github.com/grantcotherman/BL_WaitTimePrediction/assets/94634170/b68b17b3-f57a-4013-8843-d76adef6ae6b)

## Project Write-Up

### Data Cleaning and Preparation
After retrieving the wait time and feature data from https://touringplans.com, I first looked at the data dictionary to gain insight into the features and then opened up the features dataset in excel. In excel, I removed the features that were related to parks outside of the Magic Kingdom park, which is where this ride is, along with some values that were highly unlikely to contribute to the predictions and values that would be unknown in a prediction scenario. After this first round of removal, I opened up and combined the datasets in a Jupyter Notebook. Using pandas commands, I got looked at the datatypes and used the describe command to better understand the target variable (wait-time). Afterwards, I continued the eploratory analysis by generating visualizations with Matplotlib and Seaborn. See a few of the visualizations below - 

![Box_Whisker](https://github.com/grantcotherman/BL_WaitTimePrediction/assets/94634170/d951baa3-693f-45c2-8b16-04e40fd65e67)

![BL_HeatMap](https://github.com/grantcotherman/BL_WaitTimePrediction/assets/94634170/916ecac8-05c3-4ae4-8239-037e268b5431)

![BL_SeptemberHeatMap](https://github.com/grantcotherman/BL_WaitTimePrediction/assets/94634170/b0fc4c04-34c7-4ebd-be9b-2dc40db7743f)

After gaining a better understanding of the data, I removed the rows with NAs. As the NAs were few and primarily in the insession columns, I decided it would be better to drop the rows compeltely rather than to spend the time building a replacement method for the insession values. 

Next, I binned the target variables (wait_times) into three categories, the temperature variables into four, rounded the times down to the hour, binned park hours to four categories, and finally binned precipitation to two categories. The data dictionary after the binning can be seen below - 

![Data_Dictionary_Ping](https://github.com/grantcotherman/BL_WaitTimePrediction/assets/94634170/9f76b28d-05a7-4521-921a-db1afa48b857)

### Machine Learning Models and Performance
After preparing the features, I loaded the data into KNIME, an image of the condesned workflow is below - 

![KNIME Workflow](https://github.com/grantcotherman/BL_WaitTimePrediction/assets/94634170/f359ae1e-dedf-4091-8b1a-e3235b093440)



### Conclusion and Next Steps
