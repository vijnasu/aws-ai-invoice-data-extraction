# Deploy ML Models with Amazon SageMaker

Once your machine learning models have been trained, the next step is deploying them to make predictions. Amazon SageMaker provides a straightforward mechanism for deploying trained models as endpoints, which can be easily accessed for real-time or batch predictions. This guide will walk you through the deployment process.

## Prerequisites:

- AWS account with access to Amazon SageMaker.
- Trained SageMaker model(s) from the previous steps.
- Basic understanding of AWS services.

## Steps:

### 1. Open SageMaker Console

- Navigate to the SageMaker dashboard within the AWS Console.

### 2. Locate Trained Models

- In the SageMaker dashboard, click on "Training jobs".
- Locate the training job corresponding to your trained model. Click on its name to view details.

### 3. Deploy Custom Data Extraction Model

- From the training job details page, click on the “Create model” button.
- Give your model a name and configure any necessary permissions.
- Once the model is created, click on “Create endpoint”.
- Provide an endpoint name and choose an instance type suitable for your prediction workload.
- SageMaker will now deploy your model, which may take several minutes. Once deployed, the status will change to "InService".

```python
# You can also deploy directly from the SageMaker SDK in a notebook:

from sagemaker.model import Model

model = Model(model_data='s3://path-to-your-model/model.tar.gz',
              image_uri='image_uri_from_training_step',
              role=get_execution_role())
predictor = model.deploy(initial_instance_count=1, instance_type='ml.m5.large')
```

### 4. Deploy Generative AI Model
Repeat the same steps as the custom data extraction model to deploy your Generative AI model.

### 5. Testing the Endpoint
Once your models are deployed and the endpoints are "InService", you can start making real-time predictions.

```
# Using the SageMaker SDK in a notebook:

result = predictor.predict(your_input_data)
print(result)
```

Remember, the input data should be in the same format as the data the model was trained on.

### 6. Endpoint Management
- SageMaker endpoints are live resources and will incur charges as long as they are running. Make sure to shut down endpoints when they are not in use.
- To shut down an endpoint: Navigate to the "Endpoints" section in the SageMaker dashboard, select the endpoint, and choose "Delete".

### Conclusion
With your ML models deployed as SageMaker endpoints, you can now easily integrate them into applications, services, or further processes. Ensure you manage the endpoints effectively to optimize costs and performance.
