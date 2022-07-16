# PART I: Machine Learning Operations (MLOps):Overview and Definition

“MLOps (Machine Learning Operations) is a paradigm, including aspects like best practices, sets of concepts, as well as a development culture when it comes to the end-to-end conceptualization, implementation, monitoring, deployment, and scalability of machine learning products. Most of all, it is an engineering practice that leverages three contributing disciplines: machine learning, software engineering (especially DevOps), and data engineering. MLOps is aimed at productionizing machine learning systems by bridging the gap between development (Dev) and operations (Ops). Essentially, MLOps aims to facilitate the creation of machine learning products by leveraging these principles: CI/CD automation, workflow orchestration, reproducibility; versioning of data, model, and code; collaboration; continuous ML training and evaluation; ML metadata tracking and logging; continuous monitoring; and feedback loops.”

The objective of any machine learning project is to light them into production and make an amazing product that customer demand. But the sad news is that most of the projects fail to give final product. To overcome this issue, the concept of MLOPs arise to solve this challenge.

Before understanding MLOPs we need to understand about Devops. 

* Devops is pure methodology arise to reduce social and political issues in software development. The goal of Devops is reduce the gap between development and operations and emphasizes collaboration, communication, and knowledge sharing. 


* It ensures automation with continuous integration, continuous delivery, and continuous deployment (CI/CD), thus allowing for fast, frequent, and reliable. 


* In addition, it is designed to ensure continuous testing, quality assurance, continuous monitoring, logging, and feedback loops releases.




### MLOPS Principles

![image](https://user-images.githubusercontent.com/91752852/179354046-e01006d0-692d-4834-8482-5155038770f0.png)

Figure 1. Implementation of principles within technical components






### P1 CI/CD automation. 

* Continuous integration, continuous delivery, and continuous deployment. 
* Involves build, test, delivery, and deploy steps.
* Enhance overall productivity through fast feedback

### P2 Workflow orchestration. 
* Workflow orchestration
* coordinates the tasks of an ML workflow pipeline according to directed acyclic graphs (DAGs). 
* DAGs define the task execution order by considering relationships and dependencies


### P3 Reproducibility. 

* Reproduce an ML experiment and obtain the exact same outcomes
P4 Versioning. 
* Ensures the versioning of data, model, and code to enable not only reproducibility, but also traceability 

### P5 Collaboration. 
* Ensures the possibility to work collaboratively on data, model, and code. 
* Besides the technical aspect, this principle emphasizes a collaborative and communicative work culture aiming to reduce domain silos between different roles 

### P6 Continuous ML training & evaluation

* Periodic retraining of the ML model based on new feature data. 
* Enabled through the support of a monitoring component, a feedback loop, and an automated ML workflow pipeline. 
* Continuous training always includes an evaluation run to assess the change in model quality 

### P7 ML metadata tracking/logging.

* Metadata is tracked and logged for each orchestrated ML workflow task. 
* Metadata tracking and logging is required for each training job iteration (e.g., training date and time, duration, etc.), including the model specific metadata—e.g., used parameters and the resulting performance metrics, model lineage: data and code used—to ensure the full traceability of experiment runs 
P8 Continuous monitoring. 
* The periodic assessment of data, model, code, infrastructure resources, and model serving performance (e.g., prediction accuracy) to detect potential errors or changes that influence the product quality 

### P9 Feedback loops. 

* Multiple feedback loops are required to integrate insights from the quality assessment step into the development or engineering process (e.g., a feedback loop from the experimental model engineering stage to the previous feature engineering stage). 
* Another feedback loop is required from the monitoring component (e.g., observing the model serving performance) to the scheduler to enable the retraining.

### Technical Components 

Once we defined the principles that need to be incorporated into MLOps, we now elaborate on the precise components and implement them in the ML systems design.The components are listed and described in a generic way with their essential functionalities. The references in brackets denotes respective principles that the technical components are applied. 

### C1 CI/CD Component (P1, P6, P9). 

* The CI/CD component ensures continuous integration, continuous delivery, and continuous deployment.
* It takes care of the build, test, delivery, and deploy steps. 
* It provides rapid feedback to developers regarding the success or failure of certain steps, thus increasing the overall productivity 
* E.g Jenkins  and GitHub actions 

### C2 Source Code Repository (P4, P5). 

* Examples include Apache Airflow, Kubeflow Pipelines, Luigi, AWS, SageMaker Pipelines and Azure Pipelines 

### C4 Feature Store System (P3, P4). 

* A feature store system ensures central storage of commonly used features. 
* It has two databases configured:  offline database feature stores to serve features with normal latency for experimentation, and online database feature stores to serve features with low latency for predictions in production.
* Examples include Google Feast, Amazon AWS Feature Store, Tecton.ai and Hopswork.ai 
* This is where most of the data for training ML models will come from. Moreover, data can also come directly from any kind of data store.

### C5 Model Training Infrastructure (P6). 

* The model training infrastructure provides the foundational computation either in distributed or non-distributed resources, e.g., CPUs, RAM, and GPUs.
* In general, a scalable and distributed infrastructure is recommended.
* For instance, local machines (not scalable) or cloud computation as well as non-distributed or distributed computation (several worker nodes) 
*  Frameworks supporting computation are Kubernetes and Red Hat OpenShift.

### C6 Model Registry (P3, P4).

* Stores centrally the trained ML models together with their metadata.
*  It has two major roles such as storing the ML artifact and storing the ML metadata.
* Advanced storage examples include MLflow, AWS SageMaker Model Registry, Microsoft Azure ML Model Registry, and Neptune.ai.
* Simple storage examples include Microsoft Azure Storage, Google Cloud Storage, and Amazon AWS S3

### C7 ML Metadata Stores (P4, P7).

* ML metadata stores allow for the tracking of various kinds of metadata, e.g., for each orchestrated ML workflow pipeline task.
* Another metadata store can be configured within the model registry for tracking and logging the metadata of each training job (e.g., training date and time, duration, etc.), including the model specific metadata—e.g., used parameters and the resulting performance metrics, model lineage: data and code used.
* Examples include orchestrators with built-in metadata stores tracking each step of experiment pipelines such as Kubeflow Pipelines, AWS SageMaker Pipelines, ML, and IBM Watson Studio .
* MLflow provides an advanced metadata store in combination with the model registry.



## MLOPS : Roles and Resonsibilities 

* Once the principles and their resulting instantiation of components are sketched, we identify necessary roles in order to realize MLOps as given below. MLOps is an interdisciplinary group process, and the interplay of different roles is crucial to design, manage, automate, and operate an ML system in production. In the following, every role, its purpose, and related tasks are briefly described:
R1 Business Stakeholder (similar roles: Product Owner, Project Manager). 
* Defines the business goal to be achieved with ML and takes care of the communication side of the business, e.g., presenting the return on investment (ROI) generated with an ML product 

### R1 Business Stakeholder (similar roles: Product Owner, Project Manager). 

* Defines the business goal to be achieved with ML and takes care of the communication side of the business, e.g., presenting the return on investment (ROI) generated with an ML product 


### R2 Solution Architect (similar role: IT Architect).

* Designs the architecture and defines the technologies to be used, following a thorough evaluation.

### R3 Data Scientist (similar roles: ML Specialist, ML Developer). 

* Converts the business problem into an ML problem and takes care of the model engineering, including the selection of the best-performing algorithm and hyperparameters

### R4 Data Engineer (similar role: DataOps Engineer). 
* The data engineer builds up and manages data and feature engineering
pipelines.
* Ensures proper data ingestion to the databases of the feature store system

### R5 Software Engineer. 
* Applies software design patterns, widely accepted coding guidelines, and best practices to turn the raw ML problem into a well-engineered product 

### R6 DevOps Engineer. 
* Bridges the gap between development and operations and ensures proper CI/CD automation, ML workflow orchestration, model deployment to
production, and monitoring 

### R7 ML Engineer/MLOps Engineer.
* Incorporates skills from data scientists, data engineers, software engineers, DevOps engineers, and backend engineers.
* Builds up and operates the ML infrastructure, manages the automated ML workflow pipelines and model deployment to production, and monitors both the model and the ML infrastructure.

![chrome_Elx8ROn9oQ](https://user-images.githubusercontent.com/91752852/179354343-e498812a-e0e0-4d62-b0f3-b6558c2f42e1.png)


Fig 2: Roles and their intersections contributing to the MLOps paradigm

             

