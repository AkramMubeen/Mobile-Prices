# Mobile Price Classification

## Table of Contents 
1. [Problem Definition](#problem-definition)
2. [Project Outline](#project-outline)
3. [How to Run the Project](#how-to-run-the-project)

## Problem Definition
Classifying mobile device prices based on various features is a complex task. This project aims to automate this process by building a model that predicts the price range of a mobile device using its features. The dataset used for this project can be found [here](https://www.kaggle.com/datasets/iabhishekofficial/mobile-price-classification?select=train.csv).

## Project Outline 
- [Jupyter Notebook](https://github.com/AkramMubeen/Mobile-Prices/blob/main/Mobile%20Price.ipynb): The notebook covers data cleaning, exploratory data analysis, and the training of different machine learning models to predict mobile prices.
 
- [Training the Model](https://github.com/AkramMubeen/Mobile-Prices/blob/main/train.py): This script performs the final training of the selected model and saves it for later use on new data.

- [Creating a Flask App](https://github.com/AkramMubeen/Mobile-Prices/blob/main/predict.py): This script creates a Flask app that utilizes the trained model to classify new devices when their features are sent to the app.

- [Testing the Service](https://github.com/AkramMubeen/Mobile-Prices/blob/main/request.py): This script tests the classification service by sending a request to the Flask app, which returns the predicted price range of the device.

- [Creating a Dockerfile](https://github.com/AkramMubeen/Mobile-Prices/blob/main/Dockerfile): The Dockerfile is used to create a virtual environment and run the classification service within it.

## How to Run The Project
Please follow these steps to run the project:

1. Clone the repository to your computer:
   ```bash
   git clone https://github.com/AkramMubeen/Mobile-Prices.git
   ```

2. Navigate to the project directory:
   ```bash
   cd Mobile-Prices
   ```

3. Create a virtual environment using venv:
   ```bash
   python -m venv mobile-env
   ```

4. Activate the virtual environment:
   - On Windows:
     ```bash
     mobile-env\Scripts\activate.bat
     ```
   - On UNIX or MacOS:
     ```bash
     source mobile-env/bin/activate
     ```

5. Install the required libraries from the `requirements.txt` file:
   ```bash
   pip install -r requirements.txt
   ```

6. Retrain the model (optional):
   ```bash
   python train.py
   ```

7. Run the Flask app locally:
   - Directly:
     ```bash
     python predict.py
     ```
   - With Waitress:
     ```bash
     waitress-serve --listen=0.0.0.0:9696 predict:app
     ```
   - With Gunicorn:
     ```bash
     gunicorn --bind 0.0.0.0:9696 predict:app
     ```

8. Send a POST request to the service:
   ```bash
   python request.py
   ```

9. Build and run the Docker container (optional):
   ```bash
   docker build -t mobile_price_class .
   docker run -it --rm -p 9696:9696 mobile_price_class:latest
   ```


## Contact Me 
[<img src="https://img.shields.io/badge/Akram-Mubeen-000000?style=flat-square&logo=github&logoColor=white" />](https://github.com/AkramMubeen) [<img src="https://img.shields.io/badge/LinkedIn-0077B5?style=flat-square&logo=LinkedIn&logoColor=white" />](https://www.linkedin.com/in/akrammubeen/)
