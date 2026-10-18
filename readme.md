# Prediction Model Based on SSA-Optimized Algorithm for CEEMDAN-Transformer-BiGRU

1. Introduction
This paper introduces a comprehensive application of the Complete Ensemble Empirical Mode Decomposition (CEEMDAN) and the SSA-Transformer-BiGRU prediction model, based on the wind speed data (dataset attached at the end of this document), to enhance the predictive performance of time series data. The core of this method is to decompose the time series using the CEEMDAN algorithm, followed by optimizing the Transformer-BiGRU model with the SSA-Transformer-BiGRU prediction model using the Sparrow Optimization Algorithm. By modeling the decomposed data, we achieve precise predictions.
1. Wind Speed Data CEEMDAN Decomposition and Visualization
\t1.1 Importing Data
\t1.2 CEEMDAN Decomposition
According to the decomposition results, CEEMDAN has decomposed into 11 components, which are used as inputs for the SSA-Transformer-BiGRU model for prediction.
2. Dataset Preparation and Preprocessing
\t2.1 Dataset Division
\t2.2 Preprocessing
3. Sparrow Optimization Algorithm
\t3.1 Introduction to Sparrow Optimization Algorithm
The Sparrow Optimization Algorithm (SOA) is an optimization algorithm based on the characteristics of bird behavior in nature, simulating the optimization strategies of birds in foraging, migration, and social interactions. This algorithm has shown good performance in solving various optimization problems.
The basic idea of the Sparrow Optimization Algorithm is to optimize the solution in the search space through mimicking the foraging behavior of birds. The process can be divided into three stages: foraging behavior, migration behavior, and social behavior.
1. Foraging Behavior: Sparrows select food sources that are closer and have higher adaptability when foraging. In the algorithm, each individual in the solution space is considered a food source with an adaptability evaluation value. Sparrows seek out better solutions by selecting individuals with higher adaptability.
2. Migration Behavior: When sparrows search around a food source for a certain period without finding a better solution, they will choose to leave the current food source and head to other food sources to continue searching. In the algorithm, the position information between individuals will change to simulate the migration behavior of sparrows.
3. Social Behavior: While foraging, sparrows exchange information with other sparrows to gain more information and improve their foraging efficiency. In the algorithm, individuals exchange information to enhance their solutions and update the optimal solution in the solution space.
\t3.2 Python-based Sparrow Optimization Algorithm Implementation
\t3.3 Sparrow Optimization Algorithm - Parametric Optimization Process
The Sparrow Optimization Algorithm has the characteristics of simplicity, easy implementation, global optimization capability, and self-adaptability, making it suitable for solving combinatorial optimization problems. We use the Sparrow Optimization Algorithm to optimize the hyperparameters of the Transformer-BiGRU model.
By setting an appropriate population size and number of optimization iterations, we search for the optimal parameters within the given hyperparameter range.
4. CEEMDAN-Based SSA-Transformer-BiGRU Model Prediction
\t4.1 Define the SSA-Transformer-BiGRU prediction model
\tNote:
\tInput dimension is 11, representing the 11 components of CEEMDAN decomposition
\tInput shape is torch.Size([64, 24, 11])
\tBatch size=64, 24 represents the sequence length (the sliding window takes values)
In the use of Transformer models with multi-head attention, the input dimensions must be divisible by the number of heads (num_heads). This is because in the multi-head attention mechanism, the input embedding vectors are divided into multiple heads, each head's dimension is `embed_dim / num_heads`, so `embed_dim` must be divisible by `num_heads` to ensure an even distribution of the input to each attention head.

Since at this time CEEMDAN decomposition components are 11, this paper adopts a half-split stacking approach to divide the data, resulting in an input shape of [64, 12, 22].

4.2 Set parameters and train the model
After 50 epochs, the MSE is 0.008368, and the SSA-Transformer-BiGRU prediction results are satisfactory. By appropriately adjusting the model parameters, the model prediction performance can be further improved.

Note to adjust parameters:
- Modify the population size and optimization iterations of the bird optimization algorithm;
- Adjust the parameter search range for the number of layers and dimensions of the Transformer and BiLGRU layers, increasing more epochs (be cautious to prevent overfitting);
- Change the sliding window length (set a suitable window length);
- Save training results and prediction data;
- 4.3 Model evaluation
- Prediction component evaluation, visualization of results
- The prediction results from the component evaluation show that the 11 components fit well under the SSA-Transformer-BiGRU prediction model, with high prediction accuracy.
- Overall model evaluation:

## Images

<!-- PAYMENT_BLOCK -->

## Get this dataset

- Payment link (Stripe): [Buy now](https://buy.stripe.com/3cs8yP7sY87d0vu9AB)
- Payment QR code: ![Payment QR code](pay.png)

<!-- /PAYMENT_BLOCK -->
