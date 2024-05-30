# Transcription-Factor-Binding-Prediction
In this project, we tackle the task of predicting whether segments of the human chromosome 22 (Chr22) contain binding sites for the JUND transcription factor (TF). We leverage a multilayer perceptron (MLP) model to learn from the data and make accurate predictions.

## Dataset
* The dataset consists of 101-length segments from Chr22, where each position is represented as a one-hot vector denoting one of the four bases (A, C, G, T).
* Each segment has a binary label (0 or 1) indicating whether the TF binds to that region.
* We also have weights associated with each input element to account for class imbalance (only 0.42% binding sites).
* Additionally, an accessibility value per input element provides information about chromosome accessibility.

## Model Architecture
* Our MLP model includes at least one hidden layer.
* The input data (101x4) is flattened into a 404-dimensional vector.
* After passing through the hidden layer (with ReLU activation), we concatenate the accessibility value.
* The final output layer predicts the binding probability (binary classification).

## Training and Evaluation
* We train the model on the training data and use the validation set to tune hyperparameters (epochs, hidden dimension).
* The weighted prediction accuracy (weighted by sample weights) serves as our evaluation metric.
* Finally, we report the weighted accuracy on the test set.

### Achieved Test Weighted Accuracy: 0.6978
