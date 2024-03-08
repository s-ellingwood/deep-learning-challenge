# deep-learning-challenge
The 'deep-learning-challenge' folder contains two files:
* started_code.ipynb: contians the code for preprocessing and building of the initial model.
* AlphabetSoupCharity_Optimization: contains the code for preprocessing and attempt 1-3 of building an optimized model.


# Module 21 Report

## Overview of the Analysis
The purpose of this analysis was to create a tool for Alphabet Soup that could help them select applicants for funding with the best chance of success in their ventures. The analysis uses a csv of 34,000 organizations that have received funding from Alphabet Soup over the years. The data contains factors such as application type, affiliated sector of industry, government organization classification, use case of funding, organization type, active status, income classification, special considerations for application, funding amount requested, and the identification columns (both dropped for the purpose of analysis) titled EIN and NAME. The variable that we try to predict using this model is the IS_SUCCESSFUL variable.

The data was split into y labels (IS_SUCCESSFUL) and X features (all other factors listed above). The data was then split using test_train_split and scaled using StandardSclaer. A neural network model was then created using Keras Tuner (tf.keras) and trained using .fit with 100 epochs.

## Results
* Initial Neural Network (started_code.ipynb)
  * **Neurons, Layers, and Activation Functions:** There are two hidden layers in the initial model, the first one having 80 neurons and the second having only 30 neurons. Both use the 'ReLU' activation function as it helps to reduce the vanishing gradient problem.
  * **Able to acieve target model performance?** Unfortunately, no. The target model performance was an accuracy of 0.75 or higher. This initial model only had an accuracy of 0.7287.

* Optimization Attempt 1 (AlphabetSoupCharity_Optimization.ipynb)
  * **Steps taken to increase model performance:** For this first attempt at optimizing the model, all preprocessing and activation functions remained the same. However, the neurons for both of the two hidden layers were increased.
  * **Neurons, Layers, and Activation Functions:** Hidden layer 1 was increased from 80 to 200 neurons and hidden layer 2 was increased from 30 to 40 neurons. Activation functions remained the same - both layers kept the 'ReLU' activation function.
  * **Able to acieve target model performance?** Once again, unfortunately no. This model, while better than the initial model, did not achieve the desired accuracy of 0.75 and, instead, actually performed worse with an accuracy of only 0.7313.

* Optimization Attempt 2 (AlphabetSoupCharity_Optimization.ipynb)
  * **Steps taken to increase model performance:** For this second attempt, neurons and layers were both increased from the values in the initial model.
  * **Neurons, Layers, and Activation Functions:** Hidden layer 1 was again increased to 200 neurons, hidden layer 2 was increased to 40 neurons, and the new hidden layer 3 was given 30 neurons. Activation functions, again, stayed the same.
  * **Able to acieve target model performance?** While still not achieving the desired performance, this model did improve from the initial model with an accuracy of 0.7289. However, it performed worse than optimization attempt 1.
  
* Optimization Attempt 3 (AlphabetSoupCharity_Optimization.ipynb)
  * **Steps taken to increase model performance:** For this third and final attempt, the first step taken was in the preprocessing step. Instead of only dropping EIN and NAME, the STATUS column was also dropped. The number of neurons and layers were copied from optimization attemp 1 as it has performed the best so far in terms of accruacy.
  * **Neurons, Layers, and Activation Functions:** As seen in optimization attempt 1, this third optimization attempt model increased the number of neurons on hidden layer 1 from 80 to 200 and hidden layer 2 from 30 to 40.
  * **Able to acieve target model performance?** While still, unfortunately, not achieving an accuracy of 0.75, this model did perform better than optimization attempt 2 with an accuracy of 0.7292.

## Summary
While I was unable to achieve the desired performance of an accuracy of 0.75, I would recommend that the model from Optimization Attempt 1 continue to be built upon as it performs the best out of all 3 optimization attempts. I might recommend continuing to increase the number of neurons in each of those layers until an accuracy of 0.75 is achieved. It could also be beneficial to look into other activation functions. I may also recommend increasing the number of hidder layers, but with different numbers of neurons. I would also suggest adding more than 1 extra hidden layer as the patterns within this larger dataset, with many features, may be more complex than what 2 or 3 hidden layers can gauge accurately.
