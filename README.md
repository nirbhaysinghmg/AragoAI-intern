# AragoAI-intern
Shipment Delay Prediction API
Overview
This Flask API predicts whether a shipment will be delayed or not based on several features like distance, weather conditions, traffic, and shipment day. The model is built using Logistic Regression and exposed via a Flask API to make predictions on new shipment data.

Project Structure
The project consists of the following key components:

app.py: The Flask API that serves the trained Logistic Regression model.
train.py: The script used for training the Logistic Regression model.
model.pkl: The saved trained model.
requirements.txt: List of dependencies required for the project.
Prerequisites
To run this project, you will need:

Python 3.x
Flask
scikit-learn
pandas
Setup Instructions
Step 1: Install Dependencies
First, clone this repository or download the ZIP file. Then, create a virtual environment (recommended) and install the required libraries using the requirements.txt file.

To install the dependencies, run the following command:

bash
Copy code
pip install -r requirements.txt
Step 2: Train the Model
If you need to retrain the model, run the train.py script. This will load the dataset, train the Logistic Regression model, and save it as a .pkl file.

bash
Copy code
python train.py
Step 3: Run the API
Once the model is trained, you can start the Flask API by running the app.py file. This will launch the API on your local server.

bash
Copy code
python app.py
By default, the API will run on http://127.0.0.1:5000/.

Step 4: Test the API with Postman
To test the API using Postman:

Open Postman and create a POST request.

Use the following URL for the request:

arduino
Copy code
http://127.0.0.1:5000/predict
In the Body tab, select raw and choose JSON from the dropdown.

Provide the input features in JSON format. For example:

json
Copy code
{
  "features": [
    100, 3, 12, 1, 0, 0, 0, 0, 0, 0, 0, 0, 0, 1, 0, 0, 0, 0, 0, 0, 0, 1, 0, 1, 0, 0, 1, 0, 1, 0
  ]
}
The features array should contain 30 numerical values corresponding to the features for a shipment.
Click Send to submit the request.

Step 5: View the Result
The API will respond with the prediction:

json
Copy code
{
  "prediction": "On Time"
}
This indicates whether the shipment is predicted to be delayed or not.

Files
app.py: Flask API to make predictions using the trained model.
train.py: Script to train the Logistic Regression model on the data.
model.pkl: The saved trained model that is loaded by the API.
requirements.txt: Contains the list of required Python packages.

