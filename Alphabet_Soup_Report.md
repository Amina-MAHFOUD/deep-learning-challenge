# **Neural Network Model Report for Alphabet Soup**

## **Overview of the Analysis**
The purpose of this analysis is to develop a binary classification model that can predict whether an applicant receiving funding from the Alphabet Soup foundation will be successful. By leveraging deep learning techniques, we aim to provide the foundation with a data-driven approach to making funding decisions, ultimately improving the success rate of funded ventures.

---

## **Results**

### **Data Preprocessing**
- **Target Variable:**  
  - `IS_SUCCESSFUL` (indicates whether the funding led to a successful outcome)
  
- **Feature Variables:**  
  - `APPLICATION_TYPE`  
  - `AFFILIATION`  
  - `CLASSIFICATION`  
  - `USE_CASE`  
  - `ORGANIZATION`  
  - `STATUS`  
  - `INCOME_AMT`  
  - `SPECIAL_CONSIDERATIONS`  
  - `ASK_AMT`  

- **Removed Variables:**  
  - `EIN` and `NAME` (These are identifiers and do not contribute to the predictive power of the model)

- **Additional Preprocessing Steps:**  
  - Encoded categorical variables using `pd.get_dummies()`  
  - Combined rare categorical values into an `"Other"` category for columns with a large number of unique values  
  - Scaled numerical features using `StandardScaler()`  
  - Split data into training and testing sets  

---

### **Compiling, Training, and Evaluating the Model**
- **Neural Network Architecture:**  
  - **Input Layer:** Number of neurons equal to the number of features after one-hot encoding  
  - **Hidden Layers:**
    - **First hidden layer:** 80 neurons, ReLU activation  
    - **Second hidden layer:** 30 neurons, ReLU activation  
  - **Output Layer:** 1 neuron, Sigmoid activation (for binary classification)  

- **Why These Selections?**  
  - ReLU activation was used in hidden layers to handle non-linearity.  
  - The number of neurons was selected through experimentation, balancing model complexity and performance.  
  - Sigmoid activation was used in the output layer since this is a binary classification problem.  

- **Model Performance:**  
  - Initial accuracy: ~73%  
  - Loss: Moderate, indicating room for improvement  

  ![results](../deep-learning-challenge/First%20model%20results.png)

---

### **Steps Taken to Increase Model Performance**  
To optimize the model and attempt to reach an accuracy above 75%, the following adjustments were made:  

1. **Changed the number of neurons in hidden layers** to better capture patterns in the data.  
2. **Increased the number of epochs** to allow more training iterations and improve learning.  
3. **Added an additional hidden layer** to enhance the model’s capacity for feature extraction.  

- **Final Model Performance:**  
  - Despite these optimizations, the highest achieved accuracy was **73%**, which did not meet the target of 75%.  
  - This suggests that either the dataset lacks sufficient distinguishing features or that a different model architecture may be more effective.  

---

## **Summary & Recommendations**
Since deep learning alone did not achieve the target accuracy, alternative approaches should be explored:  

1. **Try a different machine learning model (e.g., Random Forest, XGBoost)**  
   - These models may perform better on structured data like this dataset.  

2. **Perform hyperparameter tuning**  
   - Systematically adjusting parameters like learning rate, batch size, and dropout rate could improve performance.  

3. **Refine feature engineering**  
   - Creating new meaningful features or removing less relevant ones may help the model distinguish successful applicants more effectively.  

Although the deep learning model did not fully meet expectations, these next steps could provide better results for Alphabet Soup’s funding decision-making process. 🚀
