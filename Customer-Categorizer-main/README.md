Customer Personality Segmentation
Problem Statement
In this data science project, we aim to build a machine learning system capable of predicting customer personality traits using machine learning algorithms. This project can be highly beneficial for malls, retail stores, and product-based companies. By analyzing a customer’s personal and purchase details, we can cluster them and predict their cluster number using classification techniques.

Proposed Solution
So how do we dynamically predict a customer’s cluster?
One effective approach is to use machine learning, where we first cluster customers based on the available data and then use classification methods—supported by domain knowledge and historical customer data—to predict the appropriate cluster.

Dataset Used
Dataset Link (Marketing Campaign)

Tech Stack Used
Python

FastAPI

Machine Learning Algorithms

Docker

MongoDB

Infrastructure Required
AWS S3

Azure

GitHub Actions

How to Run
Before starting, make sure you have a MongoDB Atlas account and the shipping dataset uploaded to it.

Step 1: Clone the repository

bash
Copy
Edit
git clone https://github.com/Machine-Learning-01/Customer_segmentation.git
Step 2: Create a conda environment

bash
Copy
Edit
conda create --prefix venv python=3.7 -y
conda activate venv/
Step 3: Install dependencies

bash
Copy
Edit
pip install -r requirements.txt
Step 4: Export environment variables

bash
Copy
Edit
export AWS_ACCESS_KEY_ID=<AWS_ACCESS_KEY_ID>
export AWS_SECRET_ACCESS_KEY=<AWS_SECRET_ACCESS_KEY>
export AWS_DEFAULT_REGION=<AWS_DEFAULT_REGION>
export MONGODB_URL=<MONGODB_URL>
Step 5: Run the application server

bash
Copy
Edit
python app.py
Step 6: Train the application

bash
Copy
Edit
http://localhost:5000/train
Step 7: Make predictions

bash
Copy
Edit
http://localhost:5000/predict
Run Locally Using Docker
Ensure the Dockerfile is present in your project directory.

Build the Docker image:

bash
Copy
Edit
docker build --build-arg AWS_ACCESS_KEY_ID=<AWS_ACCESS_KEY_ID> \
             --build-arg AWS_SECRET_ACCESS_KEY=<AWS_SECRET_ACCESS_KEY> \
             --build-arg AWS_DEFAULT_REGION=<AWS_DEFAULT_REGION> \
             --build-arg MONGODB_URL=<MONGODB_URL> .
Run the Docker image:

bash
Copy
Edit
docker run -d -p 5000:5000 <IMAGE_NAME>
Project Architecture


Data Collection Architecture


Deployment Architecture


Models Used
K-Means Clustering

Logistic Regression

After hyperparameter tuning, these two models—K-Means for clustering and Logistic Regression for classification—were selected and integrated into the pipeline.

GridSearchCV was used for hyperparameter optimization.

src Folder – Main Package Structure
Components: Contains all modules of the machine learning project:

Data Ingestion

Data Validation

Data Transformation

Data Clustering

Model Trainer

Model Evaluation

Model Pusher

Custom Logger and Exception Handling have also been included for better debugging and traceability.

Conclusion
This project is practical and can be deployed in real-life applications to better understand and segment customers dynamically.
