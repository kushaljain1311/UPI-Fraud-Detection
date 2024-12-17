# ML Based UPI Fraud Detection

UPI Fraud Detection refers to the process of identifying and preventing fraudulent activities in transactions conducted via the Unified Payments Interface (UPI). UPI is a real-time payment system developed by the National Payments Corporation of India (NPCI) that allows instant money transfers between bank accounts using a mobile device. With the widespread adoption of UPI, the risk of fraud has also increased, necessitating effective fraud detection mechanisms.

This project leverages a Convolutional Neural Network (CNN) to detect fraudulent transactions in a UPI system. The model processes transaction data to classify it as either legitimate or fraudulent, aiding in proactive fraud prevention.

## Project Overview
Fraud detection in UPI transactions is critical due to the increasing volume of digital payments. By analyzing transaction patterns, this project demonstrates how CNNs can effectively identify fraudulent activities.

### Key Features
- Data preprocessing, including encoding categorical variables and scaling features.
- Implementation of a CNN model to detect fraudulent transactions.
- Real-time prediction capability to classify new transactions.
- Saving and loading the trained model for reuse.

## Dataset
The dataset should contain the following columns:
- **TransactionID**: Unique identifier for the transaction (not used for training).
- **Amount**: Transaction amount.
- **Time**: Time of the transaction (can be categorical or numerical).
- **IsFraud**: Target variable indicating whether the transaction is fraudulent (1 for fraud, 0 for legitimate).
- Additional features relevant to transaction patterns.

> Note: Replace `upi_transactions.csv` with your actual dataset file.

## Project Setup
1. Clone the repository and navigate to the project directory:
   ```bash
   git clone <repository-url>
   cd upi_fraud_detection
   ```

2. Install required libraries:
   ```bash
   pip install numpy pandas scikit-learn keras tensorflow
   ```

3. Place your dataset file (`upi_transactions.csv`) in the project directory.

## Running the Project
1. Train the model:
   ```bash
   python upi_fraud_detection.py
   ```
2. Monitor training and evaluation results in the console.
3. Use the saved model (`upi_fraud_detection_model.h5`) for predictions on new data.

## Model Architecture
- **Conv1D Layers**: Extract temporal patterns from transaction data.
- **Dropout Layers**: Prevent overfitting by randomly deactivating neurons during training.
- **Dense Layers**: Fully connected layers for classification.

### Training Parameters
- Optimizer: Adam
- Loss Function: Categorical Crossentropy
- Epochs: 10
- Batch Size: 32

## Example Prediction
You can test the model on a sample transaction:
```python
# Example prediction
sample_transaction = np.array([X_test[0]])
prediction = model.predict(sample_transaction)
print(f"Fraud Probability: {prediction}")
```

## Results
After training, the model provides:
- **Test Accuracy**: Indicates the percentage of correct classifications on unseen data.
- **Test Loss**: Measures the error in predictions.

## Future Improvements
- Enhance the dataset by including more features, such as device information or geographic location.
- Implement a more sophisticated model architecture for improved accuracy.
- Integrate the model with a real-time UPI system for live fraud detection.


