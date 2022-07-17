# Part  II :MLOPS 's Architecture and Workflow

On the reference of identified principles, components, and roles, we design a generalized MLOps end-to-end architecture to give ML researchers and practitioners proper shape.


###  (A) MLOps project initiation.

 * (1) The business stakeholder (R1) analyzes the business and identifies a potential business problem that can be solved using ML.
 * (2) The solution architect (R2) defines the architecture design for the overall ML system and, decides on the technologies to be used once a thorough evaluation. 
* (3) The data scientist (R3) derives an ML problem—such as whether regression or classification should be used—from the business goal.
* (4) The data engineer (R4) and the data scientist (R3) work together in an effort to understand which data is required to solve the problem.
* (5) Once the answers are crystal clear, the data engineer (R4) and data scientist (R3) collaborate to locate the raw data sources for the initial data analysis. 

Data science team also check the distribution, and quality of the data and also the  performing validation checks. In addition, they ensure that the incoming data from the data sources is labeled, meaning that a target attribute is known, as this is a mandatory requirement for supervised ML. In this example, the data sources already had labeled data available as the labeling step was covered during an upstream process. 


### (B1) Requirements for feature engineering pipeline. 
The features are the relevant attributes required for model training. After the initial understanding of the raw data and the initial data analysis, the fundamental requirements for the feature engineering pipeline are defined, as follows: 

* (6) The data engineer (R4) defines the data transformation rules (normalization, aggregations) and cleaning rules to bring the data into a usable format.
* (7) The data scientist (R3) and data engineer (R4) together define the feature engineering rules, such as the calculation of new and more advanced features based on other features. 
* These initially defined rules must be iteratively adjusted by the data scientist (R3) either based on the feedback coming from the experimental model engineering stage or from the monitoring component observing the model performance. 

### (B2) Feature engineering pipeline. 
* The starting defined requirements for the feature engineering pipeline are roled by the data engineer (R4) and software engineer (R5) as a starting point to build up the prototype of the feature engineering pipeline. 
* The initially defined requirements and rules are updated according to the iterative feedback coming either from the experimental model engineering stage or from the monitoring component observing the model’s performance in production.
* As a foundational requirement, the data engineer (R4) defines the code required for the CI/CD (C1) and orchestration component (C3) to ensure the task orchestration of the feature engineering pipeline. It also defines the underlying infrastructure resource configuration.
* (8) First, the feature engineering pipeline connects to the raw data, which can be (for instance) streaming data, static batch data, or data from any cloud storage. 
* (9) The data will be extracted from the data sources.
* (10) The data preprocessing begins with data transformation and cleaning tasks. The transformation rule artifact defined in the requirement gathering stage serves as input for this task, and the main aim of this task is to bring the data into a usable format. These transformation rules are continuously improved based on the feedback.
* (11) The feature engineering task calculates new and more advanced features based on other features. The predefined feature engineering rules serve as input for this task. These feature engineering rules are continuously improved based on the feedback.
* (12) Lastly, a data ingestion job loads batch or streaming data into the feature store system (C4). The target can either be the offline or online database (or any kind of data store).

### (C) Experimentation. 

Majority of the works in the experimentation phase are handled by the data scientist (R3). The data scientist is cooperated by the software engineer (R5). 

* (13) The data scientist (R3) connects to the feature store system (C4) for the data analysis. (Alternatively, the data scientist (R3) can also connect to the raw data for an initial analysis.) In case of any required data adjustments, the data scientist (R3) reports the required changes back to the data engineering zone (feedback loop). 
* (14) Then the preparation and validation of the data coming from the feature store system is required. This task also includes the train and test split dataset creation. 
* (15) The data scientist (R3) estimates the best-performing algorithm and hyperparameters, and the model training is then triggered with the training data (C5). The software engineer (R5) supports the data scientist (R3) in the creation of well-engineered model training code. 
* (16) Different model parameters are tested and validated interactively during several rounds of model training. Once the performance metrics indicate good results, the iterative training stops. The best performing model parameters are identified via parameter tuning. The model training task and model validation task are then iteratively repeated; together, these tasks can be called “model engineering.” The model engineering aims to identify the best performing algorithm and hyperparameters for the model. 
* (17) The data scientist (R3) exports the model and commits the code to the repository. As a foundational requirement, either the DevOps engineer (R6) or the ML engineer (R7) defines the code for the (C2) automated ML workflow pipeline and commits it to the repository. Once either the data scientist (R3) commits a new ML model or the DevOps engineer (R6) and the ML engineer (R7) commits new ML workflow pipeline code to the repository, the CI/CD component (C1) detects the updated code and triggers automatically the CI/CD pipeline carrying out the build, test, and delivery steps. The build step creates artifacts containing the ML model and tasks of the ML workflow pipeline. The test step validates the ML model and ML workflow pipeline code. The delivery step pushes the versioned artifact(s)—such as images—to the artifact store (e.g., image registry). 


### (D) Automated ML workflow pipeline. 
The DevOps engineer (R6) and the ML engineer (R7) take care of the management of the automated ML workflow pipeline. They also manage the underlying model training infrastructure in the form of hardware resources and frameworks supporting computation such as Kubernetes (C5). The workflow orchestration component (C3) orchestrates the tasks of the automated ML workflow pipeline. For each task, the required artifacts (e.g., images) are pulled from the artifact store (e.g., image registry). Each task can be executed via an isolated environment (e.g., containers). Finally, the workflow orchestration component (C3) gathers metadata for each task in the form of logs, completion time, and so on. Once the automated ML workflow pipeline is triggered, each of the following tasks is managed automatically:
* (18) automated pulling of the versioned features from the feature store systems (data extraction). Depending on the use case, features are extracted from either the offline or online database (or any kind of data store). 
* (19) Automated data preparation and validation; in addition, the train and test split is defined automatically. 
* (20) Automated final model training on new unseen data (versioned features). The algorithm and hyperparameters are already predefined based on the settings of the previous experimentation stage. The model is retrained and refined. 
* (21) Automated model evaluation and iterative adjustments of hyperparameters are executed, if required. Once the performance metrics indicate good results, the automated iterative training stops. The automated model training task and the automated model validation task can be iteratively repeated until a good result has been achieved. 
* (22) The trained model is then exported and (23) pushed to the model registry (C6), where it is stored e.g., as code or containerized together with its associated configuration and environment files. For all training job iterations, the ML metadata store (C7) records metadata such as parameters to train the model and the resulting performance metrics. This also includes the tracking and logging of the training job ID, training date and time, duration, and sources of artifacts. Additionally, the model specific metadata called “model lineage” combining the lineage of data and code is tracked for each newly registered model. This includes the source and version of the feature data and model training code used to train the model. Also, the model version and status (e.g., staging or production-ready) is recorded. Once the status of a well-performing model is switched from staging to production, it is automatically handed over to the DevOps engineer or ML engineer for model deployment. 

* From there, the (24) CI/CD component (C1) triggers the continuous deployment pipeline. The production-ready ML model and the model serving code are pulled (initially prepared by the software engineer (R5)). The continuous deployment pipeline carries out the build and test step of the ML model and serving code and deploys the model for production serving.

* The (25) model serving component (C8) makes predictions on new, unseen data coming from the feature store system (C4). This component can be designed by the software engineer (R5) as online inference for real time predictions or as batch inference for predictions concerning large volumes of input data. For real-time predictions, features must come from the online database (low latency), whereas for batch predictions, features can be served from the offline database (normal latency). Model-serving applications are often configured within a container and prediction requests are handled via a REST API. As a foundational requirement, the ML engineer (R7) manages the model-serving computation infrastructure. 

* The (26) monitoring component (C9) observes continuously the model serving performance and infrastructure in real-time. Once a certain threshold is reached, such as detection of low prediction accuracy, the information is forwarded via the feedback loop. 

* The (27) feedback loop is connected to the monitoring component (C9) and ensures fast and direct feedback allowing for more robust and improved predictions. It enables continuous training, retraining, and improvement. With the support of the feedback loop, information is transferred from the model monitoring component to several upstream receiver points, such as the experimental stage, data engineering zone, and the scheduler (trigger). The feedback to the experimental stage is taken forward by the data scientist for further model improvements. The feedback to the data engineering zone allows for the adjustment of the features prepared for the feature store system. 

* Additionally, the detection of concept drifts as a feedback mechanism can enable (28) continuous training. For instance, once the model-monitoring component (C9) detects a drift in the data [3], the information is forwarded to the scheduler, which then triggers the automated ML workflow pipeline for retraining (continuous training). A change in adequacy of the deployed model can be detected using distribution comparisons to identify drift. Retraining is not only triggered automatically when a statistical threshold is reached; it can also be triggered when new feature data is available, or it can be scheduled periodically.


