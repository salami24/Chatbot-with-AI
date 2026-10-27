Chatbot with AI

A Python-based chatbot project that uses a trained machine learning model and a small conversational dataset to generate chatbot responses.

The repository includes a Jupyter Notebook for model development, a JSON dataset containing chatbot data, and a saved Keras model.

Table of Contents

Overview
Features
Technologies Used
Project Structure
Installation and Setup
Running the Project
How It Works
Using the Saved Model
Limitations
Troubleshooting
Future Improvements
License
Author

Overview

The Chatbot-with-AI project explores how a trained neural network can be used to build a conversational chatbot from a relatively small dataset.

The project includes a Jupyter Notebook for developing or exploring the model, a JSON file containing chatbot data, and a saved Keras model that can potentially be loaded for inference.

The objective is to demonstrate a basic machine learning approach to chatbot development and provide a starting point for experimenting with conversational AI.

Unlike a large language model that generates unrestricted text, a chatbot trained on a small dataset may be limited to the patterns and responses represented in its training data.

Features

A trained Keras model for chatbot-related predictions.
A JSON dataset for storing chatbot data.
A Jupyter Notebook for model development and experimentation.
A saved model that can be reused without retraining, provided the required preprocessing pipeline is available.
An educational example of applying neural networks to conversational tasks.

The exact prediction method, response-selection strategy, and supported conversation patterns should be confirmed by reviewing and executing the notebook.

🛠️ Technologies Used
Python — programming language.
TensorFlow/Keras — loading and using the saved neural network model.
Jupyter Notebook — interactive model development.
JSON — structured storage of chatbot data.
NumPy — numerical operations, if required by the notebook.

Project Structure

text
Chatbot-with-AI/
│
├── chatbot.ipynb
├── chatbot_dataset.json
├── chatbot_model.keras
└── README.md

File descriptions
File	Description
chatbot.ipynb	Jupyter Notebook containing the chatbot development workflow.
chatbot_dataset.json	JSON dataset used by the chatbot project.
chatbot_model.keras	Saved Keras model artifact.
README.md	Project documentation and setup instructions.

Installation and Setup

Step 1: Install Python

Download Python from the official website:

https://www.python.org/downloads/

Check your installation:

bash
python --version


Use a Python version supported by the TensorFlow version you install.

Step 2: Install Git

Download Git from:

https://git-scm.com/downloads

Verify the installation:

bash
git --version

Step 3: Clone the repository

Open a terminal and run:

bash
git clone https://github.com/salami24/Chatbot-with-AI.git

Step 4: Navigate to the project directory
bash
cd Chatbot-with-AI

Step 5: Create a virtual environment

A virtual environment helps isolate the project's dependencies.

Windows:

bash
python -m venv venv
venv\Scripts\activate


macOS or Linux:

bash
python3 -m venv venv
source venv/bin/activate

Step 6: Install the dependencies

Install Jupyter Notebook, TensorFlow, and NumPy:

bash
python -m pip install --upgrade pip
python -m pip install notebook tensorflow numpy


The notebook may require additional packages. Review its import statements and install any missing dependencies.

For reproducible installation, create a requirements.txt file containing the dependencies and versions verified to work with the project.

Running the Project

Option 1: Run the Jupyter Notebook

This is the recommended starting point because the notebook contains the project's development workflow.

Step 1: Start Jupyter Notebook:

bash
jupyter notebook


Step 2: Open chatbot.ipynb in the browser.

Step 3: Execute the notebook cells sequentially, beginning with the first cell.

Step 4: Check that the JSON dataset loads correctly and that the model-related cells execute without errors.

Step 5: Follow the notebook's implemented workflow to test the chatbot and inspect its predictions or responses.

Option 2: Load the saved model

The repository includes chatbot_model.keras, a saved Keras model.

You can check whether the model loads successfully using:

python
from tensorflow.keras.models import load_model

model = load_model("chatbot_model.keras")

model.summary()


Run this code from the repository directory.

Loading the model confirms only that Keras can deserialize the model. It does not, by itself, recreate the full chatbot application.

The input preprocessing, tokenizer, vocabulary, label mapping, and response-selection logic must also match the original training workflow.

How It Works

A typical neural-network chatbot pipeline includes the following steps:

Load the dataset: Read the conversational data from chatbot_dataset.json.
Prepare the data: Extract the text and any associated intent or response labels.
Preprocess user input: Transform text into the numerical representation expected by the model.
Run model inference: Pass the processed input to the trained Keras model.
Interpret the prediction: Convert the model output into an appropriate class, intent, or response selection.
Return a response: Display the selected response to the user.

This describes a general chatbot workflow. The exact architecture and sequence used by this repository should be confirmed from chatbot.ipynb.

Using the Chatbot

The repository currently provides a notebook, a dataset, and a saved model. A separate command-line or web-chat interface has not been confirmed.

To test the chatbot:

Open chatbot.ipynb.
Run the notebook cells in order.
Locate the section where the notebook accepts user text or tests predictions.
Enter a sample message using the format expected by the code.
Review the predicted output and response.

If the notebook does not include an interactive chat loop, a separate inference script can be developed using the existing model and its original preprocessing pipeline.

Limitations

A small training dataset may limit the range of supported questions.
Predictions depend on the quality and coverage of the training data.
The model may perform poorly on unfamiliar wording or topics.
The saved model may require preprocessing components that are not stored in the model file.
The project has not been verified as a deployed web application or API.
A successful model load does not guarantee correct conversational responses.

Troubleshooting

1. ModuleNotFoundError

Install the missing package in the active virtual environment:

bash
python -m pip install package-name


Replace package-name with the required package.

2. Model file not found

Make sure chatbot_model.keras is present in the repository directory and that Python is running from the expected working directory.

3. JSON loading error

Check that chatbot_dataset.json exists and contains valid JSON. Review the file's structure before accessing its keys.
