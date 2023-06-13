# Data-Engineering-AWS



| Books and Resources | Status of Completion |
| ----- | -----|
| 1. [**Data Engineering with Python**](https://www.amazon.in/Data-Engineering-Python-datasets-pipelines/dp/183921418X/ref=asc_df_183921418X/?tag=googleshopdes-21&linkCode=df0&hvadid=396987756195&hvpos=&hvnetw=g&hvrand=12838524652674757320&hvpone=&hvptwo=&hvqmt=&hvdev=c&hvdvcmdl=&hvlocint=&hvlocphy=9299139&hvtargid=pla-1066688867037&psc=1&ext_vrnc=hi) |  |



<br />

| Projects and Notebooks |
| ---------------------- |
| 1. [**Python-Postgres-Integration**](https://github.com/andysingal/postgres_python)|


One of the benefits of developing data science projects in the cloud is the smooth transition from prototype to production. We can switch from running model prototyping code in our notebook to running data-quality checks or distributed model training across petabytes of data within minutes. And once we are done, we can deploy our trained models to serve real-time or batch predictions for millions of users across the globe.
![11](https://github.com/andysingal/Data-Engineering-AWS/blob/main/Images/Screenshot%202023-06-13%20at%2011.59.30%20AM.png)

<h2> Amazon SageMaker Pipelines</h2>
Amazon SageMaker Pipelines are the standard, full-featured, and most complete way to implement AI and machine learning pipelines on Amazon SageMaker. SageMaker Pipelines have integration with SageMaker Feature Store, SageMaker Data Wrangler, SageMaker Processing Jobs, SageMaker Training Jobs, SageMaker Hyper-Parameter Tuning Jobs, SageMaker Model Registry, SageMaker Batch Transform, and SageMaker Model Endpoints.

<h2> AWS Step Functions Data Science SDK </h2>
Step Functions, a managed AWS service, is a great option for building complex workflows without having to build and maintain our own infrastructure. We can use the Step Functions Data Science SDK to build machine learning pipelines from Python environments, such as Jupyter Notebook.

<h2>MLOps Best Practices</h2>
The field of machine learning operations (MLOps) has emerged over the past decade to describe the unique challenges of operating “software plus data” systems like AI and machine learning. With MLOps, we are developing the end-to-end architecture for automated model training, model hosting, and pipeline monitoring. Using a complete MLOps strategy from the beginning, we are building up expertise, reducing human error, de-risking our project, and freeing up time to focus on the hard data science challenges.

We’ve seen MLOps evolve through three different stages of maturity:

- MLOps v1.0
Manually build, train, tune, and deploy models
- MLOps v2.0
Manually build and orchestrate model pipelines
- MLOps v3.0
Automatically run pipelines when new data arrives or code changes from deterministic triggers such as GitOps or when models start to degrade in performance based on statistical triggers such as drift, bias, and explainability divergence
AWS and Amazon SageMaker Pipelines support the complete MLOps strategy, including automated pipeline retraining with both deterministic GitOps triggers as well as statistical triggers such as data drift, model bias, and explainability divergence. 

<h2> Operational Excellence </h2>
Here are a few machine-learning-specific best practices that help us build successful data science projects in the cloud:

Data-quality checks
Since all our ML projects start with data, make sure to have access to high-quality datasets and implement repeatable data-quality checks. Poor data quality leads to many failed projects. Stay ahead of these issues early in the pipeline.
- Start simple and reuse existing solutions
- Start with the simplest solution as there is no need to reinvent the wheel if we don’t need to. There is likely an AI service available to solve our task. Leverage managed services such as Amazon SageMaker that come with a lot of built-in algorithms and pre-trained models.
- Define model performance metrics
- Map the model performance metrics to business objectives, and continuously monitor these metrics. We should develop a strategy to trigger model invalidations and retrain models when performance degrades.
- Track and version everything
- Track model development through experiments and lineage tracking. We should also version our datasets, feature-transformation code, hyper-parameters, and trained models.
Select appropriate hardware for both model training and model serving
In many cases, model training has different infrastructure requirements than does model-prediction serving. Select the appropriate resources for each phase.
Continuously monitor deployed models
Detect data drift and model drift—and take appropriate action such as model retraining.
- Automate machine learning workflows
Build consistent, automated pipelines to reduce human error and free up time to focus on the hard problems. Pipelines can include human-approval steps for approving models before pushing them to production.
