# Flower Classification
Machine Learning End to End Project on flower Classification, using Tensorflow Keras CNN model.

The model is trained in Google Colab, using GPU, and then saved.

The saved model is deployed in Google Cloud Platform (GCP).

It is tested sending an HTTP request to the URL corresponding to the model deployed in GCP. The HTTP request is sent using Postman and it contains a flower image file, receiving a response containing the corresponding flower classification.

## Training the model

Dataset can be downloaded from here: https://www.kaggle.com/alxmamaev/flowers-recognition/download

Upload Flower_recognition Jupyter notebook to Google Colab:

https://colab.research.google.com/

Enable GPU acceleration:
Go to runtime/change runtime type, select GPU for hardware acceleration. Now you can run your training on GPU 

## Deploying the Tensorflow TF Model (.h5) on GCP
1.	Create a [GCP Account](https://console.cloud.google.com/)
2.	Create a [Project on GCP](https://cloud.google.com/appengine/docs/standard/nodejs/building-app/creating-project) (Keep note of the project id)
3.	Create a [GCP bucket](https://console.cloud.google.com/storage/browser/)
4.	Upload the tf .h5 model generated in the bucket 
5.	Install Google Cloud SDK ([Setup instructions](https://cloud.google.com/sdk/docs/quickstarts)).
6.	Authenticate with Google Cloud SDK:

gcloud auth login

7.	Run the deployment script:

cd gcp

gcloud functions deploy predict --runtime python38 --trigger-http --memory 512 --project project_id


Your model is now deployed.

Use Postman to test the GCF using the Trigger URL.
