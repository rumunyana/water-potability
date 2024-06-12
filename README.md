water-quality-analysis
This dataset contains water quality measurements and assessments related to potability, which is the suitabsify water samples as potable (1) or not potable (0).ility of water for human consumption. The dataset's primary objective is to provide insights into water quality parameters and assist in determining whether the water is potable or not. Each row in the dataset represents a water sample with specific attributes, and the "Potability" column indicates whether the water is suitable for consumption.

Columns:
pH: The pH level of the water.
Hardness: Water hardness, a measure of mineral content.
Solids: Total dissolved solids in the water.
Chloramines: Chloramines concentration in the water.
Sulfate: Sulfate concentration in the water.
Conductivity: Electrical conductivity of the water.
Organic_carbon: Organic carbon content in the water.
Trihalomethanes: Trihalomethanes concentration in the water.
Turbidity: Turbidity level, a measure of water clarity.
Potability: Target variable; indicates water potability with values 1 (potable) and 0 (not potable).
Objective:
The main objective of this dataset is to assess and predict water potability based on water quality attributes. It can be used for evaluating the safety and suitability of water sources for human consumption, making informed decisions about water treatment, and ensuring compliance with water quality standards.

Machine Learning Task:
This dataset is suitable for a supervised binary classification task, where machine learning models can be trained to predict water potability based on the provided water quality attributes. The models aim to class
Exercise - Creating our own custom Model

This Report provides a step-by-step documentation on the entire process with their result.

Water Quality Dataset Overview
The dataset contains water quality measurements and assessments related to potability, indicating the suitability of water for human consumption. It aims to provide insights into water quality parameters to determine whether the water is potable or not.

Repository:   Link
Dataset Source: Water Quality and Potability

Step 1: Data Preprocessing
1. Imputing Missing Values: Missing values are replaced with the mean of each feature.
2. Normalization: Data is scaled to the same range using feature scaling.
3. Data Splitting: The dataset is split into training and test sets.

Step 2: Model Architecture
An initial model architecture is defined consisting of three dense layers:
- Input layer with 64 units and ReLU activation.
- Hidden layer with 32 units and ReLU activation.
- Output layer with 1 unit and Sigmoid activation.

Step 3: Training Process

1. Model Compilation with early stop: The model is compiled using the Adam optimizer and binary cross-entropy loss with early stop, we got: Train: 0.708, Test: 0.681




2. Without Early Stopping: We tried the model without early stop and we got: Train: 0.936, Test: 0.619



3. L1 regulariztaion with Early Stop and Adam Optimizer: Train: 0.694, Test: 0.692


4. L1 regulariztaion with Early Stop and SGD Optimizer: Train: 0.940, Test: 0.607

5. L1 regulariztaion with Batch Normalization, Early Stop and Adam Optimizer: Train: 0.716, Test: 0.662


6 - L2 regularization with Early Stop and Adam optimizer: Train: 0.711, Test: 0.688




7 - L2 regularization with Dropout,  Early Stop and Adam optimizer: Train: 0.689, Test: 0.691


Step 4: Model Evaluation
Several experiments are conducted to evaluate different model configurations:
1. Comparison of performance with and without early stopping.
2. Evaluation of L1 and L2 regularization techniques.
3. Comparison of different optimizers such as Adam and SGD.

After a thoughtful discussion, we decided to proceed with the model utilizing L1 regularization, early stopping, and the Adam optimizer, as the training and test accuracies were very close.

Step 5: Model Deployment
Unfortunately, we encountered difficulties deploying the model using FAST API after several attempts. Despite our efforts, we were unable to overcome the challenges. In our quest for alternatives, we stumbled upon TensorFlow Lite, a tool that translates Keras models into formats usable on lightweight devices such as smartphones. TensorFlow Lite enables efficient execution on CPUs. Consequently, we saved our model as a TFLite file and directly integrated it into our Flutter application.


Data Usage:
This dataset is valuable for water quality assessment, water treatment planning, and ensuring the safety of drinking water supplies. It can be utilized by water treatment plants, environmental agencies, and researchers to make data-driven decisions regarding water quality and potability.

Data Source:
https://github.com/MainakRepositor/Datasets/blob/master/water_potability.csv

