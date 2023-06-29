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
![12](https://github.com/andysingal/Data-Engineering-AWS/blob/main/Images/Screenshot%202023-06-29%20at%202.12.14%20PM.png)

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

<h2>Label Training Data with SageMaker Ground Truth</h2>
Many data science projects implement supervised learning. In supervised learning, our models learn by example. We first need to collect and evaluate, then provide accurate labels. If there are incorrect labels, our machine learning model will learn from bad examples. This will ultimately lead to inaccurate predictions. SageMaker Ground Truth helps us to efficiently and accurately label data stored in Amazon S3. SageMaker Ground Truth uses a combination of automated and human data labeling.

SageMaker Ground Truth provides pre-built workflows and interfaces for common data labeling tasks. We define the labeling task and assign the labeling job to either a public workforce via Amazon Mechanical Turk or a private workforce, such as our coworkers. We can also leverage third-party data labeling service providers listed on the AWS Marketplace, which are prescreened by Amazon.

SageMaker Ground Truth implements active learning techniques for pre-built workflows. It creates a model to automatically label a subset of the data, based on the labels assigned by the human workforce. As the model continuously learns from the human workforce, the accuracy improves, and less data needs to be sent to the human workforce. Over time and with enough data, the SageMaker Ground Truth active-learning model is able to provide high-quality and automatic annotations that result in lower labeling costs overall


<h3>Data Transformation with AWS Glue DataBrew, SageMaker Data Wrangler, and SageMaker Processing Jobs</h3>

Now let’s move on to data transformation. We assume we have our data in an S3 data lake, or S3 bucket. We also gained a solid understanding of our dataset through the data analysis. The next step is now to prepare our data for model training.

Data transformations might include dropping or combining data in our dataset. We might need to convert text data into word embeddings for use with natural language models. Or perhaps we might need to convert data into another format, from numerical to text representation, or vice versa. There are numerous AWS services that could help us achieve this.

AWS Glue DataBrew is a visual data analysis and preparation tool. With 250 built-in transformations, DataBrew can detect anomalies, converting data between standard formats and fixing invalid or missing values. DataBrew can profile our data, calculate summary statistics, and visualize column correlations.

We can also develop custom data transformations at scale with Amazon SageMaker Data Wrangler. SageMaker Data Wrangler offers low-code, UI-driven data transformations. We can read data from various sources, including Amazon S3, Athena, Amazon Redshift, and AWS Lake Formation. SageMaker Data Wrangler comes with pre-configured data transformations similar to AWS DataBrew to convert column types, perform one-hot encoding, and process text fields. SageMaker Data Wrangler supports custom user-defined functions using Apache Spark and even generates code including Python scripts and SageMaker Processing Jobs.

SageMaker Processing Jobs let us run custom data processing code for data transformation, data validation, or model evaluation across data in S3. When we configure the SageMaker Processing Job, we define the resources needed, including instance types and number of instances. SageMaker takes our custom code, copies our data from Amazon S3, and then pulls a Docker container to execute the processing step.

SageMaker offers pre-built container images to run data processing with Apache Spark and scikit-learn. We can also provide a custom container image if needed. SageMaker then spins up the cluster resources we specified for the duration of the job and terminates them when the job has finished. The processing results are written back to an Amazon S3 bucket when the job finishes.

