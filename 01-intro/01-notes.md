
### Some good practices for notebooks

- When working with notebooks we frequently test different models with different parameters, however when we go back to it we forget which where the best parameters. Better to log these experiments to something called `experiment tracker`
- Another issue, is that we ran multiple models, we could save these models in something called `model registry` with its performance mapped to the model.
    - This is done with MLFlow to keep track of these models.
- ML pipelines help automate and breakdown a notebook into correct steps so that each step is run correctly.

Steps for ML Model - we should standardize and parameterize the pipeline
1. Load and prepare data
2. Vectorize the dataframe
3. Train
4. Get trained model 
5. Put the model in the machine learning service so that clients can communicate with the service.
    - Other ways to deploy a machine learning model
6. Once users start using the model, we need to start monitoring the model to see if there is a drop in performance
7. Potentially automate and retrain a new model with newer data 


### 1.5 MLOps Maturity Model

- Usually start with level 1 which is no MLOps when a model is unproven. When the model is being proven.
- Most models do not need full mlops automation (only necessary when we have a very important or essential service) usually having a model/process at level 2 or 3 works for most cases.
- Being at level 4 is very rare for most use cases.

Different levels of machine learning projects
1. No MLOps and no automation - this is good for experimenting with different models
2. Devops, no MLOps 
    - releases are automated
    - unit and integration tests
    - CI/CD piepleine
    - Ops metrics
    - No experiment tracking
    - No reproducibility
    - DS seperated from the engineers
3. Automated training (when you have 2-3 models/services use this level)
    - Training pipeline
    - Experiment tracking
    - Model registry with training being automated
    - Low friction deployment
4. Automated deployment (5 to 6 use cases)
    - Easy to deploy model
    - Have a place to store the model with an API
    - Have A/B tests 
    - Models are monitored for performance
5. Full MLOps automation
    - Automatic training, automatic monitoring and automatic model retraining

