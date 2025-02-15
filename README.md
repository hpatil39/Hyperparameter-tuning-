# README: LSTM Model for Sequence-Based Prediction

## Project Overview
This project involves building a deep learning model using LSTM (Long Short-Term Memory) networks for sequence-based predictions. The model is optimized using Keras Tuner's RandomSearch to fine-tune hyperparameters for better performance. The primary objective is to predict target values from sequence data provided in `train.csv` and `test.csv`.

## Dependencies
Ensure the following dependencies are installed before running the script:

```bash
pip install pandas numpy keras tensorflow scikit-learn keras-tuner
```

## Data Description
The project utilizes two datasets:
- **train.csv**: Contains labeled sequence data used for training the model.
- **test.csv**: Contains unlabeled sequence data for prediction.

### Assumed Columns in the Data:
- `sequence`: The main feature containing string sequences.
- `target`: The target variable for training.
- `id`: Unique identifier for test data predictions.

## Workflow
1. **Data Preprocessing**:
   - Tokenize the character-based sequences.
   - Convert sequences into numerical format.
   - Pad sequences to a uniform length.
   - Normalize the data using MinMaxScaler.
   - Reshape the data to fit the LSTM model input requirements.

2. **Model Building & Hyperparameter Tuning**:
   - Use Bidirectional LSTM layers with dropout and L2 regularization.
   - Apply Keras Tuner's `RandomSearch` for hyperparameter tuning.
   - Optimize parameters such as LSTM units, dropout rates, and learning rate.

3. **Model Training & Validation**:
   - Train the model using `adam` optimizer and `mse` loss function.
   - Use early stopping and learning rate reduction techniques.
   - Perform validation split (80-20) to monitor performance.

4. **Prediction & Output**:
   - The best-tuned model is used to predict target values for the test set.
   - Predictions are stored in `predictions.csv` with columns `id` and `target`.

## Results Summary
- The tuning process optimized the validation loss to **18.6395**.
- Total training and tuning time: **~2 hours 42 minutes**.
- Final model performance can be improved further with additional feature engineering and more tuning trials.

## How to Run the Script
1. Place `train.csv` and `test.csv` in the same directory as the script.
2. Run the script using:
   ```bash
   python script_name.py
   ```
3. The output predictions will be saved in `predictions.csv`.


