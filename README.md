# Heart Disease Prediction API

![Python](https://badgen.net/badge/Python/3.7/orange)
![License](https://badgen.net/badge/license/MIT/blue)

Flask REST API which predicts probability of Coronary Heart Disease in a patient taking 9 parameters based on patient's history as input.

The API uses a Logistic Regression Model from scikit-learn trained on the [Framingham Heart Study Dataset](https://www.kaggle.com/amanajmera1/framingham-heart-study-dataset) from Kaggle.

The model achieved a test accuracy of around 88%.

It is deployed on [here](https://heart-sn1y.onrender.com/).

View the Jupyter notebook
[here](https://github.com/devesh2511/HeartDiseasePredictionAPI/blob/master/model/HeartDisease.ipynb)

## Predict endpoint

- Takes 9 paramteres as input
- Returns a binary prediction (0 or 1) and probability as well.

	### Sample query
    	https://heart-sn1y.onrender.com/predict?age=31&sex=1&cigs=5&chol=230&sBP=280&dia=0&dBP=90&gluc=87&hRate=84

	### Sample output

      {
         "data":{
            "age":"31",
            "cigsPerDay":"5",
            "diaBP":"90",
            "diabetes":"0",
            "glucose":"87",
            "heartRate":"84",
            "sex":"1",
            "sysBP":"280",
            "totChol":"230"
         },
         "prediction":[
            1
         ],
         "probability":[
            [
               0.4587093009776524,
               0.5412906990223476
            ]
         ]
      }


## /model endpoint
- Returns the model details such as intercept and coefficients.

		https://https://heart-sn1y.onrender.com/model
