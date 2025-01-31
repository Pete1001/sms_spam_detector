# SMS SPAM Classification with Linear Support Vector Classification (SVC)

SMS SPAM Detector - Module 21

This project provides an SMS classification solution that uses **Linear Support Vector Classification (SVC)** to classify text messages as **SPAM** or **HAM** (not SPAM). The solution includes a Gradio web application to interact with the trained model, allowing users to input text messages and get instant feedback.

## Features:
- **SMS Classification**: The system uses the `LinearSVC` model to classify SMS messages into two categories: **HAM** and **SPAM**.
- **Gradio Interface**: A simple Gradio interface is used to input SMS text and get the classification results.
- **Public URL**: The Gradio app can be accessed using a public URL, allowing anyone with the link to interact with the model.

## Requirements:
Before running the project, ensure you have the following Python libraries installed:
- `pandas`
- `scikit-learn`
- `gradio`

You can install the required libraries using:
```bash
pip install pandas scikit-learn gradio
```

## Dataset:
The dataset used for training the model is the **SMSSpamCollection.csv** file. The file contains SMS text messages with corresponding labels indicating whether the message is SPAM or not.

### CSV File Format:
- **label**: Whether the message is "SPAM" or "HAM"
- **text_message**: The actual text of the SMS message

## Code Explanation:

### 1. **SMS Classification Function**
The function `sms_classification(sms_text_df)` trains a machine learning model using a pipeline consisting of:
- **TF-IDF Vectorizer**: Converts text into numerical features.
- **Linear Support Vector Classification (SVC)**: A linear SVM classifier to classify the SMS messages.

Steps:
- Split data into training and testing sets (33% for testing).
- Build and train the pipeline.
- Return the trained model (`text_clf`).

### 2. **SMS Prediction Function**
The function `sms_prediction(text, text_clf)` takes a user-inputted text message and the trained model (`text_clf`) and returns whether the message is **SPAM** or **HAM**.

It checks the prediction:
- If the prediction is `HAM`, it returns: `The text message: "{text}", is not SPAM.`
- If the prediction is `SPAM`, it returns: `The text message: "{text}", is SPAM.`

### 3. **Gradio Interface**
The Gradio interface allows users to input text into a textbox, click a button, and receive a prediction.

Key details:
- **Input**: A textbox for the user to enter the SMS message.
- **Output**: A textbox showing whether the message is SPAM or not.
- **Submit Button**: A submit button to send the message for classification.

### 4. **Public URL**
The Gradio app can be launched with a public link, allowing others to access and use the model:
- Run `sms_app.launch(share=True)` to generate the public URL.

## Usage:
1. **Run the Notebook**: After setting up the environment and installing dependencies, run the notebook.
2. **Enter an SMS message**: In the input textbox, type the message you want to test.
3. **Get the Prediction**: The model will predict whether the message is SPAM or not and show the result in the output textbox.

## Example Texts:
Here are a few examples you can test:
1. "You are a lucky winner of $5000!"
2. "You won 2 free tickets to the Super Bowl."
3. "Thanks for registering. Text 4343 to receive free updates on medicare."

## License:
This project is licensed under the MIT License by Pete Link.
