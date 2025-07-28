# Restaurant_statistics
Statistical analysis of Kaggle restaurant dataset

This analysis code takes in the 4 input files, which represent the Kaggle Restaurant dataset. The original file was too large, and thus has been split. The code recombines and shuffles the data to randomize it. Currently, the model aims to predict restaurant rating based on 3 other variables - city, cuisine and prices. If the code is run with relayCoefficient set to zero, then it will analyze actual rating vs. city/cuisine/prices. The output shows RMS error after each epoch, and then at the very end, the variance number is given for the rating. If the model's predictive power were equal to random chance, the RMS error should come out no less than the variance of the data. A lower RMS error implies the model is able to have some predictive capacity.

By setting relayCoefficient to a larger number (such as 0.002), the rating data is artifically altered by adding to it a complicated function which depends deterministically on city/cuisine/prices. If the model were "perfect", then the RMS error would not increase, because the model would capture the full effect of this deterministic function on the outputs. If the model is no better than random chance, then the RMS error would increase as fast as the variance of the (altered) rating numbers, as relayCoefficient is increased. For a model that is useful but imperfect, the RMS error will slowly increase as relayCoefficient increases, but not nearly as fast as the variance of the rating values. 


Thus, this test combines actual data with synthetic functions in order to better characterize the model's performance relative to what is possible based on mathematical theory, while retaining the ability to run the model for actual prediction of the unaltered rating data.

To run the code, clone the repository and change the file paths in the code to the correct folder containing the input data files, before running the code. 
